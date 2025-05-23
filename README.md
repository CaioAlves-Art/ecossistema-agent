# Ecossistema Agent – Especialista Imóveis

Sistema inteligente integrado com Supabase, Vercel, múltiplos agentes IA e memória vetorial. Projetado para atender demandas da equipe Especialista Imóveis de forma rápida, segura e eficiente.

## 🚀 Deploy
🔗 Em breve: [https://ecossistema-agent.vercel.app](https://ecossistema-agent.vercel.app)

## 📦 Tecnologias
- React + TypeScript
- Supabase (DB + Auth + Vector)
- Tailwind CSS
- OpenAI + N8N + Webhooks
- Vercel (Deploy)

## 🔐 Login
- Acesso por e-mail ou WhatsApp (tabela `usuarios_sistema` no Supabase)
- Senha obrigatória
- Autenticação validada pelo Supabase, com controle por nível (`master` / `comum`)
- Usuário master: `caio.alves@especialistasmg.com.br`

## 🧠 Agentes Inteligentes
O ecossistema possui mais de 20 agentes especializados com memória e função própria.

Principais:
- Donna (secretária executiva)
- Bill (orquestrador do ecossistema)
- ISA (atendimento inicial)
- Mike Ross (jurídico imobiliário)
- Louis (CRECI e jurídico avançado)
- Soares (descrições persuasivas)
- Brandão (avaliação de imóveis)
- Maurício (imagens)
- Mark (Instagram META)
- Berlim (leilões)
- Prompt Jedi (otimização de IA)
- Fidel, Emily, Stive, Cris, Will Marston, etc.

## 📁 Estrutura de pastas
src/
┣ components/
┃ ┣ layout/
┃ ┣ chat/
┣ pages/
┣ lib/
┣ hooks/
┗ utils/

## 🛠️ Como rodar localmente

```bash
npm install
npm run dev
⚙️ Supabase – Tabelas principais
usuarios_sistema – autenticação (e-mail ou telefone)

documents – base de conhecimento

mcp_sessions, mcp_logs, mcp_acoes – controle de sessões inteligentes

🔍 Correção supervisionada de agentes
Quando um usuário corrige um agente, a correção é enviada para Caio ou outro master.
Após aprovação, a nova instrução entra no contexto permanente daquele agente.

📜 Licença
MIT

