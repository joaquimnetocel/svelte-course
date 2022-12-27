# IMPORTING COMPONENTS

WE CAN IMPORT COMPONENTS FROM OTHER FILES AND THEN USE THEM AS THOUGH WE WERE INCLUDING ELEMENTS.

WE NOW PRESENT YOU 2 FILES: `parent.svelte` AND `child.svelte`. LET'S ADD A `<script>` TAG TO `parent.svelte` THAT IMPORTS THE FILE `child.svelte` (OUR COMPONENT).

```svelte
<!-- child.svelte -->
<p>THIS PARAGRAPH IS IN THE <span>CHILD</span> COMPONENT.</p>
<style>
    span {
        color: red;
    }
</style>
```

```svelte
<!-- parent.svelte -->
<script>
    import ComponentChild from "./child.svelte";
</script>

<h3>THIS TITLE IS IN THE <span>PARENT</span> COMPONENT.</h3>

<ComponentChild/>

<style>
    span {
        color: blue;
    }
</style>
```

[RUN CODE](https://svelte.dev/repl/142d924d01ff4390a8d9b466df779f04)

AN IMPORTANT DETAIL IS THAT **THE NAME OF A COMPONENT MUST ALWAYS START WITH A CAPITAL LETTER**. THIS CONVENTION WAS ADOPTED TO ALLOW US TO DIFFERENTIATE BETWEEN USER-DEFINED COMPONENTS AND REGULAR HTML TAGS.

[BACK](../README.md)
