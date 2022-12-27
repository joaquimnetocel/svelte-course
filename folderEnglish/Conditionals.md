# CONDITIONALS

HTML DOESN'T HAVE A WAY OF EXPRESSING LOGIC, LIKE CONDITIONALS AND LOOPS. SVELTE DOES.

## IF

TO CONDITIONALLY SHOW SOME CONTENT, WE CAN WRAP IT IN AN IF BLOCK:

```svelte
<script>
    let numberCounter = 0;
    function functionIncrease() {
        numberCounter = numberCounter + 1;
    }
    function functionDecrease() {
        numberCounter = numberCounter - 1;
    }
</script>

<p>NUMBER: {numberCounter}</p>
<p>
    <button on:click={functionDecrease}>DECREASE</button>
    <button on:click={functionIncrease}>INCREASE</button>
</p>
{#if numberCounter >= 0 }
    <p>IT IS NOT A NEGATIVE NUMBER.</p>
{/if}
{#if numberCounter < 0}
    <p>IT IS A NEGATIVE NUMBER.</p>
{/if}
```

[RUN CODE](https://svelte.dev/repl/07ac151beb5a45a1af27309b61355af9)

## ELSE

WE CAN ALSO USE AN ELSE BLOCK. EXAMPLE:

```svelte
<script>
    let numberCounter = 0;
    function functionIncrease() {
        numberCounter = numberCounter + 1;
    }
    function functionDecrease() {
        numberCounter = numberCounter - 1;
    }
</script>

<p>NUMBER: {numberCounter}</p>
<p>
    <button on:click={functionDecrease}>DECREASE</button>
    <button on:click={functionIncrease}>INCREASE</button>
</p>
{#if numberCounter >= 0 }
    <p>IT IS NOT A NEGATIVE NUMBER.</p>
{:else}
    <p>IT IS A NEGATIVE NUMBER.</p>
{/if}
```

[RUN CODE](https://svelte.dev/repl/e0248a10bcf94f9888bc6500bd783342)

A `#` CHARACTER ALWAYS INDICATES A BLOCK OPENING TAG. A `/` CHARACTER ALWAYS INDICATES A BLOCK CLOSING TAG. A `:` CHARACTER, AS IN `{:ELSE}`, INDICATES A BLOCK CONTINUATION TAG.

## ELSE IF

MULTIPLE CONDITIONS CAN BE 'CHAINED' TOGETHER WITH ELSE IF:

```svelte
<script>
    let numberCounter = 0;
    function functionIncrease() {
        numberCounter = numberCounter + 1;
    }
    function functionDecrease() {
        numberCounter = numberCounter - 1;
    }
</script>

<p>NUMBER: {numberCounter}</p>
<p>
    <button on:click={functionDecrease}>DECREASE</button>
    <button on:click={functionIncrease}>INCREASE</button>
</p>
{#if numberCounter > 0 }
    <p>IT IS A POSITIVE NUMBER.</p>
{:else if numberCounter === 0}
    <p>THE NUMBER IS ZERO.</p>
{:else}
    <p>IT IS A NEGATIVE NUMBER.</p>
{/if}
```

[RUN CODE](https://svelte.dev/repl/51bb0c2a918a49e0950ca37e5db70e10)

[BACK](../README.md)
