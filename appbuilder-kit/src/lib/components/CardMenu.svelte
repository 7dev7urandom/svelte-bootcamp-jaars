<script lang="ts">
    import { clickOutside } from '$lib/scripts/click_outside';
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();
    export let actions = [""];
    let showMenu = false;

    function handleAction(action: string) {
        dispatch('menuaction', {
            text: action
        });
    }
</script>

<div use:clickOutside on:outclick={() => showMenu = false} class="annotation-item-menu annotation-float-right">
    <span on:click={() => showMenu = !showMenu} class="dropbtn">
        <img class="dropbtn-image" src="icons/ic_more_vert_black_24dp.png" alt="vertical dots">
    </span>
    <div class="dropdown-content {showMenu? "show":"hidden"}">
        {#each actions as a}
        <!-- svelte-ignore a11y-missing-attribute-->
            <a on:click={() => handleAction(a)}>{a}</a>
        {/each}
    </div>
</div>