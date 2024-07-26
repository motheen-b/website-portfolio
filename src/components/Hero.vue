<template>
    <div>
        <div class="hero-container">
            <div class="hero-text-container">
                <div class="hero-text-1">Hi, my name is</div>
                <div class="hero-text-2">Motheen Baig.</div>
                <div class="hero-text-3">#I build {{ displayedText }} ‎ </div>
                <div class="hero-text-4">
                    I kode 4 real doe, holla @ your boy
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
    @keyframes blink-caret {
        from, to {
            border-color: transparent;
        }
        50% {
            border-color: rgb(255, 255, 255);
        }
    }
    .hero-container {
        display: flex;
        font-family: 'Inter', sans-serif;
        width: 1440px;
        height: 922px;
        background-repeat: no-repeat;
        z-index: 1;
        position: fixed;
        text-shadow: 0px 4px 8px #000000;
        background-image: url('../assets/hero-background.svg');
        background-color: #09192E;
    }
    .hero-text-container {
        display: flex;
        height: 500px;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        margin: auto auto;
        overflow:inherit;
    }
    .hero-text-1 {
        font-size: 18px;
        color: rgb(255, 255, 255);
        margin-bottom: 15px;
    }
    .hero-text-2 {
        font-weight: 600;
        font-size: 54px;
        color: white;
        margin-bottom: 15px;
    }
    .hero-text-3 {
        border-right: 0.15em solid rgb(255, 255, 255);
        font-weight: 600;
        font-size: 48px;
        color: rgb(113, 255, 37);
        margin-bottom: 15px;
        animation: blink-caret 0.75s step-end infinite;
    }
    .hero-text-4 {
        font-size: 18px;
        color: white;
    }
</style>