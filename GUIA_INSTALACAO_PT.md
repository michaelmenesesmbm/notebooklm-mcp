# 📚 NotebookLM MCP - Guia de Instalação e Uso

## 🎯 O que é?

O **NotebookLM MCP Server** permite que o Antigravity (e outros agentes de IA) conversem diretamente com o NotebookLM do Google para obter respostas **sem alucinações** baseadas nos seus próprios notebooks.

## 🚀 Instalação no Antigravity

Para instalar o MCP no Antigravity, execute:

```bash
gemini mcp add notebooklm npx notebooklm-mcp@latest
```

## 📋 Início Rápido

### 1. Autenticação (apenas uma vez)

No chat do Antigravity, diga:
```
"Log me in to NotebookLM"
```

Uma janela do Chrome abrirá → faça login com sua conta Google

### 2. Crie sua base de conhecimento

1. Acesse [notebooklm.google.com](https://notebooklm.google.com)
2. Crie um novo notebook
3. Faça upload dos seus documentos:
   - 📄 PDFs, Google Docs, arquivos markdown
   - 🔗 Websites, repositórios GitHub
   - 🎥 Vídeos do YouTube
   - 📚 Múltiplas fontes por notebook

4. Compartilhe: **⚙️ Share → Anyone with link → Copy**

### 3. Use com o Antigravity

```
"Estou trabalhando com [biblioteca]. Aqui está meu NotebookLM: [link]"
```

**Pronto!** O Antigravity agora pergunta ao NotebookLM o que precisar antes de escrever código.

## 🎨 Comandos Comuns

| Intenção | Diga | Resultado |
|----------|------|-----------|
| Autenticar | *"Log me in to NotebookLM"* | Chrome abre para login |
| Adicionar notebook | *"Add [link] to library"* | Salva notebook com metadados |
| Listar notebooks | *"Show our notebooks"* | Lista todos os notebooks salvos |
| Pesquisar primeiro | *"Research this in NotebookLM before coding"* | Sessão com múltiplas perguntas |
| Selecionar notebook | *"Use the React notebook"* | Define notebook ativo |
| Ver navegador | *"Show me the browser"* | Assista ao chat ao vivo do NotebookLM |
| Corrigir autenticação | *"Repair NotebookLM authentication"* | Limpa e re-autentica |
| Trocar conta | *"Re-authenticate with different Google account"* | Muda de conta |
| Limpeza completa | *"Run NotebookLM cleanup"* | Remove todos os dados para recomeçar |

## 💡 Por que usar NotebookLM em vez de RAG local?

| Abordagem | Custo de Tokens | Tempo de Setup | Alucinações | Qualidade |
|-----------|----------------|----------------|-------------|-----------|
| **Alimentar docs ao Claude** | 🔴 Muito alto | Instantâneo | Sim | Variável |
| **Busca na web** | 🟡 Médio | Instantâneo | Alta | Inconsistente |
| **RAG Local** | 🟡 Médio-Alto | Horas | Média | Depende do setup |
| **NotebookLM MCP** | 🟢 Mínimo | 5 minutos | **Zero** | Síntese especializada |

## ✨ Recursos Principais

### **Zero Alucinações**
NotebookLM se recusa a responder se a informação não estiver nos seus documentos. Sem APIs inventadas.

### **Pesquisa Autônoma**
O Antigravity faz perguntas de acompanhamento automaticamente, construindo compreensão completa antes de codificar.

### **Gerenciamento Inteligente de Biblioteca**
Salve links do NotebookLM com tags e descrições. O Antigravity seleciona automaticamente o notebook certo para sua tarefa.

```
"Add [link] to library tagged 'frontend, react, components'"
```

### **Compartilhamento entre Ferramentas**
Configure uma vez, use em todos os lugares. Claude Code, Codex, Cursor — todos compartilham a mesma biblioteca.

## 🔧 Perfis de Ferramentas

Reduza o uso de tokens carregando apenas as ferramentas necessárias:

```bash
# Verificar configurações atuais
npx notebooklm-mcp config get

# Definir um perfil
npx notebooklm-mcp config set profile minimal    # 5 ferramentas
npx notebooklm-mcp config set profile standard   # 10 ferramentas
npx notebooklm-mcp config set profile full       # 16 ferramentas

# Resetar para padrões
npx notebooklm-mcp config reset
```

## 📁 Estrutura do Repositório

```
notebooklm-mcp/
├── src/              # Código-fonte TypeScript
├── docs/             # Documentação detalhada
├── README.md         # Documentação principal (inglês)
├── package.json      # Dependências do projeto
└── tsconfig.json     # Configuração TypeScript
```

## 📖 Documentação Adicional

- [**Usage Guide**](./docs/usage-guide.md) — Padrões, workflows, dicas
- [**Tool Reference**](./docs/tools.md) — API MCP completa
- [**Configuration**](./docs/configuration.md) — Variáveis de ambiente
- [**Troubleshooting**](./docs/troubleshooting.md) — Problemas comuns

## ⚠️ Avisos Importantes

1. **Automação de Navegador**: Use uma conta Google dedicada para automação, não sua conta principal
2. **Revisão de Código**: Sempre revise mudanças antes de commitar ou fazer deploy
3. **Testes**: Teste em ambientes seguros primeiro
4. **Backups**: Mantenha backups do trabalho importante

## 🔗 Links Úteis

- **Repositório GitHub**: [PleasePrompto/notebooklm-mcp](https://github.com/PleasePrompto/notebooklm-mcp)
- **NotebookLM**: [notebooklm.google.com](https://notebooklm.google.com)
- **Skill para Claude Code**: [notebooklm-skill](https://github.com/PleasePrompto/notebooklm-skill)

## 📝 Licença

MIT — Use livremente em seus projetos.

---

**Localização do Repositório Clonado:**
```
/Users/michaelmeneses/Library/CloudStorage/GoogleDrive-mm.design.graf@gmail.com/Meu Drive/ANTIGRAVITY/notebooklm-mcp
```

**Data de Download:** 28 de Janeiro de 2026
