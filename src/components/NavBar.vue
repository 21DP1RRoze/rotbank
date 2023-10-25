<template>
    <LoginPop></LoginPop>
  <nav>
    <div class="leftNAV">
        <router-link to="#"><i class="fa-solid fa-house"></i>HOME</router-link>
        <router-link class="abtus" to="#"><i class="fa-solid fa-circle-info"></i>ABOUT US</router-link>
    </div>
    <div class="logo"></div>
    <div class="rightNAV">
        <div class="auth" @click="openPopUp"><i class="fa-solid fa-user"></i>AUTHENTIFICATION</div>
    </div>
    
  </nav>
  <div class="underline"></div>
</template>

<script>
import LoginPop from './LoginPop.vue';
export default {
    name: "NavBar",
    components: {
        LoginPop
    },
    setup() {
        const openPopUp = () => {
            document.getElementById("loginPopUp").style.display= "block";
        }
        return {openPopUp}
    }
}
</script>

<style>
    nav {
        height: 7vh;
        position: relative;
        z-index: 2;
        top: 0;
        left: 0;
        right: 0;
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin-left: 15%;
        margin-right: 15%;
        
    }
    .abtus {
        padding-left: 60px;
    }
    .logo {
        background-image: url('../assets/logo.png');
        height: 6vh;
        width: 30vh;
        background-repeat:no-repeat;
        background-position: center;
        background-size:contain;
        position:absolute;
        left: 40%;
    }
    .rightNAV, .leftNAV {
        font-family: 'Urbanist', sans-serif;
        font-size: 14pt;
    }
    
    nav i {
        padding-right: 12px;
    }
    a {
        color:#2B2D42;
        text-decoration: none;
    }
    .underline {
        height:2px;
        width: 100%;
        background-color:#2B2D42;
    }
    .auth {
        cursor:pointer;
        color: #2B2D42;
    }
</style>