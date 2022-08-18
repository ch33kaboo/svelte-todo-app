<script>
    import Button from "./Button.svelte";
    import TodoItem from "./TodoItem.svelte"


    let todos = [
    {
      title : "go to the gym",
      time : "8:30am"
    },
    {
      title : "hangout with friends",
      description : "got to meet Ali and Sophia at the park",
      time : "9:45am"
    },
    {
      title : "have lunch",
      description : "going to a mexican restaurant",
      time : "11:30am"
    },
    {
      title : "have a nap",
      time : "1:00pm"
    },
  ]

const clearTasks = () => {
    todos = []
}

</script>

<div class="mx-20 mb-9 mt-11 px-10 py-4 border border-slate-800 dark:border-slate-200 border-opacity-60 dark:border-opacity-60 rounded-md bg-slate-400 dark:bg-slate-800 bg-opacity-40 dark:bg-opacity-40 flex flex-col gap-1">
    {#each todos as todo}
        <TodoItem title="{todo.title}" description="{todo.description}" time="{todo.time}"/>
    {/each}
    <div class="flex justify-end items-center gap-3">
        <div class="rounded-md overflow-hidden mt-3">
            <Button content="add a task"/>
        </div>
        <div on:click="{clearTasks}" class="rounded-md overflow-hidden mt-3">
            <Button content="clear all tasks"/>
        </div>
    </div>
</div>