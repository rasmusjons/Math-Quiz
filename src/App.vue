<template>
    <div>
        <h1>The Super Quiz</h1>
        <h3 v-if="counter === 10">Congratz</h3>
        <hr />
        <div class="mainContainer">
            <appCorrect v-if="display" class="correct" @newQuestion="displayNewQuestion"></appCorrect>
            <transition name="flip">
                <div v-if="!display">
                    <app-question class="question" :numberA="numberA" :numberB="numberB"></app-question>
                    <app-answer
                        class="answer"
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
import Question from "./components/Question.vue";
import Answer from "./components/Answer.vue";
import Correct from "./components/Correct.vue";
import Progressbar from "./components/Progressbar.vue";

export default {
    data() {
        return {
            numberA: "",
            numberB: "",
            answers: [],
            display: false,
            counter: 0,
            pointsTaken: false
        };
    },
    mounted() {
        this.createNumbers();
    },
    methods: {
        createNumbers() {
            let randomAnswerPosition = Math.floor(Math.random() * 4);
            this.numberA = Math.floor(Math.random() * 50);
            this.numberB = Math.floor(Math.random() * 50);
            let result = this.numberA + this.numberB;
            this.answers.splice(0, 0, result);

            for (let i = 0; i < 3; i++) {
                let numberC = result + Math.floor(Math.random() * 10);
                if (!this.answers.includes(numberC)) {
                    this.answers.splice(randomAnswerPosition, 0, numberC);
                } else i--;
            }
        },
        displayCorrect(index) {
            let value = this.answers[index];
            let answer = this.numberA + this.numberB;
            if (answer != value) {
                alert("wrong ey!");
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
        }
    },
    components: {
        appQuestion: Question,
        appAnswer: Answer,
        appCorrect: Correct,
        appProgressbar: Progressbar
    }
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

.flip-enter {
    transition: rotateY(0deg);
}
.flip-enter-active {
    transition: rotateY(180deg);
}
.flip-leave {
}
.flip-leave-active {
    transition: opacity 1s;
    opacity: 0;
}

.progressbar {
    border: solid 1px green;
    width: 100%;
    height: 40px;
}
</style>

