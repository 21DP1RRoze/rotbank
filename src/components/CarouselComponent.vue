<template>
  <div class="carousel">
    <slot :currentSlide="currentSlide"/>


    <div class="navigate">
      <div class="toggle-page left">
        <i @click="prevSlide" class="fa-solid fa-left-long"></i>
      </div>
      <div class="toggle-page right">
        <i @click="nextSlide" class="fa-solid fa-right-long"></i>
      </div>
    </div>
    
    <div class="pagination">
      <span @click="goToSlide(index)" v-for="(slide, index) in getSlideCount" :key="index" :class="{active: index + 1 ===currentSlide}"></span>
    </div>
  </div>
</template>

<script>
import {ref, onMounted} from "vue"; //since it can't get the value initally, needs onMounted so it checks the value after it has been compiled or whatever
export default {
  setup() {
    const currentSlide = ref(1);
    const getSlideCount = ref(null);
    const autoPlayEnabled = ref(true);
    const timeoutDuration = ref(5000);

    //next slide
    const nextSlide = () => {
      if (currentSlide.value === getSlideCount.value) {
        currentSlide.value =1;
        return;
      }
      currentSlide.value +=1;
    };

    //prev slide
    const prevSlide = () => {
      if (currentSlide.value === 1) {
        currentSlide.value = getSlideCount.value;
        return;
      }
      currentSlide.value -=1;
    }

    const goToSlide = (index) => {
      currentSlide.value = index+1;
    }

    // auto PLAY!!!!
    const autoPlay = () => {
      setInterval(() => {
        nextSlide();
      }, timeoutDuration.value);
    }

    if (autoPlayEnabled.value === true) {
      autoPlay();
    }

    // checks how many slides there are and inserts it into getSlideCount
    onMounted(() => {
      getSlideCount.value = document.querySelectorAll(".slide").length;
    })

    return {currentSlide, nextSlide, prevSlide, getSlideCount, goToSlide};
  }
}
</script>

<style lang="scss">
  .navigate {
    padding: 0 16px;
    height: 100%;
    width: 100%;
    position: absolute;
    display: flex;
    justify-content: center;
    align-items: center;
    .toggle-page {
      display:flex;
      flex: 1;
    }
    .right {
      justify-content: flex-end;
    }
    i {
      cursor:pointer;
      display:flex;
      align-items: center;
      justify-content: center;
      border-radius: 50%;
      width: 40px;
      height: 40px;
      background-color:#EDF2F4;
      color:#0B090A;
    }
  }

  .pagination {
    position: absolute;
    bottom: 24px;
    width: 100%;
    display:flex;
    gap: 16px;
    justify-content:center;
    align-items: center;
    
    span {
      cursor:pointer;
      width:20px;
      height:20px;
      border-radius: 50%;
      background-color: #EDF2F4;
      box-shadow: 0 1px 3px 0 rgba(0,0,0, 0.1), 0 1px 2px 0 rgba(0,0,0, 0.06);
       
    }
    .active {
      background-color: #EE8B98;
    }
  }
</style>