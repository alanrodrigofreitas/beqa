# Beqa Token

## Descrição
Beqa é um token ERC-20 baseado na blockchain Ethereum. Ele implementa funcionalidades padrão de um token ERC-20, incluindo queima de tokens (burn), permissões (permit) e um mecanismo de propriedade para controle administrativo.

## Tecnologias Utilizadas
- Solidity ^0.8.22
- OpenZeppelin Contracts ^5.0.0

## Funcionalidades
- **Total Supply Inicial:** 50.000.000 BEQA
- **Suporte a Burn:** Qualquer titular de tokens pode queimar seus próprios tokens.
- **Minting Controlado:** Apenas o proprietário do contrato pode criar novos tokens.
- **Permit (EIP-2612):** Assinaturas off-chain para aprovações de transferência sem gastar gás diretamente.
- **Ownable:** Controle administrativo do contrato para funções restritas.

## Estrutura do Código
O contrato Beqa utiliza as seguintes bibliotecas do OpenZeppelin:
- `ERC20` - Implementação padrão de um token ERC-20.
- `ERC20Burnable` - Adiciona a capacidade de queimar tokens.
- `ERC20Permit` - Implementa aprovações off-chain via assinaturas EIP-2612.
- `Ownable` - Garante que certas funções sejam executadas apenas pelo proprietário do contrato.

## Como Usar
### Deploy do Contrato
1. Compile o contrato utilizando Hardhat ou Remix.
2. Faça o deploy informando o endereço do proprietário inicial:
   ```solidity
   Beqa newToken = new Beqa(ownerAddress);
   ```

### Minting de Tokens
Apenas o proprietário pode criar novos tokens:
```solidity
newToken.mint(address recipient, uint256 amount);
```

### Queima de Tokens
Qualquer titular de BEQA pode queimar seus próprios tokens:
```solidity
newToken.burn(uint256 amount);
```

## Licença
Este projeto está licenciado sob a **MIT License**.