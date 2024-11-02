<script lang="ts">
    import Header from "./Header.svelte";
    let name = $state("araf");
    let status: "OPEN" | "CLOSED" = $state("OPEN");
    function toggle() {
        status = status === "OPEN" ? "CLOSED" : "OPEN";
    }
    function onclick() {
        status = status === "OPEN" ? "CLOSED" : "OPEN";
    }
</script>

<Header {name} />
<div class="flex justify-center">
    <input type="text" bind:value={name} class="border" />
</div>
<div class="flex justify-center">
    <p>Status: {status}</p>
</div>
<div class="flex justify-center">
    <button onclick={toggle}>toggle 1</button>
</div>
<div class="flex justify-center">
    <button {onclick}>toggle 2</button>
</div>
<div class="flex justify-center">
    <button
        onclick={() => {
            status = status === "OPEN" ? "CLOSED" : "OPEN";
        }}>toggle 3</button
    >
</div>
