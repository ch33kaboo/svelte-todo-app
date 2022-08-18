<script>
    import Button from "./Button.svelte";

</script>

<div class="mx-20 mb-9 mt-11 px-10 py-4 border border-slate-800 dark:border-slate-200 border-opacity-60 dark:border-opacity-60 rounded-md bg-slate-400 dark:bg-slate-800 bg-opacity-40 dark:bg-opacity-40 flex flex-col gap-1">
    <slot></slot>
    <div class="flex justify-end items-center gap-3">
        <div class="rounded-md overflow-hidden mt-3">
            <Button content="add a task"/>
        </div>
        <div class="rounded-md overflow-hidden mt-3">
            <Button content="clear all tasks"/>
        </div>
    </div>
</div>