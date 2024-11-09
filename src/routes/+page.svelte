<script lang="ts">
    let formState = $state({
        id: "",
        name: "",
        step: 0,
        error: "",
    });
</script>

<main>
    <p>Svelte</p>
    <p class="text-2xl font-bold m-5">Step:{formState.step}</p>
    {#if formState.step === 0}
        <div class="m-2">
            <label for="name">Name :</label>
            <input
                class="border"
                type="text"
                id="name"
                bind:value={formState.name}
            />
            <button
                class="border p-1 bg-orange-200 rounded"
                onclick={() => {
                    if (formState.name !== "") {
                        formState.step += 1;
                        formState.error = "";
                    } else {
                        formState.error = "Enter Name";
                    }
                }}>Next</button
            >
        </div>
    {/if}

    {#if formState.error}
        <p class="text-xl font-bold text-red-600 m-2">
            {formState.error}
        </p>
    {/if}

{#snippet formStep({question,id,type}:{question:string;type:string;id:string})}
<article>
<div>
    <label for={id}>{question}</label>
    <input {type} {id} bind:value={formState[id]}>
</div>
</article>
{/snippet}
</main>
