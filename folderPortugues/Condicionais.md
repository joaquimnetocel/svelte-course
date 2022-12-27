# CONDICIONAIS

O HTML NÃO TEM UMA FORMA DE EXPRESSAR LÓGICA, COMO CONDICIONAIS E LOOPS. JÁ O SVELTE TEM.

## IF

PARA EXIBIR CONTEÚDOS CONDICIONALMENTE NO TEMPLATE, PODEMOS ENVOLVÊ-LO EM UM BLOCO IF. VEJA O EXEMPLO:

```svelte
<script>
    let numeroContador = 0;
    function funcaoAumentar() {
        numeroContador = numeroContador + 1;
    }
    function funcaoDiminuir() {
        numeroContador = numeroContador - 1;
    }
</script>

<p>NÚMERO: {numeroContador}</p>
<p>
    <button on:click={funcaoDiminuir}>DIMINUIR</button>
    <button on:click={funcaoAumentar}>AUMENTAR</button>
</p>
{#if numeroContador >= 0 }
    <p>NÃO É UM NÚMERO NEGATIVO.</p>
{/if}
{#if numeroContador < 0}
    <p>É UM NÚMERO NEGATIVO.</p>
{/if}
```

[RUN CODE](https://svelte.dev/repl/88b726e348434ff38f7815e59aad72b7)

## ELSE

TAMBÉM PODEMOS UTILIZAR UM BLOCO ELSE. EXEMPLO:

```svelte
<script>
    let numeroContador = 0;
    function funcaoAumentar() {
        numeroContador = numeroContador + 1;
    }
    function funcaoDiminuir() {
        numeroContador = numeroContador - 1;
    }
</script>

<p>NÚMERO: {numeroContador}</p>
<p>
    <button on:click={funcaoDiminuir}>DIMINUIR</button>
    <button on:click={funcaoAumentar}>AUMENTAR</button>
</p>
{#if numeroContador >= 0 }
    <p>NÃO É UM NÚMERO NEGATIVO.</p>
{:else}
    <p>É UM NÚMERO NEGATIVO.</p>
{/if}
```

[RUN CODE](https://svelte.dev/repl/1592415cd48d48d2819c0f53ac9e9fc1)

UM CARACTER `#` SEMPRE INDICA UMA TAG DE ABERTURA DE BLOCO. UM CARACTER `/` SEMPRE INDICA UMA TAG DE FECHAMENTO DE BLOCO. UM CARACTER `:`, COMO EM `{:ELSE}`, INDICA UMA MARCA DE CONTINUAÇÃO DE BLOCO.

## ELSE IF

MULTIPLAS CONDIÇÕES PODEM SER ENCADEADAS COM ELSE IF:

```svelte
<script>
    let numeroContador = 0;
    function funcaoAumentar() {
        numeroContador = numeroContador + 1;
    }
    function funcaoDiminuir() {
        numeroContador = numeroContador - 1;
    }
</script>

<p>NÚMERO: {numeroContador}</p>
<p>
    <button on:click={funcaoDiminuir}>DIMINUIR</button>
    <button on:click={funcaoAumentar}>AUMENTAR</button>
</p>
{#if numeroContador > 0 }
    <p>É UM NÚMERO POSITIVO.</p>
{:else if numeroContador === 0}
    <p>O NÚMERO É IGUAL A ZERO.</p>
{:else}
    <p>É UM NÚMERO NEGATIVO.</p>
{/if}
```

[RODAR CÓDIGO](https://svelte.dev/repl/212cc415000a41799dcb83431549d43a)

[VOLTAR](../LEIAME.md)
