# PROPS

ATÉ AGORA TRATAMOS EXCLUSIVAMENTE DE DADOS QUE SÓ SÃO ACESSÍVEIS DENTRO DE UM DETERMINADO COMPONENTE. AGORA, VAMOS VER COMO PASSAR INFORMAÇÕES DE UM COMPONENTE PAI PARA UM COMPONENTE FILHO. PARA ISSO, PRECISAMOS DECLARAR PROPRIEDADES, GERALMENTE ABREVIADAS COMO 'PROPS'. EM SVELTE, FAZEMOS ISSO COM A PALAVRA CHAVE `export`. ISSO PODE PARECER UM POUCO ESTRANHO NO INÍCIO, POIS NÃO É ASSIM QUE O `export` NORMALMENTE FUNCIONA NOS MÓDULOS JAVASCRIPT! VAMOS A UM EXEMPLO:

```svelte
<!-- filho.svelte -->
<script>
    export let propIdade;
</script>
<p>A IDADE É {propIdade}</p>
```

```svelte
<!--pai.svelte-->
<script>
    import ComponenteFilho from './filho.svelte';
</script>

<ComponenteFilho propIdade={42}/>
<ComponenteFilho propIdade={18}/>
```

[RODAR CÓDIGO](https://svelte.dev/repl/79a01baabc554614afe3bde521af324f)

## DEFAULT VALUES

PODEMOS ESPECIFICAR FACILMENTE VALORES PADRÃO PARA PROPS:

```svelte
<!-- filho.svelte -->
<script>
    export let propIdade=18;
</script>
<p>A IDADE É {propIdade}</p>
```

SE AGORA ADICIONARMOS UM COMPONENTE SEM A PROP, O VALOR PADRÃO SERÁ UTILIZADO:

```svelte
<!--pai.svelte-->
<script>
    import ComponenteFilho from './filho.svelte';
</script>

<ComponenteFilho propIdade={42}/>
<ComponenteFilho/>
```

[RODAR CÓDIGO](https://svelte.dev/repl/321a902da8694385be27ced78dfc2064)