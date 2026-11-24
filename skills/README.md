# Skills

Skills são pacotes de instruções que ensinam um assistente de IA a fazer uma tarefa do
jeito certo, sempre igual. Você instala uma vez e depois só pede, em linguagem normal.

| Skill | O que faz | Baixar |
|---|---|---|
| [raio-x-terceiros](raio-x-terceiros/) | Dossiê de setor e incidentes com terceiros para uma empresa, com cada afirmação ligada à fonte | [raio-x-terceiros.zip](https://github.com/btf-security/efeito-borboleta/releases/latest/download/raio-x-terceiros.zip) |

Escolha o caminho que combina com você.

## 1. No Claude (navegador ou app): o mais simples

Funciona nos planos pagos do Claude (Pro, Max, Team e Enterprise). Confira a
disponibilidade do seu plano na [central de ajuda do Claude](https://support.claude.com/en/articles/12512180-use-skills-in-claude).

1. **Baixe o ZIP** da skill pelo link da tabela acima. Não descompacte.
2. No Claude, abra **Configurações → Capacidades** e ligue **"Criar e editar arquivos"**
   (a execução de código). A skill precisa disso.
3. Ainda nas configurações, confira se a **busca na web** está ligada. A skill pesquisa
   fontes públicas.
4. Vá em **Personalizar → Skills**, clique em **+**, depois em **Criar skill** e escolha
   **Enviar uma skill**. Selecione o ZIP.
5. Abra uma conversa nova e peça:

   > Faça um raio-x de terceiros da Empresa Exemplo, site exemplo.com.br. É um
   > fornecedor de folha de pagamento que estamos avaliando.

No plano Team, a skill fica só na sua conta. No Enterprise, o administrador pode
liberar o envio de skills (Configurações da organização → Plugins e skills) e
distribuir a skill para todo mundo.

## 2. No Claude Code (terminal)

```bash
git clone https://github.com/btf-security/efeito-borboleta.git
cp -r efeito-borboleta/skills/raio-x-terceiros ~/.claude/skills/
```

Abra o Claude Code e faça o mesmo pedido. Para usar só num projeto, copie para
`.claude/skills/` dentro dele.

Skills instaladas no Claude Code e no claude.ai são independentes: instale em cada
lugar onde for usar.

## 3. Em outro assistente de IA

O `SKILL.md` é texto puro. Em qualquer assistente com busca na web, abra o arquivo,
copie o conteúdo inteiro, cole no início da conversa e, na mesma mensagem, diga qual
empresa analisar. O resultado varia conforme o assistente, mas o método é o mesmo.

## Modificar

A skill é um arquivo Markdown. Abra o `SKILL.md` e mude o que quiser: as seções do
dossiê, o tom, as fontes preferidas, o formato de saída. Os arquivos em `references/`
são consultados pela skill e podem ser ampliados com o seu setor.

No claude.ai, depois de editar, gere o ZIP de novo (a pasta `raio-x-terceiros` tem que
estar na raiz do ZIP, não os arquivos soltos) e envie outra vez. No Claude Code, a
mudança vale na próxima conversa.

## Para mantenedores: gerar o ZIP de uma versão

```bash
cd skills && zip -r raio-x-terceiros.zip raio-x-terceiros
# sem o comando zip:
python3 -c "import shutil; shutil.make_archive('raio-x-terceiros','zip','.','raio-x-terceiros')"
```

Anexe o arquivo à release no GitHub com esse mesmo nome, para o link "latest" da tabela
continuar funcionando.
