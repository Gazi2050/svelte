<script lang="ts">
    let { name }: { name: string } = $props();
</script>

<h1 class="text-red-600 text-center font-bold text-2xl">
    Hello {name}
</h1>
<h2 class="text-red-600 text-center font-bold text-2xl">
    {name.replaceAll("a", "z")}
</h2>
