# PROPERTIES (PROPS)

UNTIL NOW, WE HAVE DEALT EXCLUSIVELY WITH DATA WHICH IS ONLY ACCESSIBLE WITHIN A PARTICULAR COMPONENT. NOW, LET'S SEE HOW TO PASS INFORMATION FROM A PARENT COMPONENT TO A CHILD COMPONENT. TO DO THIS, WE NEED TO DECLARE PROPERTIES, USUALLY ABBREVIATED AS 'PROPS'. IN SVELTE, WE DO THIS WITH THE KEYWORD `export`. THIS MIGHT SEEM A LITTLE STRANGE AT FIRST, BECAUSE THIS IS NOT HOW `export` NORMALLY WORKS IN JAVASCRIPT MODULES! LET'S SEE AN EXAMPLE:

```svelte
<!-- child.svelte -->
<script>
    export let propAge;
</script>
<p>THE AGE IS {propAge}</p>
```

```svelte
<!--parent.svelte-->
<script>
    import ComponentChild from './child.svelte';
</script>

<ComponentChild propAge={42}/>
<ComponentChild propAge={18}/>
```

[RUN CODE](https://svelte.dev/repl/acaf5fbbe81942efae60fe55e9b23fce)

## DEFAULT VALUES

WE CAN EASILY SPECIFY DEFAULT VALUES FOR PROPS:

```svelte
<!-- child.svelte -->
<script>
    export let propAge = 18;
</script>
<p>THE AGE IS {propAge}</p>
```

IF WE NOW ADD A COMPONENT WITHOUT THE PROP, IT WILL FALL BACK TO THE DEFAULT:

```svelte
<!--parent.svelte-->
<script>
    import ComponentChild from './child.svelte';
</script>

<ComponentChild propAge={42}/>
<ComponentChild/>
```

[RUN CODE](https://svelte.dev/repl/019b65ccc11d4619ac5a8dba8308e5ea)

[BACK](../README.md)
