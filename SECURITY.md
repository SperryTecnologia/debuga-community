# Política de Segurança

Segurança é parte fundamental do Debuga Community.

## Informações Sensíveis

Nunca publique neste repositório, Issues, Discussions, Pull Requests ou
logs:

- senhas;
- API keys;
- tokens;
- credenciais de registry;
- chaves privadas;
- arquivos `.env` de produção;
- banco de dados;
- dumps;
- evidências de auditoria;
- dados de clientes;
- configurações específicas de clientes.

## Vulnerabilidades

Não publique vulnerabilidades ainda não corrigidas em Issues públicas.

Utilize o mecanismo privado de comunicação de segurança disponibilizado pelo
projeto ou um canal oficial da Sperry Tecnologia.

## Instalador Público

O instalador público nunca deverá conter:

- credenciais compartilhadas;
- GitHub Personal Access Tokens;
- tokens GHCR embutidos;
- API keys internas;
- senhas de usuários;
- credenciais de clientes.

Distribuição e autorização são conceitos independentes.

O controle de acesso ao Debuga pertence à camada de autenticação e
autorização de acesso da aplicação.

## Vazamento Acidental

Caso uma credencial seja publicada acidentalmente:

1. considerar a credencial comprometida;
2. revogar ou rotacionar imediatamente;
3. interromper a distribuição do artefato afetado;
4. revisar o histórico Git;
5. revisar sistemas dependentes;
6. registrar o incidente internamente.

Remover apenas o arquivo visível não é suficiente, pois versões anteriores
podem continuar presentes no histórico Git.

## Evidências Internas

Evidências de engenharia, auditorias de produção, dumps do schema do banco e
artefatos internos da Phase 2 devem permanecer fora deste repositório
público, salvo aprovação e sanitização explícitas.

## Autenticação e Autorização de Acesso

A publicação do instalador e da documentação não altera os requisitos de
autenticação e autorização de acesso do produto. Alunos OpenInfra
autenticados têm acesso integral ao ambiente e aos recursos disponibilizados
para sua formação; clientes e demais usuários acessam o Debuga conforme a
autorização vinculada à sua conta.
