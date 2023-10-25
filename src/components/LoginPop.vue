<template>
    <div id="loginPopUp">
        <div class="bg-frosted"></div>
        <div class="container">
            <span class="closebtn"><i @click="closePopUp" class="fa-solid fa-xmark fa-xl"></i></span>
            <p>Welcome back!</p>
            <form class="loginBox">
                <label for="aCode">Auth code:</label><br>
                <input type="text" id="aCode" name="aCode"><br><br><br>
                <label for="passw">Password:</label><br>
                <input type="password" id="passw" name="passw"><br><br><br>
                <input type="submit" value="Log in">
            </form>
            <a class="donthaveaccount" href="#">Don't have an account?</a>
        </div>
    </div>
</template>

<script>
export default {
    name: "loginPopUp",
    
    setup() {
        const closePopUp = () => {
            document.getElementById("loginPopUp").style.display= "none";
        }
        const openPopUp = () => {
            document.getElementById("loginPopUp").style.display= "block";
        }
        return {closePopUp, openPopUp}
    }

}

</script>

<style>

    .bg-frosted {
        position:absolute;
        background: rgba(255, 255, 255, 0.17);
        backdrop-filter: blur(9.5px);
        -webkit-backdrop-filter: blur(9.5px);
        z-index: 3;
        width: 100vw;
        height: 100vh;
    }
    .container {
        display:block;
        position:absolute;
        height: 60vh;
        width: 22vw;
        background-color: white;
        z-index: 4;
        left: 50%;
        transform: translate(-50%, -50%);
        top: 50%;
        box-shadow: 0px 0px 8px 2px gray;
    }
    .loginBox {
        position:absolute;
        left: 50%;
        transform: translate(-50%, -50%);
        top: 55%;
    }
    label {
        font-family: 'Urbanist', sans-serif;
        font-size: 16pt;
        
    }
    input[type="text"], input[type="password"] {
        margin-top:6px;
        padding: 8px;
        width: 16vw;
        border:none;
        border-bottom: solid 2px #CAD2C5;
        transition: 200ms ease-in-out;

    }
    input[type="submit"] {
        padding:12px;
        width: 8vw;
        border-radius: 0;
        margin-left: 50%;
        background-color: #CAD2C5;
        border:none;
        color: #2F3E46;
        font-size: 12pt;
        font-family: 'Gabarito', cursive;
        cursor:pointer;
        transition: 200ms ease-in-out;
    }
    input[type="submit"]:hover {
        background-color: #52796F;
    }
    
    .container p {
        font-family: 'Gabarito', cursive;
        font-size: 300%;
        text-align: center;
        margin-top: 50px;
    }
    input[type="text"]:focus, input[type="password"]:focus {
        border:none;
        border-bottom: solid 2px #2F3E46;
        outline:none;
        
    }
    .donthaveaccount {
        position:absolute;
        top: 90%;
        left: 50%;
    }
    .closebtn {
        position:absolute;
        right:10px;
        top: 10px;
        cursor:pointer;
    }

    #loginPopUp {
        display:none;
    }
</style>