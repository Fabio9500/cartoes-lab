# CLAUDE.md

Este é um repositório de **experimentação**, cópia isolada do sistema CartõesPF (Fabio Oliveira Santos, Telasul/Construsul). O objetivo aqui é aprender a trabalhar com o Claude Code na prática — não é o sistema real em produção.

## Contexto

- Arquivo principal: `cartoes_lab.html` — um app de página única (HTML + CSS + JS), sem build step, sem dependências externas além do que já está no arquivo.
- Persistência de dados: GitHub Contents API, salvando em `cartoes-lab/dados.json` neste mesmo repositório (não no repositório real `Fabio9500/Cartoes`).
- Hospedagem: GitHub Pages, em `https://fabio9500.github.io/cartoes-lab/cartoes_lab.html`.

## Regras de desenvolvimento (mesmas do sistema real, pratique elas aqui)

1. **Sempre validar a sintaxe JavaScript antes e depois de qualquer alteração.** Como o JS está embutido no HTML, extraia o conteúdo entre `<script>` e `</script>` para um arquivo `.js` temporário e rode `node --check` nele.
2. **Usar apenas edições com string única** (equivalente ao `str_replace`) — nunca reescrever o arquivo inteiro por slice/concatenação manual.
3. **Verificar duplicação de funções** após qualquer mudança:
   ```
   grep -oP 'function \w+' arquivo.js | sort | uniq -c | sort -rn | awk '$1>1'
   ```
4. **Versionamento semântico simples**: patch = correção de bug, minor = funcionalidade nova, major = reestruturação. Atualizar a constante `VERSAO` no início do `<script>` a cada entrega.
5. **Nomes de arquivo/commit versionados** — nunca sobrescrever silenciosamente; usar mensagens de commit claras.
6. **Nunca commitar tokens ou senhas** — o token de acesso ao GitHub é configurado pelo próprio usuário dentro do app (tela de configuração), nunca deve aparecer no código-fonte.

## O que pedir primeiro (sugestão de progressão)

1. Uma mudança visual pequena (cor de um botão, texto de um rótulo).
2. Uma mudança de comportamento simples (ex: um novo campo opcional num formulário).
3. Pedir para o Claude Code explicar uma função existente antes de mexer nela.
4. Um commit + push real, revisando o diff antes de aprovar.
