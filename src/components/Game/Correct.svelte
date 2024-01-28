<script lang="ts">
    import { onMount } from "svelte";
    import type { quizesType } from "../../types";

    export let flag: number;
    export let quizes: quizesType[]; 
    export let count: number;

    onMount(() => {
        setTimeout(() => {
            if(count == quizes.length){
                flag = 4
            }else{
                flag = 1
            }
        }, 2000); 
    });

</script>

<div
    class="border border-black h-[500px] rounded flex justify-center items-center flex-col"
>
    <h2 class="text-7xl mb-3">正解</h2>
</div>
