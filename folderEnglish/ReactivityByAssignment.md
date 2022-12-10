# REACTIVITY BY ASSIGNMENT

SVELTE REACTIVITY IS CAUSED BY ASSIGNMENT (USING THE "="). METHODS THAT MUTATE ARRAYS OR OBJECTS WILL NOT TRIGGER UPDATES. LET'S UNDERSTAND THE PROBLEM IN THE EXAMPLE BELOW.

IN THE EXAMPLE BELOW, AT EVERY CLICK ON THE "ADD NUMBER" BUTTON, AN ELEMENT IS ADDED INTO THE SEQUENCE OF NUMBERS.

```javascript
<script>
    let arrayNumbers = [1,2,3,4];

    function functionAddNumber(){
        arrayNumbers.push(arrayNumbers.length+1);
    }
</script>

<p>NUMBERS: {arrayNumbers.join(" => ")}</p>

<button on:click={functionAddNumber}>ADD NUMBER</button>
<button on:click={()=>alert(arrayNumbers)}>SHOW ARRAY</button>
```

[RUN THE CODE](https://svelte.dev/repl/511451d9deb04a65bd77d281d1d73380?version=3.54.0)

NOTE (BY CLICKING ON BOTH BUTTONS) THAT, ALTHOUGH THE SEQUENCE IS BEING UPDATED, THE VALUES DISPLAYED ON THE SCREEN ARE NOT UPDATED. THIS HAPPENS BECAUSE THE REACTIVITY OF SVELTE IS CAUSED ONLY IF THE "=" IS USED. AS THE ARRAY IS BEING CHANGED WITHOUT USING "=" (THROUGH THE `push` FUNCTION), THE REACTIVITY DOESN'T HAPPEN, THAT IS, THE UPDATE IS NOT PERCEIVED BY SVELTE.

ONE WAY TO FIX THIS IS WITH `arrayNumbers=arrayNumbers`. THIS WAY WE FORCE THE USE OF "=", SO THAT THE CHANGE IS PERCEIVED BY SVELTE AND THE UPDATE OCCURS. LET'S SEE:

```javascript
<script>
    let arrayNumbers = [1,2,3,4];

    function functionAddNumber(){
        arrayNumbers.push(arrayNumbers.length+1);
        arrayNumbers=arrayNumbers; // THIS LINE FORCES REACTIVITY
    }
</script>

<p>NUMBERS: {arrayNumbers.join(" => ")}</p>

<button on:click={functionAddNumber}>ADD NUMBER</button>
<button on:click={()=>alert(arrayNumbers)}>SHOW ARRAY</button>
```
