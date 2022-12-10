# COMPONENTS

MODERN WEB DEVELOPMENT IS VERY MUCH FOCUSED ON COMPONENTS, AND SVELTE IS NO DIFFERENT.

WHAT IS A COMPONENT? A COMPONENT IS A PART OF THE APPLICATION. IN OTHER WORDS, COMPONENTS CONTAIN EVERYTHING NEEDED TO REPRESENT A PART OF THE USER INTERFACE. EACH SVELTE COMPONENT IS DECLARED IN A `.svelte` FILE. IN THESE FILES YOU WILL FIND THE CONTENT (HTML), THE FORMATTING (CSS) AND THE CODE (JAVASCRIPT).

LET'S SEE THE EXAMPLE OF A COMPONENT IN SVELTE:

```svelte
<script>
const stringSize = "SMALL";
</script>

<p>THE HOUSE IS {stringSize} AND <span class="classColor">RED</span>.</p>

<style>
    .classColor {
        color: red;
    }
</style>
```

[RUN THE CODE](https://svelte.dev/repl/8317951f7e3f45b7b5d908ed6134d710?version=3.54.0)

EXCEPT IF DELIBERATELY SPECIFIED, THE CSS AND THE JAVASCRIPT DEFINED ARE INTERNAL TO THE COMPONENT AND DO NOT "LEAK" OUTSIDE. IN OTHER WORDS, GENERALLY, THE CSS AND JAVASCRIPT DEFINED IN A COMPONENT DOES NOT AFFECT OTHER COMPONENTS. LATER WE WILL SEE THAT IT IS POSSIBLE TO DELIBERATELY PROMOTE THE EXCHANGE OF INFORMATION BETWEEN COMPONENTS.

[BACK](../README.md)