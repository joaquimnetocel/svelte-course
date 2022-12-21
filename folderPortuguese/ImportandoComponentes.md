# IMPORTANDO COMPONENTES

PODEMOS IMPORTAR COMPONENTES DE OUTROS ARQUIVOS E DEPOIS USÁ-LOS COMO SE ESTIVESSEMOS INCLUINDO ELEMENTOS.

NO EXEMPLO A SEGUIR, SERÃO UTILIZADOS 2 ARQUIVOS: `pai.svelte` E `filho.svelte`. VAMOS ADICIONAR UMA TAG `<script>` AO `parent.svelte` QUE IMPORTA O ARQUIVO `child.svelte` (NOSSO COMPONENTE).

```svelte
<!-- child.svelte -->
<p>ESTE PARÁGRAFO ESTÁ NO COMPONENTE <span>FILHO</span>.</p>
<style>
    span {
        color: red;
    }
</style>
```

```svelte
<!-- parent.svelte -->
<script>
    import ComponenteFilho from "./filho.svelte";
</script>

<h3>ESTE TÍTULO ESTÁ NO COMPONENTE <span>PAI</span>.</h3>

<ComponenteFilho/>

<style>
    span {
        color: blue;
    }
</style>
```

[RODAR CÓDIGO](https://svelte.dev/repl/3dfd4044eb4a4db4999c2059b222d283?version=3.55.0)

UM DETALHE IMPORTANTE É QUE **O NOME DE UM COMPONENTE DEVE SEMPRE INICIAR COM LETRA MAIÚSCULA**. ESSA CONVENÇÃO FOI ADOTADA PARA NOS PERMITIR DIFERENCIAR ENTRE COMPONENTES DEFINIDOS PELO USUÁRIO E TAGS HTML REGULARES.
