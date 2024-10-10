---
marp: true
---

# Smart Contracts: Um Programa em Blockchain

Um contrato inteligente é um código implantado na blockchain. Por exemplo:

```js
contract Agreement {
  address recipient;
  bool conditionIsMet;

  function payout() external {
    if (conditionIsMet) {
      sendValue(recipient);
    }
  }

  // ...
}

---

## Implantando um Contrato

- ⚙️ compile seu código **solidity** para bytecode
- ✉️ envie uma transação contendo o bytecode para um nó EVM
- 🏡 o nó calcula um endereço para o seu novo contrato

## Implantação do Contrato

| Opcode | Nome | Descrição                   | Gas |
| ------ | ---- | ----------------------------| --- |
| `0x00` | STOP  | Interrompe a execução       | 0   |
| `0x01` | ADD   | Operação de adição          | 3   |
| `0x02` | MUL   | Operação de multiplicação   | 5   |
| `0x03` | SUB   | Operação de subtração       | 3   |

[Referência](https://ethereum.org/en/developers/docs/evm/opcodes/)

## Principais Conclusões

1. ⚙️ Contratos são compilados para bytecode de criação
2. ⛓ O campo `data` contém seu bytecode de criação
3. 📭 O campo `to` é deixado em branco para implantar um contrato
4. 🏡 Seu contrato terá um endereço, saldo e bytecode de execução

## Ciclo de Vida de uma Transação

---

## Principais Conclusões

1. 🥾 As transações começam em uma EOA (Conta Externamente Controlada)
2. ☝️ As transações ocorrem de forma sequencial
3. ⛽️ As transações definem um limite de gas
4. 🎯 As transações enviam calldata, visando um método do contrato
5. 🌐 Da mesma forma, os contratos inteligentes podem chamar uns aos outros dentro de uma mesma transação
