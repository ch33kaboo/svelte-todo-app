<script>
    import {createEventDispatcher} from 'svelte'
    let dispatch = createEventDispatcher()

    export let title
    export let description = "no description given"
    export let time = "no time given"

    let deleteItem = (title) => {
        dispatch('deleteItem', title)
    }

</script>

<div class="flex flex-col sm:flex-row items-center justify-between gap-3 rounded-xl px-5 py-3 bg-slate-400 dark:bg-slate-800 border border-slate-800 dark:border-slate-200 border-opacity-60 dark:border-opacity-60 text-slate-800 dark:text-slate-200">
    <div class="flex  items-center gap-6">
        <div class="font-bold w- w-20">{time}</div>
        <div class="flex flex-col items-start">
            <div class="text-xl font-semibold capitalize">{title}</div>
            <div class="-mt-1 {description === "no description given" ? "opacity-60" : "opacity-95"}">{description}</div>
        </div>
    </div>
    <div on:click={() => {deleteItem(title)}} class="cursor-pointer">
        <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2m7-2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
    </div>
</div>

<style>

</style>