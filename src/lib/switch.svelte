<script lang="ts">
    /* === PROPS ============================== */
    export let a11yLabel: string;
    export let output = false;
</script>



<div class="cell">
    <label
        class="switch"
        class:active={output}>
        <input
            class="visuallyHidden"
            type="checkbox"
            bind:checked={output}>
        <span class="visuallyHidden">{a11yLabel}</span>
        <span class="top">{output ? "1" : "0"}</span>
    </label>
</div>




<style lang="scss">
    .cell {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: 100%;
    }

    label {
        cursor: pointer;
        display: block;
        position: relative;

        font-family: sans-serif;
        font-size: 1.8rem;

        margin-top: calc(-1 * var(--input-transY-hover));

        // prevent text selection
        -webkit-user-select: none; // Safari
        user-select: none;

        &::before {
            content: "";
            position: absolute;
            inset: 0;
            z-index: -2;

            background-color: #ED9718;
            border-radius: var(--border-radius);
            border: var(--border);
        }

        .top {
            display: block;
            position: relative;

            padding: 21px 13px 9px 13px;
            border-radius: var(--border-radius) var(--border-radius) 0 0;
            border-top: var(--border);
            border-right: var(--border);
            border-left: var(--border);

            transform: translateY(var(--input-transY));

            transition: transform var(--trans-input);

            &::before {
                content: "";
                position: absolute;
                inset: 0;
                z-index: -1;

                background: linear-gradient(0deg, #FFE0B3 0%, #FFCF8A 80%);
                border-radius: calc(var(--border-radius) - var(--border-width));
            }
        }

        &:hover, &:focus {
            .top {
                transform: translateY(var(--input-transY-hover));
            }
        }

        &:active, &.active {
            .top {
                transform: translateY(var(--input-transY-active));
            }
        }

        &.active {
            &:hover, &:focus {
                .top {
                    transform: translateY(var(--input-transY-active-hover));
                }
            }

            &:active {
                .top {
                    transform: translateY(var(--input-transY-active));
                }
            }
        }
    }

    input {
        visibility: hidden;
    }
</style>