<template>
  <div class="home">
    <Nav />
    <Carousel class="carousel" v-slot="{currentSlide}">
      <Slide v-for="(slide, index) in carouselSlides" :key="index">
        <div v-show="currentSlide === index + 1" class="slide-info">
          <img :src="require(`../assets/${slide}.jpg`)" alt="">
          <p class="slideTitle">The bank for everyone!</p>
          <p class="slideSubTitle">Find out more!</p>
          <a href="#text"><i class="fa-solid fa-question fa-xl"></i></a>
        </div>
      </Slide>
    </Carousel>
    <MainContent />
  </div>
</template>

<script>
import Carousel from '../components/CarouselComponent.vue'
import Slide from '../components/SlideComponent.vue'
import Nav from '../components/NavBar.vue'
import MainContent from '../components/MainContent.vue'


export default {
  name: 'HomeView',
  components: {
    Carousel, Slide, Nav, MainContent
  },
  setup() {
    const carouselSlides = ['carousel1', 'carousel2', 'carousel3'];
    const titleText = ["Get free consultations!", "Sustainable living", "Superb loans!"]

    return {carouselSlides, titleText};
  },
}
</script>

<style lang="scss" scoped>
.carousel {
  position:relative;
  max-height: 85vh;
  height: 75vh;
  width: 100%;

  .slide-info {
    
    position:absolute;
    top: 0;
    left: 0;
    width: 100%;
    max-height: 100%;
    height: 100%;
    

    img {
      width: 100%;
      min-width: 85%;
      height: 100%;
      object-fit: cover;
    }

    p {
      position: absolute;
      top: 20%;
      left: 10%;
      z-index: 1;
      color: white;
      
    }
    .slideTitle {
      font-size: 72pt;
      text-shadow: 1px 2px rgba(0,0,0,0.5);
      font-family: 'Staatliches';
    }
    .slideSubTitle {
      font-size: 32pt;
      text-shadow: 1px 2px rgba(0,0,0,0.5);
      top: 45%;
    }


    i {
      position: absolute;
      top: 60%;
      left: 10%;
      z-index: 1;
      cursor:pointer;
      display:flex;
      align-items: center;
      justify-content: center;
      border-radius: 20%;
      width: 50px;
      height: 50px;
      background-color:#EDF2F4;
      color:#0B090A;
    }
  }
}
</style>
