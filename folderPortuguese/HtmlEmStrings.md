# HTML EM STRINGS

## ENTENDENDO O PROBLEMA

CASO UMA STRING CONTENHA CÓDIGO HTML, ESTE CÓDIGO NÃO SERÁ PROCESSADO AO INSERIR A STRING NO TEMPLATE. VEJA O EXEMPLO:

```svelte
<script>
const stringHtml = "<p>OLÁ <strong>JOAQUIM</strong></p>"
</script>

{stringHtml}
```

[RODAR CÓDIGO](https://svelte.dev/repl/bf5643c8da66426e90ddb1c54824055b)

## A SOLUÇÃO

CÓDIGO HTML PODE SER INSERIDO NO TEMPLATE COM `{@html ...}`. VEJA O EXEMPLO:

```svelte
<script>
const stringHtml = "<p>OLÁ <strong>JOAQUIM</strong></p>"
</script>

{@html stringHtml}
```

[RODAR CÓDIGO](https://svelte.dev/repl/c0299e1f0ba542bcb31d69d5c2e136e6)

[BACK](../LEIAME.md)
