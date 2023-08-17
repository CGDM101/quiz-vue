<script setup>

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

</script>

<template>
    <header>Depeche Mode Lyrics Quiz</header>
    <main>
        <p class="score-section">du har x poäng av x poäng</p>
        <p class="question-section">Frågan</p>
        <div class="answer-section">
            <button>opt1</button>
            <button>opt2</button>
            <button>opt2</button>
            <button>opt3</button>
        </div>
    </main>
</template>

<style scoped></style>
