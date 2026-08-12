# Mica AI Deal Escrow

This project supports two escrow custody modes:

- `seam` mode: the deal workflow works, but on-chain escrow funding is disabled.
- `contract` mode: on-chain Arc USDC escrow is enabled when `VITE_ESCROW_FACTORY_ADDRESS` is configured.

## Enable real on-chain escrow

1. Deploy the `DealEscrowFactory` contract:
   ```bash
   npm install --save-dev solc
   node scripts/deploy-escrow.mjs
   ```
2. Set the factory address in `.env` or your Vite environment:
   ```env
   VITE_ESCROW_FACTORY_ADDRESS=0xYourFactoryAddressHere
   ```
3. Restart the Vite dev server.

## Notes

- If `VITE_ESCROW_FACTORY_ADDRESS` is not set, the app falls back to `seam` custody mode.
- `scripts/deploy-escrow.mjs` also supports `DEPLOYER_PRIVATE_KEY` and `ARC_RPC_URL` via environment variables.

