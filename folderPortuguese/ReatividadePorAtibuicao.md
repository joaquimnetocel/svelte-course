# REATIVIDADE POR ATRIBUIÇÃO

A REATIVIDADE DO SVELTE É PROVOCADA POR ATRIBUIÇÃO (USANDO O "="). MÉTODOS QUE ALTERAM ARRAYS OU OBJETOS NÃO ACIONARÃO ATUALIZAÇÕES. VAMOS ENTENDER O PROBLEMA NO EXEMPLO ABAIXO.

NO EXEMPLO ABAIXO, A CADA CLIQUE NO BOTÃO "ADICIONAR NÚMERO" UM ELEMENTO É ADICIONADO NA SEQUÊNCIA DE NÚMEROS.

```svelte
<script>
    let arrayNumeros = [1,2,3,4];

    function funcaoAdicionarNumeros(){
        arrayNumeros.push(arrayNumeros.length+1);
    }
</script>

<p>NÚMEROS: {arrayNumeros.join(" => ")}</p>

<button on:click={funcaoAdicionarNumeros}>ADICIONAR NÚMERO</button>
<button on:click={()=>alert(arrayNumeros)}>MOSTRAR ARRAY</button>
```

[EXECUTAR CÓDIGO ACIMA](https://svelte.dev/repl/09d7607198a44cbf97f57a00cbed937b?version=3.54.0)

REPARE (CLICANDO EM AMBOS OS BOTÕES) QUE, EMBORA A SEQUÊNCIA ESTEJA SENDO ATUALIZADA, OS VALORES EXIBIDOS NA TELA NÃO SÃO ATUALIZADOS. ISSO ACONTECE POIS A REATIVIDADE DO SVELTE É PROVOCADA SOMENTE SE O "=" FOR UTILIZADO. COMO O ARRAY ESTÁ SENDO ALTERADO SEM UTILIZAR "=" EM MOMENTO ALGUMPELA FUNÇÃO (ATRAVÉS DA FUNÇÃO `push`), A REATIVIDADE NÃO ACONTECE, OU SEJA, A ALTERAÇÃO NÃO É PERCEBIDA PELO SVELTE.

UMA MANEIRA DE CORRIGIR ISSO, É COM `arrayNumeros=arrayNumeros`. DESTA FORMA FORÇAMOS A UTILIZAÇÃO DO "=" PARA QUE A ALTERAÇÃO SEJA PERCEBIDA PELO SVELTE E A ATUALIZAÇÃO OCORRA. VEJAMOS:

```svelte
<script>
    let arrayNumeros = [1,2,3,4];

    function funcaoAdicionarNumeros(){
        arrayNumeros.push(arrayNumeros.length+1);
        arrayNumeros=arrayNumeros; // ESTA LINHA FORÇA A REATIVIDADE
    }
</script>

<p>NÚMEROS: {arrayNumeros.join(" => ")}</p>

<button on:click={funcaoAdicionarNumeros}>ADICIONAR NÚMERO</button>
<button on:click={()=>alert(arrayNumeros)}>MOSTRAR ARRAY</button>
```

[RODAR O CÓDIGO](https://svelte.dev/repl/7a76e9e027aa4c2c9b0a86f48a053fa7?version=3.54.0)

[VOLTAR](../LEIAME.md)
