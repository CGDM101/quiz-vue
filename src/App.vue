<script setup>
import { ref } from 'vue'

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

</script>

<template>
    <header>Depeche Mode Lyrics Quiz</header>
    <main>
        <p class="score-section">du har x poäng av {{ questions.length }} poäng</p>
        <p class="question-section">
        <div class="question-count">fråga {{ currentQuestion + 1 }} av {{ questions.length }}</div>
        <div class="question-text">{{ questions[0].questionText }}</div>
        </p>
        <div class="answer-section">
            <button v-for="opt in questions[0].answerOptions">{{ opt.answerText }}</button>
        </div>
    </main>
</template>

<style scoped></style>
