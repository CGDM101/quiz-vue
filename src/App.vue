<script setup>
import { ref } from 'vue'
import JSConfetti from 'js-confetti'
const jsConfetti = new JSConfetti()

const questions = [
    {
        questionText: "This twisted tortured mess",
        answerOptions: [
            { answerText: "Barrel of a Gun", isCorrect: true },
            { answerText: "Clean", isCorrect: false },
            { answerText: "Wrong", isCorrect: true },
        ],
    },
    {
        questionText: "Take second best put me to the test",
        answerOptions: [
            { answerText: "In Your Room", isCorrect: false },
            { answerText: "Nothing", isCorrect: false },
            { answerText: "Personal Jesus", isCorrect: true },
        ],
    },
    {
        questionText: "All the things I detest I will almost like",
        answerOptions: [
            { answerText: "Somebody", isCorrect: true },
            { answerText: "A Question of Lust", isCorrect: false },
            { answerText: "In Your Room", isCorrect: false },
        ],
    },
    {
        questionText: "Girl of sixteen, whole life ahead of her",
        answerOptions: [
            { answerText: "Nothing", isCorrect: false },
            { answerText: "Blasphemous Rumours", isCorrect: true },
            { answerText: "Little 15", isCorrect: false },
        ],
    },
]

const currentQuestion = ref(0)
const score = ref(0)
const showScore = ref(false)

const handleAnswerButtonClick = (opt) => {
    if (currentQuestion.value < questions.length - 1) {
        currentQuestion.value++
        if (opt == true) {
            score.value++
        } else if (opt == false) { }
    } else {
        if (opt == true) {
            score.value++
        } else if (opt == false) { }
        console.log('end of quiz, total socre: ', score.value);
        showScore.value = ref(true)
        jsConfetti.addConfetti({
            emojis: ['💜', '🖤'],
            emojiSize: 30,
        }
        )
    }
}
</script>

<template>
    <div class="app">
        <header>Depeche Mode Lyrics Quiz</header>
        <main>
            <p v-if="showScore" class="score-section">Du fick {{ score }} poäng av {{ questions.length }} totalt poäng</p>
            <div v-else>
                <div class="question-section">
                    <p class="question-count"> {{ currentQuestion + 1 }} / {{ questions.length }}:</p>
                    <p class="question-text">{{ questions[currentQuestion].questionText }}</p>
                </div>
                <div class="answer-section">
                    <button @click="handleAnswerButtonClick(opt.isCorrect)"
                        v-for="opt in questions[currentQuestion].answerOptions">{{
                            opt.answerText }}</button>
                </div>

                <img src='./assets/vio2.png' alt="violator-rose" />
            </div>

        </main>


    </div>
</template>

<style scoped></style>
