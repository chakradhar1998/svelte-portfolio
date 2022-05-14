<script>
    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();
    export let items;
    export let activeItem;
</script>

<div class="tabs">
    <ul>
        {#each items as item}
            <li on:click={() => dispatch("tabChange", item)}>
                <div class:active={item === activeItem}>{item}</div>
            </li>
        {/each}
    </ul>
</div>

<style>
    .tabs {
        margin-bottom: 40px;
    }
    ul {
        display: flex;
        justify-content: center;
        padding: 0;
        list-style: none;
    }
    li {
        margin: 0 16px;
        font-size: 1.4rem;
        color: #fff;
        cursor: pointer;
        font-family: Montserrat, sans-serif;
    }
    .active {
        color: #f8f40a;
        padding-bottom: 8px;
    }
</style>
