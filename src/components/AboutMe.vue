<template>
    <div class="about-me-content">
        <div class="about-me-header">
            About Me
        </div>
        <div class="about-me-items">
        <div class="about-me-details">
            <div class="about-me-text">
                Halo
            </div>
        <div class="about-me-img">
            <img src="../assets/instagram.svg" alt="">
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
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700');
    * {
        font-family: 'Inter', sans-serif;
    }
    .about-me-content {
        display: flex;
        flex-direction: column;
        padding: 50px;
        border: 2px solid black;
    }
    .about-me-header {
        display: flex;
        justify-content: center;
        padding: 25px;
        font-weight: 600;
        color: white;
        font-size: 35px;
        text-shadow: 0px 4px 8px #000000;
        border: 2px solid black;
    }
    
    .about-me-items {
        display: flex;
        /* flex-basis: 20%; */
        flex-direction: row;
        justify-content: space-between;
        padding: 25px;
        border: 2px solid green;
    }
    .about-me-text {
        display: flex;
        flex-basis: 100%;
        color: white;
        border: 2px solid green;
    }
    .about-me-img {
        width: 50px;
        height: 50px;
        border: 2px solid black;
    }
    .about-me-img img {
        width: 50px;
        height: 50px;
    }
</style>