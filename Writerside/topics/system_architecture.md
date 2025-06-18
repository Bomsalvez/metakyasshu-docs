# 🏗️ Arquitetura do Sistema METAKYASSHU

## 🔄 Arquitetura Geral

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Mobile App    │    │   Web App       │    │   Desktop App   │
│   (Kotlin/      │    │   (Angular 17+) │    │   (Kotlin/      │
│   Android)      │    │   + PWA         │    │   Compose MP)   │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                      │                      │
         └──────────────────────┼──────────────────────┘
                                │
                                ▼
                        ┌─────────────────┐
                        │   API Gateway   │
                        │ (Spring Gateway)│
                        │   + Rate Limit  │
                        └─────────────────┘
                                │
                                ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Auth Service  │    │Financial Service│    │  Group Service  │
│  (Spring Boot)  │◄──►│ (Spring Boot)   │◄──►│ (Spring Boot)   │
│   + JWT/OAuth2  │    │   + Analytics   │    │  + Permissions  │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                      │                      │
         └──────────────────────┼──────────────────────┘
                                │
                                ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   User Service  │    │Notification Svc │    │Integration Svc  │
│  (Spring Boot)  │    │ (Spring Boot)   │    │ (Spring Boot)   │
│   + Profiles    │    │   + Push/Email  │    │ + Open Banking  │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                      │                      │
         └──────────────────────┼──────────────────────┘
                                │
                                ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│     MinIO       │    │     MySQL 8.x   │    │     Redis       │
│ (File Storage)  │    │ (Master/Slave)  │    │   (Cache)       │
│  + Encryption   │    │   + Backups     │    │  + Sessions     │
└─────────────────┘    └─────────────────┘    └─────────────────┘
                                │
                                ▼
                        ┌─────────────────┐
                        │     Docker      │
                        │   Compose +     │
                        │  Monitoring     │
                        └─────────────────┘
