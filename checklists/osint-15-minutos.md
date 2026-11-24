# OSINT de fornecedor em 15 minutos

Atacantes escolhem a porta mais fácil, e muitas vezes ela é um fornecedor. Este roteiro
mostra o que qualquer pessoa consegue ver sobre uma empresa **sem tocar nos sistemas
dela**. Use para preparar a avaliação de um fornecedor e fazer perguntas melhores.

## Antes de começar: as regras

- **Só reconhecimento passivo.** Você consulta bases públicas e índices de terceiros.
  Não faz varredura de portas, não testa senha, não tenta login, não explora nada.
- **Só empresas com as quais você tem relação legítima** (fornecedor atual ou em
  avaliação, ou a sua própria empresa).
- **Achou credencial, dado pessoal ou documento interno exposto? Não use, não baixe,
  não compartilhe.** Anote onde está e avise o fornecedor por um canal oficial.
- **Registre** data, fonte e o que viu. É isso que vira pergunta no questionário.

Acesso não autorizado a sistema é crime no Brasil (Código Penal, art. 154-A). Este
roteiro não chega perto disso, e não deve ser adaptado para chegar.

## O roteiro

### 1. O que a empresa declara (2 min)

- [ ] Existe página de segurança, privacidade ou *trust center*?
- [ ] Ela cita certificações (ISO/IEC 27001, SOC 2)? Com escopo e validade?
- [ ] Existe `https://<domínio>/.well-known/security.txt` com um canal para relatar
      vulnerabilidade?

*O que isso diz:* maturidade declarada e se há um caminho para avisar de um problema.

### 2. E-mail: dá para se passar por eles? (3 min)

Consulte os registros públicos de DNS do domínio (qualquer verificador online de SPF e
DMARC serve, ou `dig TXT _dmarc.<domínio>` no terminal).

- [ ] Tem **SPF**?
- [ ] Tem **DMARC**? Com qual política: `none` (só observa), `quarantine` ou `reject`?

*O que isso diz:* sem DMARC em `quarantine` ou `reject`, fica mais fácil mandar e-mail
falso em nome do fornecedor, inclusive para você. É a base de muita fraude de boleto e
troca de dados bancários.

### 3. Superfície exposta (4 min)

- [ ] **Subdomínios** nos registros públicos de certificados (Certificate Transparency,
      por exemplo em crt.sh). Procure nomes como `vpn`, `homolog`, `dev`, `teste`,
      `admin`, `old`.
- [ ] **Serviços indexados** em buscadores de dispositivos (como Shodan ou Censys),
      buscando pelo domínio ou pela organização. Você lê o índice, não varre nada.
- [ ] **Domínios parecidos** registrados por terceiros (troca de letra, hífen, outro
      TLD), que podem servir para phishing.

*O que isso diz:* ambiente de teste exposto e painel administrativo público são portas
de entrada clássicas.

### 4. O que vaza sem querer (3 min)

- [ ] **Vagas de emprego**: revelam a pilha de tecnologia (sistemas, nuvem, VPN) e o
      tamanho do time de segurança.
- [ ] **Repositórios públicos** de código da empresa ou de funcionários citando o
      domínio. Só observe se existem; não abra arquivos de configuração alheios.
- [ ] **Documentos indexados** em buscadores (`site:<domínio> filetype:pdf`): manuais,
      apresentações, planilhas que não deveriam ser públicas.

*O que isso diz:* quanto o atacante consegue saber antes de mandar o primeiro e-mail.

### 5. Histórico (3 min)

- [ ] **Notícias** com o nome da empresa e "vazamento", "incidente", "ataque",
      "ransomware".
- [ ] **Agregadores públicos de incidentes de ransomware**, que noticiam as vítimas
      anunciadas pelos grupos. Nunca acesse os sites dos próprios grupos.
- [ ] **Comunicados oficiais** da empresa ou da ANPD sobre incidentes.

*O que isso diz:* se houve incidente, o que a empresa comunicou e o que mudou depois.
Anúncio de grupo criminoso é **alegação**, não fato confirmado.

## Do achado à pergunta

O objetivo não é dar nota ao fornecedor. É fazer perguntas que um questionário genérico
não faria.

| Se você viu | Pergunte |
|---|---|
| DMARC ausente ou em `none` | "Qual o plano para publicar DMARC com política de bloqueio?" |
| Subdomínio `homolog` ou `dev` exposto | "Ambientes de teste usam dados reais? Como o acesso é restrito?" |
| Vaga citando VPN sem segunda etapa de login | "Todo acesso remoto exige MFA, inclusive de terceiros de vocês?" |
| Incidente noticiado | "O que mudou nos controles depois do incidente de <data>?" |
| Sem `security.txt` nem canal de segurança | "Como um pesquisador ou cliente reporta uma vulnerabilidade?" |

## Limites

Este roteiro mostra a superfície, não a segurança real. Um fornecedor com tudo em ordem
aqui pode ter problemas sérios por dentro, e o contrário também acontece. Use como ponto
de partida da conversa, nunca como veredito.
