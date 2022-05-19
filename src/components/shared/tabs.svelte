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
        flex-flow: row wrap;
        justify-content: center;
        padding: 0;
        list-style: none;
    }
    li {
        margin: 0 16px;
        font-size: 1.4rem;
        color: #fff;
        cursor: pointer;
        font-weight: bold;
        font-family: Montserrat, sans-serif;
        padding: 4px 8px 4px 8px;
    }
    /* .active {
        color: #f8f40a;
    } */
    li:hover {
        background-color: yellow;
        font-weight: bold;
        color: black;
        border-radius: 2px;
        padding: 4px 8px 4px 8px;
    }
</style>
