# AK Governor — Claude Code Project Guide

## Project Overview
AK Governor is an open-source DAO governance system for Solana.
Stack: Anchor (Rust smart contracts) + React/TypeScript frontend + Alchemy RPC.

## Environment Variables
```bash
export COLOSSEUM_COPILOT_API_BASE="https://copilot.colosseum.com/api/v1"
export COLOSSEUM_COPILOT_PAT="<your_token>"
export ALCHEMY_SOLANA_URL="https://solana-mainnet.g.alchemy.com/v2/<your_key>"
export ALCHEMY_ETH_URL="https://eth-mainnet.g.alchemy.com/v2/<your_key>"
```

## Project Structure
```
ak-governor/
├── programs/
│   └── ak-governor/
│       └── src/
│           ├── lib.rs          # Main program entry
│           ├── governor.rs     # Proposal + voting logic
│           └── timelock.rs     # Timelock execution
├── app/
│   ├── src/
│   │   ├── components/
│   │   │   ├── ProposalList.tsx
│   │   │   ├── VotePanel.tsx
│   │   │   └── ExecutionQueue.tsx
│   │   ├── hooks/
│   │   │   ├── useGovernor.ts
│   │   │   └── useWallet.ts
│   │   └── lib/
│   │       └── rpc.ts          # Alchemy RPC client
├── tests/
│   └── ak-governor.ts
├── Anchor.toml
├── CLAUDE.md                   # This file
└── package.json
```

## Common Commands

### Smart Contracts (Anchor)
```bash
anchor build          # Compile programs
anchor test           # Run tests
anchor deploy         # Deploy to devnet
anchor deploy --provider.cluster mainnet  # Deploy to mainnet
```

### Frontend
```bash
cd app
npm install
npm run dev           # Start dev server
npm run build         # Production build
```

### RPC Queries (via Alchemy)
```bash
# Get latest blockhash
curl "$ALCHEMY_SOLANA_URL" \
  --request POST \
  --header 'content-type: application/json' \
  --data '{"id":1,"jsonrpc":"2.0","method":"getLatestBlockhash"}'

# Get account info
curl "$ALCHEMY_SOLANA_URL" \
  --request POST \
  --header 'content-type: application/json' \
  --data '{"id":1,"jsonrpc":"2.0","method":"getAccountInfo","params":["<ADDRESS>"]}'
```

## Architecture

### Governor Flow
```
User creates proposal
  → Governor contract stores on-chain
  → Voting period opens (e.g. 3 days)
  → Token holders vote (for/against/abstain)
  → Quorum reached → Proposal passes
  → Timelock delay (e.g. 48 hours)
  → Anyone can execute
```

### Key Accounts
- `GovernorState` — global config (quorum, voting period, timelock delay)
- `Proposal` — individual proposal (description, votes, status)
- `VoteRecord` — per-user vote (prevents double voting)
- `TimelockQueue` — pending executions

## Claude Code Tips

### Useful prompts to use in `claude`:
```
"Add a new proposal instruction to the governor program"
"Write a React hook to fetch all active proposals from the RPC"
"Generate a test for the timelock delay logic"
"Review my voting math for off-by-one errors"
"Set up Phantom wallet connection in the frontend"
```

### With Colosseum Copilot skill active:
```
"Check my project against Colosseum hackathon requirements"
"What Solana-specific patterns should I follow for governance?"
```

## Grant Milestone Tracking

| # | Deliverable | Status |
|---|---|---|
| M1 | Smart contract core | 🔨 In Progress |
| M2 | Frontend UI | ⏳ Pending |
| M3 | Wallet integration | ⏳ Pending |
| M4 | Open-source release + docs | ⏳ Pending |
| M5 | Community testing + v1.0 | ⏳ Pending |

## Resources
- Solana Docs: https://docs.solana.com
- Anchor Docs: https://anchor-lang.com
- Alchemy Solana API: https://docs.alchemy.com/reference/solana-api
- Grant Application: https://solana.org/grants
- Colosseum Hackathons: https://colosseum.org
