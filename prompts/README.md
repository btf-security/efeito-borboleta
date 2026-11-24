# Prompts para TPRM

Cada arquivo traz um prompt **ruim**, um **bom** e o **porquê** da diferença. A ideia é
aprender o padrão, não só copiar o texto.

| Prompt | Para quê |
|---|---|
| [Análise de evidência](analise-de-evidencia.md) | Conferir se o documento do fornecedor prova o que ele respondeu |
| [Triagem de questionário](triagem-de-questionario.md) | Achar, em dezenas de respostas, onde olhar primeiro |
| [Resumo para a diretoria](resumo-para-diretoria.md) | Transformar a avaliação em uma página que o board lê |

## Os 6 elementos de um bom prompt de TPRM

1. **Papel:** quem a IA é ("analista de risco de terceiros").
2. **Contexto:** quem é o fornecedor, o que ele faz para você, a criticidade.
3. **Critério:** o que conta como prova, explícito. Sem critério, a IA usa o dela.
4. **Saída:** formato fixo (tabela, JSON). Facilita comparar fornecedores.
5. **Saída de emergência:** "se não houver evidência, responda SEM EVIDÊNCIA". Sem isso,
   a IA preenche o buraco com algo plausível.
6. **Citação:** cada conclusão aponta o trecho e a página do documento.

## Antes de colar qualquer coisa

- **Confira a política de IA da sua empresa.** Documento de fornecedor costuma ter
  cláusula de confidencialidade.
- **Prefira ferramentas corporativas** com contrato que proíba treinar com seus dados.
- **Tire dado pessoal** que não for necessário para a análise.
- **A IA sugere, você decide.** Nenhuma resposta dela vai para o fornecedor ou para o
  relatório sem revisão humana.
