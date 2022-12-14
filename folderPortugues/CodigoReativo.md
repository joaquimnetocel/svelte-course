# CÓDIGO REATIVO

## ENTENDENDO O PROBLEMA

ALÉM DE MANTER O TEMPLATE EM SINCRONIA COM AS VARIÁVEIS (COMO VIMOS NA SEÇÃO ANTERIOR), A REATIVIDADE DO SVELTE É CAPAZ DE MANTER AS VARIÁVEIS EM SINCRONIA COM OUTRAS VARIÁVEIS. MAS ANTES, VAMOS ENTENDER O PROBLEMA E PERCEBER QUE ISSO NÃO É ALGO REALIZADO AUTOMATICAMENTE. O EXEMPLO A SEGUIR ILUSTRA O PROBLEMA:

```svelte
<script>
let numeroIdade = 20;
let numeroDobroDaIdade = 2*numeroIdade;
function funcaoAumentarIdade() {
    numeroIdade += 1;
}
</script>

<p>A IDADE É {numeroIdade} E O SEU DOBRO É {numeroDobroDaIdade}.</p>
<button on:click={funcaoAumentarIdade}>AUMENTAR</button>
```

[RODAR CÓDIGO](https://svelte.dev/repl/cd95e787b7dd424493d8bc9e14f4ddfb)

COMO PODEMOS VER NO EXEMPLO ACIMA, AO CLICAR NO BOTÃO, APENAS A VARIÁVEL 'numeroIdade' É ALTERADA E A 'numeroDobroDaIdade' NÃO É RECALCULADA.

## VARIÁVEIS REATIVAS

PARA TORNAR UMA VARIÁVEL REATIVA, PODEMOS FAZER O SEGUINTE:

```svelte
<script>
let numeroIdade = 20;
$: numeroDobroDaIdade = 2*numeroIdade;

function funcaoAumentarIdade() {
    numeroIdade += 1;
}
</script>

<p>A IDADE É {numeroIdade} E SEU DOBRO É {numeroDobroDaIdade}.</p>
<button on:click={funcaoAumentarIdade}>AUMENTAR</button>
```

[RODAR CÓDIGO](https://svelte.dev/repl/3306eaba32064d609c20737a332266af)

AQUI, O `$` DIZ AO SVELTE PARA RECALCULAR A VARIÁVEL SEMPRE QUE QUALQUER UM DOS VALORES UTILIZADOS NO CÁLCULO MUDAR.

É CLARO QUE VOCÊ PODE ESCREVER `{numeroIdade * 2}` DIRETO NO TEMPLATE E EVITAR USAR VARIÁVEIS REATIVAS. VARIÁVEIS REATIVAS TORNAM-SE PARTICULARMENTE VALIOSAS QUANDO VOCÊ PRECISA REFERENCIÁ-LAS VÁRIAS VEZES OU QUANDO VOCÊ TEM VALORES QUE DEPENDEM DE OUTROS VALORES REATIVOS.

## BLOCOS DE CÓDIGO REATIVOS

NÃO ESTAMOS LIMITADOS APENAS A VARIÁVEIS REATIVAS. BLOCOS INTEIROS DE CÓDIGO TAMBÉM PODEM SER REATIVOS À QUALQUER MUDANÇA NAS VARIÁVEIS UTILIZADAS. PARA ISTO, IREMOS DEFINIR O BLOCO DE CÓDIGOS COM `$:{...}`. POR EXEMPLO:

```svelte
<script>
    let numeroContador = 0;

    function funcaoAumentar() {
        numeroContador = numeroContador + 1;
    }

    $: {
        console.log(numeroContador);
        if (numeroContador > 4) {
            alert('O CONTADOR ESTÁ PERIGOSAMENTE ALTO!');
            numeroContador = 4;
        }
    }
</script>

<p>{numeroContador}</p>
<button on:click={funcaoAumentar}>
    AUMENTAR
</button>
```

[RODAR CÓDIGO](https://svelte.dev/repl/67375e933ec64e6ba3ff65732c3001b3)

O BLOCO DE CÓDIGOS DEFINIDO POR `$:{...}` SERÁ REEXECUTADO SEMPRE QUE HOUVER UMA MUDANÇA NAS VARIÁVEIS UTILIZADAS PELO BLOCO.

[VOLTAR](../LEIAME.md)
