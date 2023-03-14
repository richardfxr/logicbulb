<script lang="ts">
    /* === IMPORTS ============================ */
    import Switch from "$lib/switch.svelte";
    
    /* === REFS =============================== */
    let sticky: HTMLElement;
    let main: HTMLElement;

    /* === VARIABLES ========================== */
    let scrollPos = 0; // stores the current scrollLeft value to prevented repeated on:scroll calls
    let switch1 = false;
    let switch2 = false;
    let switch3 = false;
    let switch4 = false;
    let switch5 = false;
    let switch6 = false;
    let switch7 = false;
    let switch8 = false;
</script>



<div bind:this={sticky} class="container" id="sticky" on:scroll={e => {
    // return if already at scrollPos to prevent on:scroll loop
    if (sticky.scrollLeft === scrollPos) return;

    main.scrollLeft = sticky.scrollLeft;
    scrollPos = sticky.scrollLeft
    console.log("scrolled main");
}}>
    <ol class="inputs">
        <li class="input">
            <Switch
                a11yLabel="switch 1"
                bind:output={switch1} />
        </li>
        <li class="input">
            <Switch
                a11yLabel="switch 2"
                bind:output={switch2} />
        </li>
        <li class="input">
            <Switch
                a11yLabel="switch 3"
                bind:output={switch3} />
        </li>
        <li class="input">
            <Switch
                a11yLabel="switch 4"
                bind:output={switch4} />
        </li>
        <li class="input">
            <Switch
                a11yLabel="switch 5"
                bind:output={switch5} />
        </li>
        <li class="input">
            <Switch
                a11yLabel="switch 6"
                bind:output={switch6} />
        </li>
        <li class="input">
            <Switch
                a11yLabel="switch 7"
                bind:output={switch7} />
        </li>
        <li class="input">
            <Switch
                a11yLabel="switch 8"
                bind:output={switch8} />
        </li>
    </ol>
</div>

<div bind:this={main} class="container" on:scroll={e => {
    // return if already at scrollPos to prevent on:scroll loop
    if (main.scrollLeft === scrollPos) return;

    sticky.scrollLeft = main.scrollLeft;
    scrollPos = main.scrollLeft;
    console.log("scrolled sticky");
}}>
    <ol class="inputs">
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
    </ol>
    <ol class="inputs">
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
    </ol>
    <ol class="inputs">
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
    </ol>
    <ol class="inputs">
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
    </ol>
    <ol class="inputs">
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
    </ol>
    <ol class="inputs">
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
    </ol>
    <ol class="inputs">
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
    </ol>
    <ol class="inputs">
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
        <li class="input"></li>
    </ol>
</div>



<style lang="scss">
    :global {
        body {
            background-color: var(--clr-100);
        }
    }
    .container {
        display: flex;
        flex-flow: column nowrap;

        overflow: auto;
    }

    ol.inputs {
        list-style-type: none;
        display: grid;
        grid-template-columns: repeat(8, var(--cell-width));

        padding: 0 15px;
        margin: 0 auto 0 auto;
    }

    #sticky {
        position: sticky;
        top: -40px;
    }

    li {
        display: block;
        height: var(--cell-height);
    }
</style>