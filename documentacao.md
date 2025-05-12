# Documentação do Ecossistema Especialista Imóveis

## Informações Gerais do Sistema
**Especialista Imóveis (Ecossistema DONNA + BILL 2.0)**  
Data de implantação: 12/05/2025

### Configuração do Sistema
- Login customizado via tabela usuarios_sistema
- Integração do chat com a base de conhecimento
- Sistema de correção supervisionada de agentes

### Tecnologias Utilizadas
- Frontend: React, TypeScript, Tailwind CSS
- Backend: Supabase (Database, Storage, Edge Functions)
- Autenticação: Sistema próprio (integrado ao Supabase)

## Usuários e Autenticação

### Sistema de Usuários
- 8 usuários cadastrados na tabela usuarios_sistema
- Canal padrão de todos os usuários: web
- Usuário master: caio.alves@especialistasmg.com.br

### Autenticação
- Login por e-mail ou WhatsApp + senha
- Validação direta contra a tabela usuarios_sistema
- Controle de permissões por nível (master/comum)
- Sessão armazenada via localStorage

## Agentes e Base de Conhecimento

### Base de Conhecimento
- Estrutura na tabela documents do Supabase
- Organização por tags e categorias
- Busca semântica via ILIKE (simplificada)

### Agentes Implementados

**Agentes Principais:**
- Donna (Interface Executiva)
- Bill (Orquestrador Central)
- ISA (Atendimento Inicial)
- Mike Ross (Captação)
- Louis (Jurídico)
- Soares (Pós-venda)
- Brandão (Captação)
- Maurício (Visual)
- Mark (Marketing)

**Agentes Especializados:**
- Fidel (Pós-venda)
- Emily (Textos)
- Stive (Vídeos)
- Cris (Criativos)
- Prompt Jedi (Otimização)
- Delegado (Ética)
- Caio-IA (Simulação)
- Berlim (Leilões)
- Will Marston (DISC)

## Funcionalidades e Integrações

### ChatInterface
- Integração com a base documents do Supabase
- Busca semântica por title, content e tags
- Sistema de histórico de mensagens

### Correção Supervisionada
- Detecção de correções nos inputs do usuário
- Envio para aprovação do usuário master
- Aprendizado contínuo após aprovação

---

## Instruções para Implantação

### Configuração do Supabase

1. **Tabelas requeridas no Supabase:**
   - usuarios_sistema (autenticação)
   - documents (base de conhecimento)
   - mcp_sessions (rastreamento de sessões)
   - mcp_acoes (registro de ações/execuções)
   - mcp_logs (histórico de interações)

2. **Configuração de usuários:**
   - Garantir que o usuário master esteja cadastrado: caio.alves@especialistasmg.com.br
   - Configurar senha e status ativo

3. **Importação da base de conhecimento:**
   - Importar via CSV para a tabela documents ou usar a interface administrativa

### Estrutura do Frontend

O projeto é estruturado em componentes React com TypeScript:

- **Layout**:
  - Header: Barra de navegação superior
  - SidebarMenu: Menu lateral com acesso aos agentes e ferramentas
  - RightSidebar: Painel lateral direito (quando aplicável)

- **Autenticação**:
  - Login: Integração híbrida com Supabase e tabela usuarios_sistema
  - ProtectedRoute: HOC para proteção de rotas

- **Chat e Comunicação**:
  - ChatInterface: Componente principal de interação com agentes
  - ChatInput: Entrada de mensagens do usuário
  - ChatMessageList: Exibição de histórico de mensagens

- **Documentação**:
  - SystemDocumentation: Documentação completa do sistema

### Integração com GitHub

O repositório do projeto está disponível em: 
https://github.com/CaioAlves-Art/ecossistema-agent

### Recursos Adicionais

Para baixar a documentação completa em formato de texto, utilize o botão "Download Documentação" na página de documentação do sistema.

### Memória Vetorial e Documentação

- Supabase utilizado como vetor de contexto + logs operacionais
- Mensagens e interações registradas com session_id, task_id, user_id
- Arquivos de suporte incluem prompts, fluxos JSON e textos técnicos
