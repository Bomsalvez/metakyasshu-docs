# 🧪 Testes

## 📋 Estratégia de Testes

* **🔍 Testes Unitários**
    * 80% de cobertura mínima
    * Testes de componentes
    * Testes de funções
    * Testes de classes

* **🔄 Testes de Integração**
    * APIs REST
    * Banco de dados
    * Serviços externos
    * Comunicação entre módulos

* **🎯 Testes End-to-End**
    * Fluxos críticos
    * Cenários completos
    * Interface do usuário
    * Experiência do usuário

* **⚡ Testes de Performance**
    * Testes de carga
    * Testes de stress
    * Testes de escalabilidade
    * Análise de bottlenecks

* **🔒 Testes de Segurança**
    * Testes de penetração
    * Análise de vulnerabilidades
    * Testes de autenticação
    * Testes de autorização

## 📝 Casos de Teste Críticos

### 🔐 TC001 - Login com Credenciais Válidas

**Cenário:** Usuário faz login com email e senha corretos

* **Dado que** o usuário está na tela de login
* **Quando** preenche email válido e senha correta
* **Então** deve ser redirecionado para o dashboard
* **E** deve receber token de autenticação válido

### 🔄 TC002 - Compartilhar Transação com Grupo

**Cenário:** Usuário compartilha transação com grupo específico

* **Dado que** o usuário possui uma transação criada
* **E** faz parte de pelo menos um grupo
* **Quando** seleciona a transação e escolhe compartilhar
* **E** seleciona um grupo específico
* **Então** a transação deve ficar visível para membros do grupo
* **E** membros devem receber notificação

### 💰 TC003 - Dividir Gasto Entre Membros

**Cenário:** Usuário divide gasto igualmente entre membros do grupo

* **Dado que** o usuário registrou um gasto de R$ 100,00
* **E** o grupo possui 4 membros ativos
* **Quando** escolhe dividir o gasto igualmente
* **Então** cada membro deve receber cobrança de R$ 25,00
* **E** todos devem receber notificação da divisão

---

> ---------------------------------------------------------------------------
> #### 💰 METAKYASSHU 💰
> ***Transformando finanças em conquistas compartilhadas***
> ---------------------------------------------------------------------------