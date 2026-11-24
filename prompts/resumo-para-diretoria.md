# Resumo para a diretoria

**Situação:** a avaliação dos fornecedores está pronta e a diretoria quer saber "como
estamos". Ninguém lá vai ler 30 páginas, nem entender um score sozinho.

## O prompt ruim

```
Faça um resumo executivo da avaliação de fornecedores.
```

**O que dá errado:** sai um texto genérico, cheio de "é importante destacar", sem
número, sem decisão pedida e sem relação com o negócio.

## O prompt bom

```
Você vai escrever uma página para a diretoria sobre o risco de terceiros da empresa.
Quem lê é executivo, não técnico, e tem 3 minutos.

CONTEXTO DO NEGÓCIO
- A empresa: <o que faz, em uma frase>.
- O que mais importa para o negócio agora: <ex.: renovar contrato com grande cliente
  que exige ISO 27001; lançamento de produto; auditoria do regulador em março>.

DADOS DA AVALIAÇÃO
<cole os números: total de fornecedores, quantos críticos, quantos avaliados,
principais lacunas, fornecedores com prazo vencido>

ESTRUTURA (siga exatamente)
1. Uma frase de situação: estamos melhor, igual ou pior do que no último ciclo, e por quê.
2. Os 3 riscos que mais importam, cada um ligado ao contexto do negócio acima.
   Formato: risco, impacto no negócio, o que está sendo feito.
3. Uma decisão que a diretoria precisa tomar, com as opções e a recomendação.
4. 3 números para acompanhar no próximo ciclo.

REGRAS
- Máximo de 350 palavras.
- Use apenas os dados fornecidos. Se faltar algo para um item, escreva
  "[DADO NECESSÁRIO: ...]" em vez de supor.
- Nada de jargão técnico sem tradução. "MFA" vira "segunda etapa de login".
- Nenhum adjetivo sem número que o sustente.
```

## Por que funciona

- **O contexto do negócio é o que transforma score em decisão.** "12 fornecedores com
  lacuna" não move ninguém. "O fornecedor que hospeda os dados do cliente X, cujo
  contrato renova em março, não comprova backup" move.
- **Pedir uma decisão** muda o papel do relatório: deixa de ser prestação de contas e
  vira pauta.
- **"[DADO NECESSÁRIO]"** evita que a IA invente para fechar a estrutura.

Veja também o [modelo de uma página](../modelos/uma-pagina-para-a-diretoria.md).
