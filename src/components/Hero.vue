<template>
    <div class="hero-content">
        <div class="hero-content-items">
            
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
        border: 2px solid green;
    }
</style>