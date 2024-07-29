<template>
    <div class="hero-content">
        <div class="top-bar">
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
                    Resume
            </div>
        </div>
        </div>
        <div class="hero-body-content">
            safsdf
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
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700');
    .hero-content {
        font-family: 'Inter', sans-serif;
        display: flex;
        flex-direction: column;
        height: 922px;
        background-image: url('../assets/hero-background.svg');
        border: 2px solid black;
    }
    .top-bar {
        display: flex;
        height: 50px;
        padding: 25px;
        border: 2px solid green;
    }

    .hero-body-content {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100%;
        padding: 50px 50px;
        border: 2px solid white;
    }

    .social-items {
        display: flex;
        width: 200px;
        justify-content: space-between;
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
        align-items: center;
        flex-basis: 100%;
    }
    .resume-button {
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: #FEB132;
        width: 138px;
        height: 54px;
        border-radius: 15px;
        text-shadow: 2px 2px 4px rgba(1, 1, 1, 0.5);
        border: 1px solid #F05B23;
        box-shadow: 2px 2px 8px rgba(0, 0, 0, 0.3);
    }
    .resume-button:hover {
        cursor: pointer;
        background-color: #f69f13;
    }
    @media (min-width: 320px) and (max-width: 768px) {
        .top-bar {
            flex-direction: column;
            align-items: center;
            height: 100px;
        }
        .buttons {
            padding: 15px;
        }
    }
</style>