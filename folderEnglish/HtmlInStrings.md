# HTML IN STRINGS

## ENTENDENDO O PROBLEMA

IF A STRING CONTAINS HTML CODE, THIS CODE WILL NOT BE PROCESSED WHEN INSERTING THE STRING INTO THE TEMPLATE. LET'S SEE THE EXAMPLE:

```svelte
<script>
const stringHtml = "<p>HELLO <strong>JOHN</strong></p>"
</script>

{stringHtml}
```

[RODAR CÓDIGO](https://svelte.dev/repl/563e8c44a25b40ab9b9de17e9f36a29d)

## THE SOLUTION

HTML CODE CAN BE INSERTED WITH `{@html ...}`. EXAMPLE:

```svelte
<script>
const stringHtml = "<p>HELLO <strong>JOHN</strong></p>"
</script>

{@html stringHtml}
```

[RODAR CÓDIGO](https://svelte.dev/repl/4a16c2da68464054804c144295e2bb61)

[BACK](../README.md)
