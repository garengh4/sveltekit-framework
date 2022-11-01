<script>
    import schools from "../schools.json";

    let selectedSchool = null;
</script>

<svelte:head>
    <title>Home</title>
    <meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
    <h2>
        try editing <strong>src/routes/+page.svelte</strong>
    </h2>

    <!-- =========================================================================================================================== -->
    <main>
        {#if selectedSchool}
            <!-- svelte-ignore a11y-invalid-attribute -->
            <p><a href="#" on:click={() => selectedSchool = null}>Go back to school list</a></p>
            <h1>School : {selectedSchool.SCHOOLNAME}</h1>
            <p>Education Level : {selectedSchool.SCH_TYPE}</p>
            <p>Principal : {selectedSchool.PRINCIPAL}</p>

        {:else}
            <ul>
                <h3>School List</h3>
                <p>Select a school to read some details about it</p>
                {#each schools as school} 
                    <!-- svelte-ignore a11y-invalid-attribute -->
                    <li><a href="#" on:click={() => selectedSchool = school}>{school.SCHOOLNAME}</a></li>
                {/each}
            </ul>
        {/if}

    </main>
</section>

<style>
    section {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        flex: 0.6;
    }

    h1 {
        width: 100%;
    }
</style>
