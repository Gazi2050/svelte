<script lang="ts">
    let formState = $state({
        id: "",
        name: "",
        step: 0,
        error: "",
    });
</script>

<main>
    <p class="text-2xl font-bold m-5">Step:{formState.step}</p>
    {#if formState.step === 0}
        <div>
            <label for="name">Name :</label>
            <input
                class="border"
                type="text"
                id="name"
                bind:value={formState.name}
            />
        </div>
    {/if}
</main>
