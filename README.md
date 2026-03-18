## API Trello

## Objetivo
Realizar um GET na API do Trello e validar:
- Status code 200
- Campo data.list.name
- Valor esperado: "Professional"

## Endpoint
https://api.trello.com/1/actions/592f11060f95a3d3d46a987a

## Ferramenta
Postman

##Testes realizados

- Validação de status code
- Validação de campo existente
- Validação de valor esperado

## Collection do Postman

Você pode importar a collection utilizada neste projeto:

[⬇️ Baixar Collection](./Desafio%20API%20Trello.postman_collection.json)

## Script de teste

## código usado em testes
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
