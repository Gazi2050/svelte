<script lang="ts">
    let {
        name,
        fake_name = "ioi",
    }: { name: string; fake_name?: string | null } = $props();
</script>

<h1 class="text-red-600 text-center font-bold text-2xl">
    Hello {name}
</h1>
<h2 class="text-red-600 text-center font-bold text-2xl">
    {name.replaceAll("a", "z")}
</h2>

{fake_name}
