# Análise de evidência de fornecedor

**Situação:** o fornecedor respondeu "sim" para "Vocês fazem backup criptografado com
teste de restauração?" e anexou um PDF de 40 páginas. Você precisa saber se o PDF prova
a resposta.

## O prompt ruim

```
Analise esse documento e me diga se o fornecedor é seguro.
```

**O que dá errado:**

- "Seguro" não é critério. A IA vai elogiar o documento.
- Não diz qual pergunta o documento deveria provar.
- Não pede citação, então você não consegue conferir.
- Não dá saída para "não está no documento". A IA tende a deduzir e completar.

## O prompt bom

```
Você é analista de risco de terceiros e revisa evidências enviadas por fornecedores.

CONTEXTO
- Fornecedor: processa a folha de pagamento da nossa empresa. Criticidade ALTA
  (acessa dados pessoais de todos os funcionários).
- Pergunta do questionário: "Vocês fazem backup criptografado com teste de
  restauração?"
- Resposta do fornecedor: "Sim".
- Documento anexo: política de backup (PDF).

CRITÉRIO
A resposta só está COMPROVADA se o documento mostrar os três itens:
1. backup com criptografia (algoritmo ou padrão citado);
2. teste de restauração com periodicidade definida;
3. data de vigência ou de revisão do documento nos últimos 12 meses.

REGRAS
- Use somente o documento. Não use conhecimento geral sobre o fornecedor.
- Para cada item, cite o trecho exato e a página.
- Se o item não estiver no documento, escreva SEM EVIDÊNCIA. Não deduza.
- Política ("devemos fazer") não é registro ("fizemos em março"). Diga qual dos dois é.

SAÍDA
Tabela com as colunas: Item | Status (COMPROVADO, PARCIAL, SEM EVIDÊNCIA) |
Trecho e página | Política ou registro.
Depois, um veredito de uma linha e no máximo 3 perguntas para mandar ao fornecedor.
```

## Por que funciona

| Elemento | Onde está |
|---|---|
| Papel | "analista de risco de terceiros" |
| Contexto | fornecedor, criticidade, pergunta e resposta |
| Critério | os três itens explícitos |
| Saída de emergência | "SEM EVIDÊNCIA. Não deduza." |
| Citação | "trecho exato e a página" |
| Formato | tabela fixa + veredito + perguntas |

O detalhe que mais faz diferença na prática: **política não é registro**. Um documento
que diz que o backup "deve ser testado" não prova que foi testado. Pedir essa distinção
explícita evita a maioria dos falsos "comprovado".

## Variações

- Troque a pergunta e os três itens do critério para qualquer controle.
- Para comparar vários fornecedores, mantenha a mesma tabela de saída em todos.
