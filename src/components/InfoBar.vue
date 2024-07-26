<template>
    <div>
        <div class="info-container">
            <div class="social-icons">
                <div class="icon" @click="openGithub()">
                    <img src="../assets/github.svg" alt="">
                </div>
                <div class="icon">
                    <img src="../assets/linked-in.svg" alt="">
                </div>
                <div class="icon">
                    <img src="../assets/instagram.svg" alt="">
                </div>
            </div>
            <div class="buttons">
                <div class="button">
                    Resume
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
    function openGithub() {
        window.location.href = 'https://github.com/motheen-b/';
    }
    function openLinkedIn() {

    }
    function openInstagram() {

    }
</script>

<style scoped>
    .info-container {
        display: flex;
        color: white;
        z-index: 2;
        position: absolute;
        width: 1440px;
        padding: 25px;
        /* border: 2px solid green; */
    }
    .social-icons {
        display: flex;
        align-content: center;
        /* border: 2px solid black; */
    }
    .icon {
        margin-top: 2px;
        width: 50px;
        height: 50px;
        margin-right: 35px;
        /* border: 2px solid white; */
    }
    .icon img {
        width: 50px;
        height: 50px;
    }
    .icon:hover {
        cursor: pointer;
        transform: translateY(5px);
    }
    .buttons {
        display: flex;
        justify-content: flex-end;
        font-family: 'Inter', sans-serif;
        width: 100%;
        /* border: 2px solid black; */
    }

    

    .button {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 138px;
        height: 54px;
        font-size: 20px;
        border-radius: 15px;
        border: 1px solid #F05B23;
        background-color: #FEB132;
        text-shadow: 2px 2px 4px #000000;
        box-shadow: 0 4px 8px rgba(55, 59, 57, 0.8);
    }
    .button:hover {
        cursor: pointer;
        border: 1px solid #F05B23;
        background-color: #eeb559;
    }
</style>