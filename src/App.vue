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
    {
        questionText: "I used the wrong method with the wrong technique",
        answerOptions: [
            { answerText: "Useless", isCorrect: false },
            { answerText: "It's No Good", isCorrect: false },
            { answerText: "Wrong", isCorrect: true },
        ],
    },
    {
        questionText: "Your favourite slave",
        answerOptions: [
            { answerText: "In Your Room", isCorrect: true },
            { answerText: "Master and Servant", isCorrect: false },
            { answerText: "Puppets", isCorrect: false },
        ],
    },
    {
        questionText: "Death is everywhere",
        answerOptions: [
            { answerText: "Ghosts Again", isCorrect: false },
            { answerText: "Fly on the Windscreen", isCorrect: true },
            { answerText: "Barrel of a Gun", isCorrect: false },
        ],
    },
    {
        questionText: "It used to be so civilised",
        answerOptions: [
            { answerText: "People are People", isCorrect: false },
            { answerText: "Policy of Truth", isCorrect: true },
            { answerText: "People Are Good", isCorrect: false },
        ],
    },
    {
        questionText: "Words are meaningless",
        answerOptions: [
            { answerText: "Shout", isCorrect: false },
            { answerText: "Lie To Me", isCorrect: false },
            { answerText: "Enjoy the Silence", isCorrect: true },
        ],
    },
    {
        questionText: "I stand still stepping on a shady street",
        answerOptions: [
            { answerText: "New Life", isCorrect: true },
            { answerText: "Photographic", isCorrect: false },
            { answerText: "Just Can't Get Enough", isCorrect: false },
        ],
    },
    {
        questionText: "Sitting waiting, anticipating nothing",
        answerOptions: [
            { answerText: "Black Celebration", isCorrect: false },
            { answerText: "Sacred", isCorrect: false },
            { answerText: "Nothing", isCorrect: true },
        ],
    },
    {
        questionText: "Faith is sleeping",
        answerOptions: [
            { answerText: "Ghosts Again", isCorrect: true },
            { answerText: "Blasphemous Rumours", isCorrect: false },
            { answerText: "Mercy In You", isCorrect: false },
        ],
    },
    {
        questionText: "Things get damaged",
        answerOptions: [
            { answerText: "Useless", isCorrect: false },
            { answerText: "Precious", isCorrect: true },
            { answerText: "Broken", isCorrect: false },
        ],
    },
    {
        questionText: "I look to you, and your strong belief",
        answerOptions: [
            { answerText: "Stripped", isCorrect: false },
            { answerText: "Black Celebration", isCorrect: true },
            { answerText: "Personal Jesus", isCorrect: false },
        ],
    },
]

const currentQuestion = ref(0)
const score = ref(0)
const showScore = ref(false)

const handleAnswerButtonClick = (opt) => {
    if (currentQuestion.value < questions.length - 1) {
        if (opt == true) {
            score.value++
        }
        currentQuestion.value++
    } else {
        if (opt == true) {
            score.value++
        }
        showScore.value = ref(true)
        if (score.value > questions.length * 0.66) {
            jsConfetti.addConfetti({
                emojis: ['💜', '🖤'],
                emojiSize: 30,
            }
            )
        }
    }
}
</script>

<template>
    <div class="quiz">
        <header>Depeche Mode Lyrics Quiz</header>
        <main>
            <p v-if="showScore" class="score-section">Du fick {{ score }} poäng av totalt {{ questions.length }} poäng</p>
            <div v-else>
                <div> <!--  class="question-section" -->
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
