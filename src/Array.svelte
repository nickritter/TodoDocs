<script>

export let arrayName;
export let arrayIn;

</script>

<div class="array">
<h2>{arrayName}</h2>
    <ul>
        {#each arrayIn as item}
            <li>{item.toString()}</li>
        {/each}
    </ul>
</div>