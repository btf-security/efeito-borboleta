# Raio-X de Terceiros

Gera um dossiê sobre **como o risco de terceiros aparece no setor de uma empresa**: em
que posição ela está na cadeia de fornecedores, que normas a pressionam e que incidentes
com terceiros já aconteceram com empresas parecidas, no Brasil e no mundo.

Serve para:

- preparar uma reunião com um fornecedor ou um cliente;
- justificar para a diretoria por que o programa de terceiros existe;
- entender um setor novo antes de avaliar fornecedores dele.

## O que ela não faz

**Nenhuma análise técnica do domínio da empresa.** Nada de DNS, portas, certificados ou
cabeçalhos. O Raio-X é pesquisa de setor e de incidentes públicos. Para o olhar técnico
passivo, veja o [checklist de OSINT](../../checklists/osint-15-minutos.md), e só aplique
em empresas com as quais você tem relação.

## Como usar

Depois de [instalar](../README.md) (no Claude pelo navegador, no Claude Code ou colando
em outro assistente), peça:

> Faça um raio-x de terceiros da Empresa Exemplo, site exemplo.com.br. Contexto: é um
> fornecedor de folha de pagamento que estamos avaliando.

Saída, numa pasta `raio-x-saida/<empresa>/`:

| Arquivo | O que é |
|---|---|
| `raio-x.md` | O dossiê, em 7 seções |
| `rastreabilidade.md` | Cada afirmação do dossiê com a classe (fato, alegação, recomendação) e a fonte |
| `pesquisa.md` | Anotações brutas da pesquisa, com URL e data de acesso |

Leia a `rastreabilidade.md` antes de mandar o dossiê para alguém. É ela que garante que
nada foi inventado.

## Regra de ouro

Um dossiê menor e 100% correto vale mais do que um completo com um erro. Na dúvida, a
skill corta.
