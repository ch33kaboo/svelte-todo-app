<script>
    import Button from "./Button.svelte";
    import TodoItem from "./TodoItem.svelte"
    import TaskForm from "./TaskForm.svelte"

    let time
    let title
    let description

    let addTask = () => {
      let newTask = {
        time,
        title,
        description
      }

      todos = [newTask, ...todos]
    }

    let emptyInputs = () => {
      time = ""
      title = ""
      description = ""
    }

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

const deleteItem = (e) => {
  todos = todos.filter((task) => task.title != e.detail)
}

</script>

<div class="mx-5 sm:mx-20 mb-9 mt-11 px-4 sm:px-10 py-4 border border-slate-800 dark:border-slate-200 border-opacity-60 dark:border-opacity-60 rounded-md bg-slate-400 dark:bg-slate-800 bg-opacity-40 dark:bg-opacity-40 flex flex-col gap-2 sm:gap-1">
    {#each todos as todo}
        <TodoItem on:deleteItem={deleteItem} title="{todo.title}" description="{todo.description}" time="{todo.time}"/>
        {:else}
        <p class="text-center capitalize text-gray-800 dark:text-gray-200">there are no tasks to show</p>
    {/each}
    <div class="flex justify-end items-center gap-3">
        <label on:click="{emptyInputs}" for="my-modal" class="rounded-md overflow-hidden mt-3 px-3 py-1 text-slate-200 dark:text-slate-800 bg-gray-600 bg-opacity-80 dark:bg-gray-100 dark:bg-opacity-80 hover:bg-opacity-95 dark:hover:bg-opacity-95 modal-button cursor-pointer text-center">add a task</label>
        <!-- I didnt use the Button component because it doesnt work with daisyUI, the modal button has to be a label tag but I had a Button component tag -->
            <input type="checkbox" id="my-modal" class="modal-toggle" />

            <div class="modal">
                <div class="modal-box">
                  <TaskForm bind:time="{time}" bind:title="{title}" bind:description="{description}"/>
                    <div class="modal-action">
                        <label on:click="{addTask}" for="my-modal" class="btn">Add Task!</label>
                    </div>
                </div>
            </div>            
                                

        
        <div on:click="{clearTasks}" class="rounded-md overflow-hidden mt-3">
            <Button content="clear all tasks"/>
        </div>
    </div>
</div>