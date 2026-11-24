# Triagem de questionário

**Situação:** um fornecedor devolveu um questionário com 120 respostas. Você tem meia
hora e precisa saber onde olhar primeiro.

## O prompt ruim

```
Resuma esse questionário.
```

**O que dá errado:** o resumo repete o que o fornecedor disse, com o mesmo otimismo.
Você não fica sabendo o que é risco, o que é inconsistência e o que está faltando.

## O prompt bom

```
Você é analista de risco de terceiros fazendo a triagem de um questionário de
segurança respondido por um fornecedor.

CONTEXTO
- O fornecedor presta <serviço> e tem acesso a <tipo de dado ou sistema>.
- Criticidade: <ALTA | MÉDIA | BAIXA>.

TAREFA
Leia todas as respostas e liste apenas o que precisa de atenção humana, em 4 grupos:

1. RESPOSTA NEGATIVA OU PARCIAL em controle importante para este serviço.
2. INCONSISTÊNCIA: duas respostas que se contradizem (ex.: "não usamos nuvem" e
   "backup na AWS"). Cite os números das duas perguntas.
3. "SIM" SEM EVIDÊNCIA em controle crítico (acesso, criptografia, incidente, backup,
   subcontratados).
4. RESPOSTA VAGA: texto que não responde à pergunta ("seguimos as melhores práticas").

REGRAS
- Cite sempre o número da pergunta.
- Não liste o que está bem respondido.
- Não invente risco: se o questionário não fala de um tema, coloque o tema numa lista
  final chamada "NÃO PERGUNTADO", sem julgar.

SAÍDA
Uma tabela por grupo: Pergunta nº | O que foi respondido | Por que chama atenção.
No fim, as 5 perguntas de acompanhamento mais importantes para mandar ao fornecedor.
```

## Por que funciona

- **Os 4 grupos são o critério.** A IA para de resumir e passa a filtrar.
- **Inconsistência** é onde a IA mais ajuda: cruzar 120 respostas é cansativo para uma
  pessoa e trivial para a IA.
- **"Não liste o que está bem"** corta 80% do texto inútil.
- **"NÃO PERGUNTADO"** separa lacuna do questionário de falha do fornecedor.
