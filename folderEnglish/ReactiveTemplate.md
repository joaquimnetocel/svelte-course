# REACTIVE TEMPLATE

AT THE HEART OF SVELTE IS A POWERFUL SYSTEM OF REACTIVITY FOR KEEPING YOUR PAGE IN SYNC WITH YOUR APPLICATION STATES. TO DEMONSTRATE IT, LET'S PROPOSE BUTTONS TO INCREMENT/DECREMENT THE VALUE OF A VARIABLE:

```svelte
<script>
let stateAge = 20;

function functionIncrease(){
    stateAge = stateAge+1;
}
function functionDecrease(){
    stateAge = stateAge-1;
}
</script>

<p>MY AGE IS {stateAge}<p>
<p><button on:click={functionIncrease}>INCREASE</button></p>
<p><button on:click={functionDecrease}>DECREASE</button></p>
```

[RUN CODE](https://svelte.dev/repl/d27135f25ed349118d0bf44ecef9d4a5)

[BACK](../README.md)
