# EZ-Path MONSKILLS Skill

[![npm version](https://img.shields.io/npm/v/@infiniteezverse/monskills-ezpath.svg)](https://www.npmjs.com/package/@infiniteezverse/monskills-ezpath)
[![GitHub](https://img.shields.io/badge/github-infiniteezverse%2Fmonskills--ezpath-blue)](https://github.com/infiniteezverse/monskills-ezpath)

A MONSKILLS skill exposing **EZ-Path** DEX routing to AI agents building on Monad, Base, and other EVM chains.

**Agentic Monad Price Racing Orchestration of Diverse Aggregators** — Races 10 DEX venues simultaneously and returns the best price.

## What is EZ-Path?

- 🏎️ **Races 10 DEX venues** simultaneously (0x, ParaSwap, Aerodrome, Uniswap V3, Curve, Balancer, Uniswap V2, 1Inch, CoW, Synthetix)
- 💰 **Returns the best price** (highest buyAmount)
- 🔐 **No API key required** — Payment via X402 EIP-3009 USDC
- ⚡ **Sub-2 second quotes**

Live: https://ezpath.myezverse.xyz

## Installation

```bash
npx skills add @infiniteezverse/monskills-ezpath
npm install @infiniteezverse/monskills-ezpath
```

## Quick Start

```typescript
import { getPrice } from '@infiniteezverse/monskills-ezpath';

const result = await getPrice(
  'base',
  '0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913', // USDC
  '0x4200000000000000000000000000000000000006', // WETH
  '1000000' // 1 USDC
);

if ('price' in result) {
  console.log(`Price: ${result.price}`);
  console.log(`Sources: ${result.sources.join(', ')}`);
}
```

## API

- `getPrice(chain, sellToken, buyToken, amount)` — Quick price lookup
- `getQuote(request)` — Full quote with venue details
- `batchQuotes(requests)` — Multiple quotes in parallel

## Chains

| Chain | Status |
|-------|--------|
| Base | ✅ Live |
| Monad | ✅ Live |
| Arbitrum, Optimism, Polygon | 🚧 Soon |

## Pricing

| Tier | Cost | Features |
|------|------|----------|
| Basic | $0.03 | Direct 0x |
| Resilient | $0.10 | 4-venue race |
| Institutional | $0.50 | 10-venue race |

Payment via X402 USDC on Base.

## Use Cases

✅ Agent swaps with real DEX pricing  
✅ Portfolio valuation  
✅ Arbitrage detection  
✅ Arena agent bankroll management

## Links

- 🌐 https://ezpath.myezverse.xyz
- 📖 https://ezpath.myezverse.xyz/openapi.json
- 🤖 https://ezpath.myezverse.xyz/.well-known/agent.json
- 💬 https://discord.gg/monad

## License

MIT

---

**Made for agents, by builders.** 🚀
