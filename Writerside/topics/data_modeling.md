# 📊 Modelagem de Dados

## 🏗️ Entidades Principais

* **👤 Usuário**
* **👥 Perfil**
* **💰 Conta Financeira**
* **💸 Transação**
* **👥 Grupo**

## 🔄 Relacionamentos

* **👤 Usuário**
    * ➡️ Múltiplos perfis (1:N)
    * ➡️ Múltiplos grupos (N:M)
    * ➡️ Múltiplas transações (1:N)

* **👥 Perfil**
    * ➡️ Múltiplas contas (1:N)
    * ➡️ Múltiplas transações (1:N)
    * ➡️ Pertence a um usuário (N:1)

* **💰 Conta Financeira**
    * ➡️ Múltiplas transações (1:N)
    * ➡️ Pertence a um perfil (N:1)
    * ➡️ Pode ser compartilhada (N:M)

* **💸 Transação**
    * ➡️ Pertence a uma conta (N:1)
    * ➡️ Pode ser compartilhada (N:M)
    * ➡️ Pode ter múltiplos participantes (N:M)

* **👥 Grupo**
    * ➡️ Múltiplos usuários (N:M)
    * ➡️ Múltiplas transações (N:M)
    * ➡️ Múltiplas contas (N:M)

---

> ---------------------------------------------------------------------------
> #### 💰 METAKYASSHU 💰
> ***Transformando finanças em conquistas compartilhadas***
> ---------------------------------------------------------------------------