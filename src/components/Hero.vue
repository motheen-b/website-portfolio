<template>
    <div class="hero-content">
        <div class="top-bar">
            <div class="social-content">
                <div class="social-item">
                    <img src="../assets/github.svg" alt="">
                </div>
                <div class="social-item">
                    <img src="../assets/linked-in.svg" alt="">
                </div>
                <div class="social-item">
                    <img src="../assets/instagram.svg" alt="">
                </div>
            </div>
            <div class="button-content">
                <div class="button">
                    Resume
                </div>
            </div>
        </div>
        <div class="text-content">
            <h1>Hi my name is,</h1>
            <h2>Motheen Baig</h2>
            <h3>{{ displayedText }}‎ </h3>
            <h4>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quia perferendis quisquam qui molesti</h4>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            messages: [
                'Web3 applications.', 
                'automation solutions.', 
                "RESTful API's.",
                'ML models.',
                'data analytics solutions.'
            ],
            selectedMessageIndex: 0,
            displayedText: '',
            typingSpeed: 100
        }
    },
    mounted() {
        this.doTyping()
    },
    methods: {
        doTyping() {
            let index = 0;
            let message = this.messages[this.selectedMessageIndex];
            console.log('Message:', message)
            const type = () => {
                if (index < message.length) {
                    this.displayedText += message.charAt(index)
                    index++;
                    setTimeout(type, this.typingSpeed);
                } else {
                    setTimeout(this.doBackspace, 1000)
                }
            }
            type()
        },
        doBackspace() {
            const backspace = () => {
                if (this.displayedText.length > 0) {
                    this.displayedText = this.displayedText.slice(0, -1);
                    setTimeout(backspace, 50);
                } else {
                    this.selectedMessageIndex++;
                    console.log('idx', this.selectedMessageIndex)
                    if (this.selectedMessageIndex > this.messages.length - 1) {
                        this.selectedMessageIndex = 0;
                    }
                    setTimeout(this.doTyping, this.typingSpeed);
                }
            }
            backspace()
        },
    }
}
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700');
    .hero-content {
        display: flex;
        flex-direction: column;
        flex-basis: 100%;
        height: 922px;
        background-image: url('../assets/hero-background.svg');
        border: 2px solid black;
    }
    .top-bar {
        display: flex;
        padding: 25px;
        /* border: 2px solid green; */
    }
    .social-content {
        display: flex;
        align-items: center;
        /* padding-top: 2px; */
        width: 200px;
        justify-content: space-between;
        /* border: 2px solid black; */
    }
    .social-item {
        width: 50px;
        height: 50px;
    }
    .social-item img {
        width: 50px;
        height: 50px;
    }
    .social-item:hover {
        cursor: pointer;
        transform: translateY(10px);
    }
    .button-content {
        display: flex;
        flex-basis: 100%;
        justify-content: flex-end;
        /* border: 2px solid white; */
    }
    .button {
        display: flex;
        justify-content: center;
        align-items: center;
        align-self: center;
        width: 138px;
        height: 54px;
        border-radius: 15px;
        background-color: #FEB132;
        border: 1px solid #F05B23;
        box-shadow: 2px 2px 8px rgba(0, 0, 0, 0.3);
    }
    .button:hover {
        cursor: pointer;
        background-color: #f4c818;
    }
    .text-content {
        display: flex;
        flex-direction: column;
        /* justify-content: space-between; */
        /* align-items: center; */
        justify-content: center;
        margin: 25px;
        padding: 25px;
        height: 922px;
        /* border: 2px solid white; */
    }
    h1 {
        font-size: 22px;
        color: rgb(20, 228, 20);
        text-shadow: 0px 4px 8px #000000;
        padding-bottom: 10px;
    }
    h2 {
        font-size: 36px;
        color: white;
        text-shadow: 0px 4px 8px #000000;
        padding-bottom: 10px;
    }
    h3 {
        font-size: 36px;
        color: rgb(234, 225, 225);
        text-shadow: 0px 4px 8px #000000;
        padding-bottom: 10px;
    }
    h4 {
        font-size: 22px;
        color: white;
        text-shadow: 0px 4px 8px #000000;
    }
    @media (min-width: 320px) and (max-width: 768px) {
        .hero-content {
            height: 600px;
        }
        .top-bar {
            padding: 15px;
            flex-direction: column;
            align-items: center;
        }
        h1 {
            font-size: 20px;
        }
        h2 {
            font-size: 32px;
        }
        h3 {
            font-size: 32px;
        }
        h4 {
            font-size: 20px;
        }
    }
</style>