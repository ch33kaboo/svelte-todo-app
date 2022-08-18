<script>
  import "./app.css"
  import Header from "./lib/component/Header.svelte"
  import Button from "./lib/component/Button.svelte";
  import Footer from "./lib/component/Footer.svelte";
  import TodoItem from "./lib/component/TodoItem.svelte";
  import TodoList from "./lib/component/TodoList.svelte";

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

  let dark = ""

  const allPage = document.getElementsByTagName('html')
  const toggleDarkMode = () => {
    dark = dark === "dark" ? "" : "dark"
  }
</script>

<div class="{dark}">
  <div class="bg-slate-300 dark:bg-slate-700 w-screen min-h-screen overflow-hidden">
    <Header/>

    <main class="relative">
      <main on:click="{toggleDarkMode}" class="absolute top-0 right-5 rounded-b-xl overflow-hidden shadow-md hover:shadow-lg">
        <Button content="Toggle Dark Mode"/>
      </main>
    </main>

    <TodoList>
      <slot>
        {#each todos as todo}
          <TodoItem title="{todo.title}" description="{todo.description}" time="{todo.time}"/>
        {/each}
      </slot>
    </TodoList>

    <Footer/>

  </div>
</div>

<style>
</style>
