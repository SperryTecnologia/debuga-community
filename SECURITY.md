# Security Policy

Segurança é parte fundamental do Debuga Community.

## Informações Sensíveis

Nunca publique neste repositório, Issues, Discussions, Pull Requests ou logs:

- senhas;
- API keys;
- tokens;
- registry credentials;
- private keys;
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

## Installer Público

O Installer público nunca deverá conter:

- credenciais compartilhadas;
- GitHub Personal Access Tokens;
- tokens GHCR embutidos;
- API keys internas;
- senhas de usuários;
- credenciais de clientes.

Distribuição e autorização são conceitos independentes.

O controle de acesso ao Debuga pertence à camada de autenticação e
entitlement da aplicação.

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

Evidências de engenharia, auditorias de produção, database schema dumps e
artefatos internos da Phase 2 devem permanecer fora deste repositório
público, salvo aprovação e sanitização explícitas.
