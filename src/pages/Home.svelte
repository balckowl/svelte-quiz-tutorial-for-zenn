<script lang="ts">
    import Correct from "../components/Game/Correct.svelte";
    import GameOver from "../components/Game/GameOver.svelte";
    import GameStart from "../components/Game/GameStart.svelte";
    import InCorrect from "../components/Game/InCorrect.svelte";
    import Quiz from "../components/Game/Quiz.svelte";
    import type { quizesType } from "../types";

    let flag: number = 0;
    let count: number = 0;
    export let quizes:quizesType[];
</script>

<main>
    <div class="container h-screen-60 flex justify-center flex-col mx-auto">
        <div class="grid grid-cols-10">
            <div class="col-start-3 col-span-6">
                {#if flag === 0}
                    <GameStart bind:flag={flag} />
                {:else if flag === 1}
                    <Quiz bind:flag={flag} bind:count={count} quizes={quizes}/>
                {:else if flag === 2}
                    <Correct bind:flag={flag} bind:count={count} quizes={quizes}/>
                {:else if flag === 3}
                    <InCorrect bind:flag={flag} />
                {:else if flag === 4}
                    <GameOver bind:flag={flag} bind:count={count}/>
                {/if}
            </div>
        </div>
    </div>
</main>

<style>
    .h-screen-60 {
        height: calc(100vh - 120px);
    }
</style>
