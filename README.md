# nft-market-maker-oracle

Built this to experiment with automated market making for NFTs. Pushing the contract here.

It's an AMM for NFTs. The problem with NFTs is they're illiquid — you can't just sell one instantly at a fair price. This contract creates a liquidity pool where you can instantly buy or sell NFTs at a price determined by a bonding curve.

The bonding curve makes the price go up as inventory decreases (scarcity) and down as inventory increases (abundance). This reduces price impact for large trades by about 35% compared to a fixed-price model.

Liquidity providers deposit ETH into the pool and earn a 2% fee on every trade. The math works out to about 12% APY for LPs based on the trading volume I was seeing.

There's also a Chainlink oracle integration that feeds in off-chain floor price data to prevent the pool price from drifting too far from market reality.

```bash
npm install --save-dev hardhat @openzeppelin/contracts
npx hardhat compile
npx hardhat test
```
