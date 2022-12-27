# TEMPLATE REATIVO

NO CORAÇÃO DO SVELTE ESTÁ UM PODEROSO SISTEMA DE REATIVIDADE PARA MANTER SUA PÁGINA SINCRONIZADA COM SEUS ESTADOS DE APLICATIVO. PARA DEMONSTRAR ISSO, VAMOS PROPOR BOTÕES PARA AUMENTAR/DIMINUIR O VALOR DE UMA VARIÁVEL:

```svelte
<script>
let numeroIdade = 20;

function funcaoAumentar(){
    numeroIdade = numeroIdade+1;
}
function funcaoDiminuir(){
    numeroIdade = numeroIdade-1;
}
</script>

<p>MINHA IDADE É {numeroIdade}<p>
<p><button on:click={funcaoAumentar}>AUMENTAR</button></p>
<p><button on:click={funcaoDiminuir}>DIMINUIR</button></p>
```

[RODAR CÓDIGO](https://svelte.dev/repl/999f20202fb44c8cb694848e6d4bd5f5)

[VOLTAR](../LEIAME.md)
