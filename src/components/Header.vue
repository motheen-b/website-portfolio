<template>
    <div class="header-container">
        <div class="header-items">
            <div class="item">
                <img src="../assets/phone-img.svg" alt="">
                +1 (647)-901-7565
            </div>
            <div class="item">
                <img src="../assets/email-img.svg" alt="">
                motheenbaig@gmail.com
            </div>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700');
    .header-container {
        display: flex;
        flex-basis: 100%;
        align-items: center;
        height: 50px;
        padding-right: 25px;
        font-family: 'Inter', sans-serif;
        font-size: 14px;
        background: linear-gradient(to right, #F05C23, #8A3514);
        /* border: 2px solid black; */
    }
    .header-items {
        display: flex;
        justify-content: flex-end;
        flex-basis: 100%;
        /* border: 2px solid green; */
    }
    .item {
        display: flex;
        align-items: center;
        color: white;
        margin-left: 10px;
        text-shadow: 0px 4px 8px #000000;
    }
    .item:hover {
        cursor: pointer;
        text-decoration: underline;
    }
    .item-img {
        width: 30px;
        height: 30px;
    }
    .item img {
        /* display: flex; */
        width: 30px;
        height: 30px;
    }
    @media (min-width: 320px) and (max-width: 768px) {
        .header-container {
            height: 70px;
            padding-right: 0px;
        }
        .header-items {
            padding-top: 10px;
            padding-bottom: 10px;
            flex-direction: column;
            align-items: center;
        }
    }
</style>