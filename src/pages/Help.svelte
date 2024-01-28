<script lang="ts">
    import type { quizesType } from "../types";

    export let quizes: quizesType[];
</script>

<main>
    <div class="container mx-auto h-screen-60 mt-4">
        <h2 class="text-4xl mb-2">問題一覧</h2>
        <ul>
            {#each quizes as quiz}
                <li>{quiz.ques} - {quiz.ans}</li>
            {/each}
        </ul>
    </div>
</main>

<style>
    .h-screen-60 {
        height: calc(100vh - 120px);
    }
</style>
