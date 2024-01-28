<script lang="ts">
    import type { ChangeEventHandler } from "svelte/elements";
    import type { quizesType } from "../../types";

    export let flag: number;
    export let count: number;
    export let quizes: quizesType[];

    let answer: string = "";

    const handleSubmit = () => {
        if (answer) {
            if (answer == quizes[count].ans) {
                // alert("正解");
                flag = 2;
                count += 1;
            } else {
                // alert("不正解");
                flag = 3;
            }
        } else {
            alert("入力されていません。");
        }
    };
</script>

<div
    class="border border-black h-[500px] rounded flex justify-center items-center flex-col"
>
    <div class="text-center mb-2">
        <p class="text-3xl">
            {#each Array(quizes[count].ans.length) as _, i}
                ○
            {/each}
        </p>
        <h2 class="text-7xl mb-3">{quizes[count].ques}</h2>
    </div>

    <div class="mb-5">
        <input
            type="text"
            class="border border-black focus:outline-none rounded py-1 px-2"
            bind:value={answer}
        />
    </div>

    <button
        type="button"
        class="bg-orange-400 px-5 py-2 rounded"
        on:click={handleSubmit}>確定</button
    >
</div>
