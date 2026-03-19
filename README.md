## 🔎 Teste de API - Trello

### 🎯 Objetivo
Realizar uma requisição GET na API do Trello e validar alguns pontos importantes da resposta, garantindo que o serviço esteja funcionando corretamente.

---

### 🌐 Endpoint utilizado
https://api.trello.com/1/actions/592f11060f95a3d3d46a987a

---

### 🛠️ Ferramenta
Postman

---

### ✅ BDD

Feature: Trello API

  Scenario: Validar retorno da API do Trello

    Given I send a GET request to the Trello API
    Then the response status should be 200
    And the list name should be "Professional"

---

### 📦 Collection
A collection do Postman utilizada neste teste está disponível no repositório para importação.

---

### 🧪 Script de testes

```javascript
pm.test("Status code é 200", function () {
    pm.response.to.have.status(200);
});

let response = pm.response.json();

pm.test("Campo list.name existe", function () {
    pm.expect(response.data.list.name).to.not.be.undefined;
});

pm.test("Nome da lista é Professional", function () {
    pm.expect(response.data.list.name).to.eql("Professional");
});

