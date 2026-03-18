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

### ✅ Validações realizadas

- Verificação do status code (esperado: 200)
- Validação da existência do campo `data.list.name`
- Validação do valor retornado (esperado: `"Professional"`)

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

