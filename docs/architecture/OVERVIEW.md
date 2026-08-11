# Debuga Community Architecture

## Objetivo

O Debuga Community fornece a camada pública de distribuição do ecossistema
Debuga preservando uma fronteira explícita entre recursos públicos de
implantação e o código privado da aplicação.

## Distribution Boundary

```mermaid
flowchart TB
    PRIVATE["Private Application Source"]
    BUILD["Controlled Build Pipeline"]
    IMAGE["Official Versioned Image"]
    COMMUNITY["Debuga Community"]
    INSTALLER["Public Installer"]
    TARGET["Student / Customer Host"]
    AUTH["Authentication"]
    ENT["Entitlement"]
    ACCESS["Authorized Access"]

    PRIVATE --> BUILD
    BUILD --> IMAGE
    COMMUNITY --> INSTALLER
    INSTALLER --> TARGET
    IMAGE --> TARGET
    TARGET --> AUTH
    AUTH --> ENT
    ENT --> ACCESS
```

## Runtime Padrão

```mermaid
flowchart LR
    USER["Browser"]
    GATEWAY["Caddy"]
    APP["Debuga App"]
    DB["PostgreSQL"]
    STORAGE["MinIO"]

    USER --> GATEWAY
    GATEWAY --> APP
    APP --> DB
    APP --> STORAGE
```

## LOCAL

```text
Browser → HTTP :8080 → Caddy → Debuga App
```

Indicado para laboratório, curso, homologação e rede interna.

## PUBLIC

```text
Internet → HTTP/HTTPS :80/:443 → Caddy → Debuga App
```

Indicado para VPS ou servidor publicado diretamente.

## Princípio de Segurança

```text
Public Distribution
        ≠
Authorized Use
```

Disponibilizar recursos de instalação publicamente não remove os requisitos
de autenticação e entitlement do produto.

## Princípio de Release

```text
Source
  ↓
Controlled Build
  ↓
Immutable Image
  ↓
Release Manifest
  ↓
Installer
  ↓
Validated Deployment
```

Cada componente público deve ser rastreável e verificável antes de uma
release oficial.
