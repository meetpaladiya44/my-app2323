# ERC-20 Token

| Field | Value |
|-------|-------|
| Type | `erc20-stylus` |
| ID | `8bc58ace` |
| Category | contracts |
| Tags | token, erc20, stylus, arbitrum, fungible |
| Description | Deploy ERC-20 token on Arbitrum Stylus |

## Configuration

| Setting | Value |
|---------|-------|
| Token Name | SuperPositionToken |
| Token Symbol | SPT |
| Decimals | 18 |
| Network | arbitrum-sepolia |
| Selected Functions | mint, mint_to, burn |

## Environment Variables

| Key | Description | Required | Secret | Default |
|-----|-------------|----------|--------|---------|
| `NEXT_PUBLIC_TOKEN_ADDRESS` | Deployed ERC20 token address | No | No |  |
| `PRIVATE_KEY` | Private key for deployment and transactions | Yes | Yes |  |
| `ERC20_DEPLOYMENT_API_URL` | URL of the ERC20 deployment API | No | No | http://localhost:4000 |

## Scripts

| Name | Command |
|------|---------|
| `deploy:token` | `ts-node scripts/deploy-erc20.ts` |
| `token:info` | `ts-node scripts/token-info.ts` |

## Documentation

### ERC-20 Token

# SuperPositionToken (SPT)

An ERC-20 token deployed on Arbitrum Sepolia using Stylus.

## Token Details

- **Name:** SuperPositionToken
- **Symbol:** SPT
- **Initial Supply:** 1000000
- **Network:** arbitrum-sepolia
- **Features:** ownable, mintable, burnable, pausable

## Deployment

```bash
pnpm deploy:token
```

This will deploy the token and output the contract address.

## Usage

### Get Token Info

```typescript
import { fetchTokenInfo } from '@/lib/erc20-token';

const info = await fetchTokenInfo();
console.log(info.name, info.symbol, info.formattedTotalSupply);
```

### Transfer Tokens

```typescript
import { sendTokens } from '@/lib/erc20-token';

await sendTokens('0x...', '100', privateKey);
```

### Mint Tokens (Owner Only)

```typescript
import { mintTokens } from '@/lib/erc20-token';

await mintTokens('0x...', '1000', privateKey);
```

## Contract Features

- **ownable**: Enabled
- **mintable**: Enabled
- **burnable**: Enabled
- **pausable**: Enabled


## File Structure

This component would generate the following files:

- `deploy-erc20.ts` (contract-scripts)
- `erc20-token.ts` (frontend-lib)
- `ERC20TokenPanel.tsx` (frontend-components)

