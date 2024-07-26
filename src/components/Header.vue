<template>
    <div>
        <div class="header-container">
            <div class="header-items">
                <div class="svg-icon">
                    <img src="../assets/phone-img.svg" alt="">
                </div>
                <div class="item">
                    +1 (647)-901-7565
                </div>
                <div class="svg-icon">
                    <img src="../assets/email-img.svg" alt="">
                </div>
                <div class="item">
                    motheenbaig@gmail.com
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
    .header-container {
        display: flex;
        justify-content: flex-end;
        height: 50px;
        font-family: 'Inter', sans-serif;
        /* background: linear-gradient(to right, #a29f9f, #09192E); */
        background: linear-gradient(to right, #F05C23, #8A3514);
    }
    .header-items {
        display: flex;
        align-items: center;
        margin: 10px;
    }
    .item {
        color: white;
    }
    .item:hover {
        cursor: pointer;
        text-decoration: underline;
    }
    .svg-icon {
        margin-top: 2px;
        margin-left: 10px;
        margin-right: 4px;
        height: 30px;
        width: 30px;
    }
    .svg-icon img {
        height: 30px;
        width: auto;
    }
</style>