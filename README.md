# Efeito Borboleta

**Ferramentas abertas para gestão de risco de terceiros, feitas no Brasil.**

Uma falha pequena num fornecedor distante vira um incidente grande na sua empresa. É o
efeito borboleta da cadeia de fornecedores, e é por ele que boa parte dos ataques
começa hoje.

Este repositório junta material prático para quem cuida de risco de terceiros (TPRM)
no Brasil: skills de IA, prompts testados, checklists e modelos, pensados para a LGPD e
para as normas brasileiras, não para a regulação americana.

Tudo aqui é gratuito, pode ser usado e adaptado, e aceita contribuições.

## O que tem aqui

| Pasta | O que é | Comece por |
|---|---|---|
| [`skills/`](skills/) | Skills para assistentes de IA (Claude Code e compatíveis) | [Raio-X de Terceiros](skills/raio-x-terceiros/) |
| [`prompts/`](prompts/) | Prompts para TPRM, sempre com a versão ruim, a boa e o porquê | [Análise de evidência de fornecedor](prompts/analise-de-evidencia.md) |
| [`checklists/`](checklists/) | Roteiros curtos para usar no dia a dia | [OSINT em 15 minutos](checklists/osint-15-minutos.md) |
| [`modelos/`](modelos/) | Modelos de documento prontos para preencher | [Uma página para a diretoria](modelos/uma-pagina-para-a-diretoria.md) |
| [`normas/`](normas/) | O que as normas brasileiras pedem sobre terceiros | [Mapa de normas](normas/README.md) |

## Como usar

- **Prompts, checklists, modelos e normas** não precisam de instalação: abra o arquivo,
  copie e use.
- **Skills** se instalam uma vez no seu assistente de IA. No Claude pelo navegador, é
  baixar um ZIP e enviar nas configurações. O passo a passo está em
  [`skills/`](skills/README.md).

## Princípios

1. **Só fonte pública e verificável.** Número sem fonte e ano não entra.
2. **Ético por padrão.** Nada aqui faz varredura ativa, teste de intrusão ou acesso a
   sistema de terceiros sem autorização. Reconhecimento é passivo.
3. **IA com revisão humana.** Os prompts e skills sugerem, a pessoa decide. Nenhum
   material aqui orienta enviar dado confidencial para uma IA sem a política da sua
   empresa permitir.
4. **Português primeiro, linguagem simples.**

## Como contribuir

Leia o [CONTRIBUTING.md](CONTRIBUTING.md). Prompt que funcionou, checklist que você usa,
correção de norma: tudo é bem-vindo.

## Licença

- Código e skills: [MIT](LICENSE).
- Textos, prompts, checklists e modelos: [CC BY 4.0](LICENSE-CONTEUDO.md). Pode usar e
  adaptar, inclusive comercialmente, desde que dê o crédito.

## Mantido por

[Butterfly Security](https://butterflysecurity.com.br), plataforma brasileira de
gestão de segurança e risco de terceiros. O conteúdo deste repositório não depende da
plataforma: tudo funciona sozinho.
