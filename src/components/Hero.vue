<template>
    <div class="hero-content">
        <div class="hero-content-items">
            <div class="social-items">
                <div class="item">
                    <img src="../assets/github.svg" alt="">
                </div>
                <div class="item">
                    <img src="../assets/linked-in.svg" alt="">
                </div>
                <div class="item">
                    <img src="../assets/instagram.svg" alt="">
                </div>
            </div>
            <div class="buttons">
                <div class="resume-button">

            </div>
        </div>
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
                'machine learning models.',
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
    .hero-content {
        display: flex;
        height: 922px;
        background-image: url('../assets/hero-background.svg');
        border: 2px solid black;
    }
    .hero-content-items {
        display: flex;
        flex-basis: 100%;
        height: 50px;
        padding: 25px;
        border: 2px solid green;
    }
    .social-items {
        display: flex;
        width: 200px;
        justify-content: space-between;
        border: 1px solid white;
    }
    .item {
        width: 50px;
        height: 50px;
    }
    .item:hover {
        cursor: pointer;
        transform: translateY(5px);
    }
    .item img {
        width: 50px;
        height: 50px;
    }
    .buttons {
        display: flex;
        justify-content: flex-end;
        flex-basis: 100%;
        border: 1px solid white;
    }
    .resume-button {
        align-self: center;
        background-color: #FEB132;
        width: 138px;
        height: 54px;
        border-radius: 15px;
        border: 1px solid #F05B23;
    }
    .resume-button:hover {
        cursor: pointer;
        background-color: #f69f13;
    }
    @media (min-width: 320px) and (max-width: 768px) {
        .hero-content-items {
            flex-direction: column;
            align-items: center;
        }
    }
</style>