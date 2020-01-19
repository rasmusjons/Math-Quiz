<template>
    <div>
        <h1>Math Quiz</h1>
        <hr />
        <!-- <app-gif></app-gif> -->
        <div class="mainContainer">
            <transition name="flip" mode="out-in">
                <appCorrect
                    v-if="display"
                    class="correct"
                    @newQuestion="displayNewQuestion"
                ></appCorrect>
                <div v-if="!display">
                    <app-question
                        :sign="sign"
                        :numberA="numberA"
                        :numberB="numberB"
                    ></app-question>
                    <app-answer
                        v-if="!display"
                        :answers="answers"
                        :numberA="numberA"
                        :numberB="numberB"
                        style="cursor: pointer"
                        @clickedAnswer="displayCorrect"
                    ></app-answer>
                </div>
            </transition>
            <div class="progressbar" v-if="pointsTaken">
                <app-progressbar :counter="counter"></app-progressbar>
            </div>
        </div>
    </div>
</template>

<script>
    import Question from './components/Question.vue';
    import Answer from './components/Answer.vue';
    import Correct from './components/Correct.vue';
    import Progressbar from './components/Progressbar.vue';
    import GifApi from './components/GifApi.vue';

    export default {
        data() {
            return {
                numberA: '',
                numberB: '',
                sign: '+',
                result: '',
                answers: [],
                display: false,
                counter: 0,
                pointsTaken: false,
            };
        },
        mounted() {
            this.createNumbers();
        },
        methods: {
            createNumbers() {
                this.numberA = Math.floor(Math.random() * 50);
                this.numberB = Math.floor(Math.random() * 50);

                if (this.numberA >= 25) {
                    this.result = this.numberA - this.numberB;
                    this.sign = '-';
                    this.answers.splice(0, 0, this.result);
                } else {
                    this.result = this.numberA + this.numberB;
                    this.sign = '+';
                    this.answers.splice(0, 0, this.result);
                }

                for (let i = 0; i < 3; i++) {
                    let numberC = this.result + Math.floor(Math.random() * 10);
                    let randomAnswerPosition = Math.floor(Math.random() * 4);

                    if (!this.answers.includes(numberC)) {
                        this.answers.splice(randomAnswerPosition, 0, numberC);
                        console.log(this.answers);
                    } else i--;
                }
            },
            displayCorrect(index) {
                let value = this.answers[index];
                if (this.result != value) {
                    alert('wrong ey!');
                    this.counter = 0;
                } else {
                    this.pointsTaken = true;
                    this.counter++;
                    this.display = true;
                }
            },
            displayNewQuestion(hej) {
                this.answers = [];
                this.createNumbers();
                this.display = false;
            },
            button() {
                this.display = !this.display;
            },
        },
        components: {
            appQuestion: Question,
            appAnswer: Answer,
            appCorrect: Correct,
            appProgressbar: Progressbar,
            appGif: GifApi,
        },
    };
</script>

<style scoped>
    .mainContainer {
        border: solid 1px lightgrey;
        width: 600px;
        margin: auto;
        height: 200px;
    }

    h1 {
        margin: auto;
        margin-top: 20px;
        text-align: center;
        padding: 30px;
    }

    /*FUNGERAR ---> */
    /* .flip-enter {
            opacity: 0;
        }
        .fade-leave {
            opacity: 0;
        }

        .flip-enter-active {
            transition: opacity 1s;
        }
        .flip-leave-active {
            transition: opacity 1s;
        } */

    /* .flip-enter {
            transform: rotateY(180deg);
        }
        .fade-leave {
            transform: rotateY(180deg);
        }

        .flip-enter-active {
            transition: transform 0.5s;
        }
        .flip-leave-active {
            transition: transform 0.5s;
        } */

    .flip-enter {
        /* transform: rotateY(0deg); */
    }
    .fade-leave {
        /* transform: rotateY(0deg); */
    }

    .flip-enter-active {
        animation: flip-in 0.5s ease-out forwards;
    }
    .flip-leave-active {
        animation: flip-out 0.5s ease-out forwards;
    }

    @keyframes flip-out {
        from {
            transform: rotateY(0deg);
        }
        to {
            transform: rotateY(90deg);
        }
    }

    @keyframes flip-in {
        from {
            transform: rotateY(90deg);
        }
        to {
            transform: rotateY(0deg);
        }
    }

    .progressbar {
        border: solid 1px green;
        width: 100%;
        height: 40px;
    }
</style>
