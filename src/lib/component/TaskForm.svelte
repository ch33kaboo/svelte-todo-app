<script>
export let title
export let description
export let time
</script>

<div class="flex flex-col gap-2">
    <input class="py-2 px-3 rounded-md text-lg text-gray-800" placeholder="Title (mandatory)" type="text" bind:value="{title}">
    <input class="py-2 px-3 rounded-md text-lg text-gray-800" placeholder="description (optional)" type="text" bind:value="{description}">
    <input class="py-2 px-6 rounded-md text- text-2xl text-gray-800" placeholder="time" type="time" bind:value="{time}">
</div>