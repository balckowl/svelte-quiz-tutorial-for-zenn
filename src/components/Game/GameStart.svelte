<script lang="ts">
    export let flag:number;

    const GameStart = () => {
        flag = 1;
    }
</script>

<div
    class="border border-black h-[500px] rounded flex justify-center items-center flex-col"
>
    <h2 class="text-7xl mb-3">漢字クイズ</h2>
    <button type="button" class="bg-orange-500 py-2 px-4 rounded" on:click={GameStart}>始める</button
    >
</div>