```

## 🛠️ Microserviços (Spring Boot 3.x)

### 🔐 **Auth Service**

- Autenticação JWT + Refresh Tokens
- Autenticação biométrica
- Gestão de sessões multi-dispositivo
- Logs de auditoria de acesso

### 👤 **User Service**

- Perfis de usuário completos
- Configurações e preferências
- Temas personalizáveis (Dark/Light)
- Score financeiro pessoal
- Backup/restore de dados

### 💰 **Financial Service**

- **Transações**: CRUD completo com tags
- **Categorias**: Personalizáveis e inteligentes (IA para categorizar transações)
- **Orçamentos**: Individuais e colaborativos
- **Previsões**: IA para análise preditiva
- **Multi-moeda**: Conversão automática
- **PIX Integration**: Reconhecimento automático tanto de pix quanto boletos e demais transações bancárias

### 👥 **Group Service**

- **Compartilhamento Granular**: Por tags, períodos, valores
- **Permissões**: Visualização, edição, aprovação
- **Grupos Temporários**: Links com expiração
- **Orçamento Familiar**: Múltiplos contribuintes

### 🔔 **Notification Service**

- Alertas inteligentes (gastos anômalos)
- Lembretes de vencimentos
- Notificações push multiplataforma
- Webhooks para sistemas externos
- Templates personalizáveis

### 📊 **Analytics Service**

- **Dashboards**: Interativos e personalizáveis
- **Relatórios**: PDF, Excel, múltiplos formatos
- **Insights**: Padrões de consumo e tendências
- **Comparações**: Benchmark social anônimo
- **Exportação**: Dados completos em vários formatos

### 🔌 **Integration Service**

- **Open Banking**: APIs bancárias brasileiras
- **Importação**: OFX, CSV, PDF, extratos por email
- **APIs Externas**: Cotações, inflação, juros
- **Sincronização**: Automática e manual
- **API Pública**: Para desenvolvedores terceiros

### 📁 **File Service**

- Upload de comprovantes via MinIO
- Criptografia end-to-end
- Compressão automática de imagens
- OCR para extração de dados
- Backup automático criptografado

## 🛠️ Stack Tecnológica

### 🌐 Frontend

* **Web**
    * Angular 17+
    * Angular Material
    * Progressive Web App (PWA)
* **Mobile**
    * Kotlin (Android nativo)
    * Widgets nativos Android/iOS
* **Desktop**
    * Kotlin Multiplatform
    * Compose Multiplatform

### ⚙️ Backend

* **Framework**
    * Spring Boot 3.x
    * Spring Security 6.x
* **Serviços**
    * API Gateway (Spring Gateway)
    * Microserviços: Auth, User, Financial, Group, Notification, Analytics, Integration, File (todos Spring Boot)
* **Banco de Dados**
    * MySQL 8.x (replicação master-slave)
    * Redis (cache, sessões)
* **Armazenamento**
    * MinIO (arquivos, backups)
* **Mensageria**
    * RabbitMQ (comunicação assíncrona)
* **Validação**
    * Bean Validation (Jakarta)
    * Custom Validators
* **Documentação**
    * Swagger/OpenAPI
    * Javadoc

### ☁️ Infraestrutura & DevOps

* **Containers**
    * Docker
    * Docker Compose
* **CI/CD**
    * GitHub Actions
    * Testes automatizados
* **Monitoramento**
    * Prometheus
    * Grafana
    * Jaeger (tracing)
* **Logs**
    * ELK Stack (Elasticsearch, Logstash, Kibana)
* **Segurança**
    * Vault (gestão de segredos)

## 📁 Estrutura do Projeto

```
metakyasshu/
├── apps/
│   ├── web/                 # App Angular
│   ├── mobile/              # App Kotlin Android
│   └── desktop/             # App Kotlin Multiplatform
├── services/
│   ├── api-gateway/         # Spring Gateway
│   ├── auth-service/        # Auth (Spring Boot)
│   ├── user-service/        # User (Spring Boot)
│   ├── financial-service/   # Financial (Spring Boot)
│   ├── group-service/       # Group (Spring Boot)
│   ├── notification-service/# Notification (Spring Boot)
│   ├── analytics-service/   # Analytics (Spring Boot)
│   ├── integration-service/ # Integration (Spring Boot)
│   └── file-service/        # File (Spring Boot)
├── infra/
│   ├── docker/              # Dockerfiles, Compose, scripts
│   ├── k8s/                 # Manifests Kubernetes (opcional)
│   └── monitoring/          # Dashboards, alertas
├── docs/                    # Documentação
└── scripts/                 # Scripts de automação
```

## 🔄 Pipeline de Deploy

### 🌍 Ambientes

* **Development**
    * Ambiente local (Docker Compose)
    * Hot-reload (Spring DevTools, Angular CLI)
    * Debugging
* **Staging**
    * Homologação integrada
    * Testes automatizados (CI)
    * QA
* **Production**
    * Alta disponibilidade
    * Replicação de banco
    * Monitoramento e backup

### ⚡ Processo de Deploy

* **Commit & Review**
    * GitHub
    * Pull Requests
    * Proteção de branch
* **Build**
    * Build de imagens Docker para cada serviço
    * Otimização e cache
* **Testes**
    * Unitários (JUnit, Angular)
    * Integração (Testcontainers, Postman)
    * E2E (Cypress, Espresso)
* **Segurança**
    * Análise de vulnerabilidades (SCA)
    * Gestão de segredos (Vault)
    * Compliance LGPD/PCI-DSS
* **Deploy**
    * Docker Compose (local/staging)
    * Kubernetes (produção, opcional)
    * Blue-green/rollback
* **Monitoramento**
    * Health checks
    * Métricas (Prometheus)
    * Logs centralizados (ELK)
    * Alertas (Grafana)

### Recursos Diferenciados

#### 🎯 **Compartilhamento Inteligente**

- Granularidade por transação, categoria, período
- Valores mascarados (percentuais, faixas)
- Aprovações em tempo real
- Histórico de visualizações

#### 🤖 **IA & Machine Learning**

- Categorização automática de transações
- Detecção de fraudes e anomalias
- Previsões de gastos personalizadas
- Recomendações de economia

#### 🔒 **Segurança Avançada**

- Criptografia E2E para dados sensíveis
- Autenticação multi-fator
- Tokenização de dados bancários
- Compliance com LGPD e PCI-DSS

---

> ---------------------------------------------------------------------------
> #### 💰 METAKYASSHU 💰
> ***Transformando finanças em conquistas compartilhadas***
>
> **Arquitetura Escalável • Segurança Bancária • Experiência Única**
> ---------------------------------------------------------------------------