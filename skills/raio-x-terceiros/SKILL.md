---
name: raio-x-terceiros
description: Gera o "Raio-X de Terceiros", um dossiê em Markdown sobre como o risco de terceiros aparece no setor de uma empresa: posição dela na cadeia de fornecedores, normas brasileiras que a pressionam e incidentes públicos envolvendo terceiros no Brasil e no mundo, com cada afirmação ligada à fonte. Não faz análise técnica do domínio. Use quando pedirem "raio-x de terceiros", "dossiê de terceiros", "estudo de setor para TPRM" ou "como está o risco de fornecedores do setor da empresa X".
---

# Raio-X de Terceiros

Dossiê curto que mostra, para uma empresa específica, **como o risco de terceiros aparece
no setor dela**. Quem lê deve terminar entendendo três coisas: onde a empresa está na
cadeia de fornecedores, o que já aconteceu com empresas parecidas, e por onde começar.

Parte do projeto aberto [Efeito Borboleta](https://github.com/btf-security/efeito-borboleta).

## Limites (não negocie)

- **Nada de análise técnica do domínio**: nem DNS, nem portas, nem certificados, nem
  cabeçalhos, nem busca de credenciais vazadas da empresa. Se o usuário pedir, explique
  que o Raio-X é pesquisa de setor e indique o checklist de OSINT do projeto, lembrando
  que só deve ser aplicado com relação legítima com a empresa.
- **Nada de conhecimento não público.** O que o usuário contar sobre a empresa entra só
  como contexto da conversa, nunca como fato no dossiê.
- **Nunca ligue a empresa a um incidente que não é dela.** O caso de um concorrente
  mostra o risco do setor; não sugira que a empresa tem a mesma falha.

## Entradas

Pergunte só o que faltar. Obrigatório: **nome e site** da empresa.
Opcional: setor e porte, e o contexto (é um fornecedor sendo avaliado? um cliente? a
própria empresa do usuário?). O contexto muda o ângulo do texto.

## Passo a passo

1. **Pasta de saída.** Crie `raio-x-saida/<slug-da-empresa>/` no diretório atual. Se o
   ambiente não permitir criar arquivos, entregue os três conteúdos na própria conversa,
   em blocos separados e na mesma ordem.

2. **Pesquisa pública** (busca e leitura na web), anotada em `pesquisa.md` com URL e data
   de acesso de cada item:
   - **A empresa:** o que faz, modelo de negócio, porte, clientes que ela mesma cita, o
     que a página de segurança ou privacidade declara (escreva sempre "declara", nunca "tem").
   - **A cadeia:** quem avalia a empresa (clientes grandes, bancos, reguladores) e de que
     tipos de fornecedor um negócio assim depende. Fale em **categorias** (folha de
     pagamento, nuvem, atendimento), nunca em fornecedores com nome inferido.
   - **O setor:** normas aplicáveis (comece por `references/normas-por-setor.md` e
     **confirme a vigência na fonte oficial**) e números de mercado com fonte primária.
   - **Incidentes com terceiros**, nesta ordem: (a) em fornecedores do mesmo tipo da
     empresa, quando ela é fornecedora de alguém; (b) no setor da empresa; (c) os grandes
     casos de cadeia de suprimentos dos últimos dois anos. Meta: 3 a 4 casos no mundo e
     2 a 3 no Brasil. Para cada um: quando, empresa afetada, terceiro envolvido, vetor,
     impacto **segundo a fonte** e a lição. Se não houver caso público no Brasil do mesmo
     tipo, diga isso: é um dado, não um buraco.

3. **Leitura dos dados.** Antes de escrever, responda para si:
   - A empresa é **contratante**, **fornecedora** ou **ambos**? Isso define a narrativa.
   - Que **padrões** os incidentes mostram? No máximo três, cada um ancorado em casos
     citados (exemplos: "o dado vaza no fornecedor e a manchete é do cliente";
     "credencial legítima de terceiro"; "integração entre sistemas SaaS").
   - O que a empresa **já faz bem**, segundo ela mesma declara?

4. **Rastreabilidade.** Antes do dossiê, escreva `rastreabilidade.md`: uma linha por
   afirmação que vai para o texto, com a classe e a prova:
   - **FATO PÚBLICO**: URL da fonte (site da empresa, norma, imprensa, relatório).
   - **ALEGAÇÃO**: o que só uma parte interessada afirma (por exemplo, um grupo
     criminoso). Só entra rotulada: "o grupo afirma".
   - **RECOMENDAÇÃO**: opinião assumida. Só aparece na seção de recomendações.
   Afirmação que não cabe em nenhuma das três **sai do texto**.

5. **Escrever `raio-x.md`** seguindo `references/modelo-de-saida.md`, nas 7 seções:
   1. Resumo (4 números com fonte, o que a empresa já faz, frase-síntese)
   2. A empresa na cadeia (quem avalia a empresa, de quem ela depende, normas)
   3. Incidentes no mundo
   4. Incidentes no Brasil
   5. O padrão (os até 3 padrões e as perguntas que o mercado passou a fazer)
   6. Por onde começar (5 recomendações de governança e processo, em ordem)
   7. Metodologia e fontes (o que foi feito, limitações, lista de fontes)

6. **Revisão.** Releia o dossiê contra a `rastreabilidade.md`. Toda frase com fato
   precisa ter linha correspondente. Depois, informe ao usuário os caminhos dos arquivos
   e um resumo de 5 linhas: o ângulo, os 3 achados mais fortes e uma pergunta para abrir
   a conversa com a empresa.

## Regra de ouro: só certezas

- **Número só com origem e ano.** Cite o relatório e a edição. Número que só aparece em
  blog, sem fonte primária ou veículo sério confirmando, não entra.
- **Imprensa com "segundo a imprensa"** ou "segundo a empresa". Se as fontes divergem em
  valor ou data, use o valor mais recente confirmado pela empresa ou pela autoridade, e
  diga "ao menos".
- **Alegação de criminoso é alegação.** "O grupo afirma ter levado X" nunca vira "X vazou".
- **Norma ou decisão judicial em curso:** diga o estado na data da pesquisa.
- **Dado de empresa** (clientes, receita, funcionários) só se vier dela mesma ou de fonte
  recente.
- **Na dúvida, corte.**

## Tom e escrita

- Tom de parceiro, nunca de auditor: "o que o setor está vivendo", não "seus riscos".
  Comece pelo que a empresa já faz bem.
- Português do Brasil, frases curtas, linguagem de diretoria.
- Não estime multa em reais sem porte e faturamento com fonte.
- O dossiê fala de uma empresa real: trate como documento reservado. Não publique sem o
  consentimento dela.
