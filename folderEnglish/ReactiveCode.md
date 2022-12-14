# REACTIVE CODE

## UNDERSTANDING THE PROBLEM

IN ADDITION TO KEEPING THE TEMPLATE IN SYNCHRONY WITH THE VARIABLES (AS WE SAW IN THE PREVIOUS SECTION), THE REACTIVITY OF SVELTE IS CAPABLE OF KEEPING VARIABLES IN SYNCHRONY WITH OTHER VARIABLES. BUT FIRST, LET'S UNDERSTAND THE PROBLEM AND REALIZE THAT IT IS NOT SOMETHING CARRIED OUT AUTOMATICALLY. THE FOLLOWING EXAMPLE ILLUSTRATES THE PROBLEM:

```svelte
<script>
let numberAge = 20;
let numberDoubleAge = 2*numberAge;
function functionIncreaseAge() {
    numberAge = numberAge + 1;
}
</script>

<p>THE AGE IS {numberAge} AND ITS DOUBLE IS {numberDoubleAge}.</p>
<button on:click={functionIncreaseAge}>INCREASE</button>
```

[RUN CODE](https://svelte.dev/repl/683c5ee5076d474781b5a462d9695119)

AS WE CAN SEE IN THE EXAMPLE ABOVE, WHEN CLICKING ON THE BUTTON, ONLY THE `numberAge` VARIABLE IS CHANGED AND THE `numberDoubleAge` IS NOT RECALCULATED.

## REACTIVE VARIABLES

TO MAKE A VARIABLE REACTIVE WE CAN DO THE FOLLOWING:

```svelte
<script>
let numberAge = 20;
$: numberDoubleAge = 2*numberAge;

function functionIncreaseAge() {
    numberAge += 1;
}
</script>

<p>THE AGE IS {numberAge} AND ITS DOUBLE IS {numberDoubleAge}.</p>
<button on:click={functionIncreaseAge}>INCREASE</button>
```

[RUN CODE](https://svelte.dev/repl/10dd3b43ea154659af9c28f4776d0f3f)

HERE, THE `$` TELLS SVELTE TO RECALCULATE THE VARIABLE WHENEVER ANY OF THE VALUES USED IN THE CALCULATION CHANGES.

OF COURSE, YOU COULD JUST WRITE `{numberAge * 2}` DIRECTLY AND AVOID USING REACTIVE VARIABLES. REACTIVE VARIABLES BECOME PARTICULARLY VALUABLE WHEN YOU NEED TO REFERENCE THEM MULTIPLE TIMES, OR YOU HAVE VALUES THAT DEPEND ON OTHER REACTIVE VALUES.

## REACTIVE BLOCKS OF CODE

WE ARE NOT LIMITED TO JUST REACTIVE VARIABLES. ENTIRE BLOCKS OF CODE CAN ALSO BE REACTIVE TO ANY CHANGES IN THE USED VARIABLES. FOR THIS, WE MUST DEFINE THE CODE BLOCK WITH `$:{...}`. FOR EXAMPLE:

```svelte
<script>
    let numberCount = 0;

    function functionIncrease() {
        numberCount = numberCount + 1;
    }

    $: {
        console.log(numberCount);
        if (numberCount > 4) {
            alert('COUNT IS DANGEROUSLY HIGH!');
            numberCount = 4;
        }
    }
</script>

<p>{numberCount}</p>
<button on:click={functionIncrease}>
    INCREASE
</button>
```

[RUN CODE](https://svelte.dev/repl/50b4cd9e48c94330802f6be8858c4c99)

THE CODE BLOCK DEFINED BY `$:{...}` WILL BE RE-EXECUTED WHENEVER THERE IS A CHANGE IN THE VARIABLES USED BY THE BLOCK..

[BACK](../README.md)
