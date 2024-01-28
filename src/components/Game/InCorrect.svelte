<script lang="ts">
    import { onMount } from "svelte";

    export let flag: number;

    onMount(() => {
        setTimeout(() => {
            flag = 4;
        }, 2000);
    });
</script>

<div
    class="border border-black h-[500px] rounded flex justify-center items-center flex-col"
>
    <h2 class="text-7xl mb-3">不正解</h2>
</div>
