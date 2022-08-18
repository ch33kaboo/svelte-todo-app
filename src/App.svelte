<script>
  import "./app.css"
  import Header from "./lib/component/Header.svelte"
  import Button from "./lib/component/Button.svelte";
  import Footer from "./lib/component/Footer.svelte";
  import TodoList from "./lib/component/TodoList.svelte";

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

    <TodoList/>
    <Footer/>

  </div>
</div>

<style>
</style>
