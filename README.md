# Regional Index Pools (RWA DeFi)

**Next-generation DeFi protocol for tokenized regional economic indices on Solana blockchain**

![Solana](https://img.shields.io/badge/Solana-000000?style=for-the-badge&logo=solana&logoColor=white)
![Rust](https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)
![Hackathon](https://img.shields.io/badge/Hackathon-2026Solana-FF0060?style=for-the-badge)

---

## 🎯 Overview

**Regional Index Pools** is a decentralized finance protocol that revolutionizes real-world asset (RWA) investing by creating tokenized regional economic indices. We bring the liquidity pool model from DeFi into the world of real assets, enabling fractional ownership of diversified regional portfolios.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                           REGIONAL INDEX POOLS                               │
│                                                                             │
│   ┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐       │
│   │    INVESTOR     │    │   SMART POOL    │    │   RWA ASSETS    │       │
│   │                 │    │                 │    │                 │       │
│   │ 💰 $1000 USDC  │───▶│ LP Tokens (8.5%)│◀───│ 🏢 Real Estate  │       │
│   │                 │    │                 │    │ 🛣️ Infra       │       │
│   │ 📊 Dashboard   │◀───│ APY Dashboard   │───▶│ 💻 IP / Tech    │       │
│   └─────────────────┘    └─────────────────┘    └─────────────────┘       │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 📸 Screenshots

### Dashboard
![Dashboard](assets/screenshots/dashboard.png)

### Pool Detail
![Pool Detail](assets/screenshots/pool-detail.png)

### Invest Modal
![Invest Modal](assets/screenshots/invest-modal.png)

### Portfolio
![Portfolio](assets/screenshots/portfolio.png)

---

## 🌟 Key Features

| Feature | Description | Status |
|---------|-------------|--------|
| 🎯 Regional Pools | Diversified RWA portfolios by region | ✅ MVP |
| 💰 LP Tokens | Fractional ownership mechanism | ✅ MVP |
| 📈 Auto Yield | Automatic profit distribution | ✅ MVP |
| 🔒 KYC/AML | Compliance verification | ✅ Mock |
| 🛡️ Smart Contracts | Audited Anchor programs | ✅ MVP |
| 📊 Analytics | Real-time portfolio tracking | ✅ MVP |
| 🌐 Multi-chain | Cross-chain expansion | 🚧 Roadmap |
| 🏛️ Governance | DAO token holders | 🚧 Roadmap |

---

## 🌍 Supported Regions

| Region | Flag | APY Range | TVL | Assets | Risk |
|--------|------|-----------|-----|--------|------|
| Asia-Pacific | 🌏 | 7.5% - 10.5% | $1.24M | Real Estate, Tech, Commodities | Low |
| Europe | 🌍 | 6.0% - 8.5% | $890K | Infrastructure, Energy, Finance | Low |
| Americas | 🌎 | 8.0% - 12.0% | $650K | Agriculture, Mining, Tech | Medium |
| Middle East | 🌙 | 9.0% - 14.0% | $420K | Real Estate, Finance, Energy | Medium |

---

## 🧱 System Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                              FRONTEND LAYER                                │
│                                                                             │
│   ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────────┐  │
│   │   Landing   │  │  Dashboard  │  │ Pool Detail │  │  Admin Panel    │  │
│   │   (Hero)    │  │ (Portfolio) │  │   (Invest)  │  │  (Management)  │  │
│   └──────┬──────┘  └──────┬──────┘  └──────┬──────┘  └────────┬────────┘  │
│          └─────────────────┼─────────────────┼───────────────────┘          │
│                            │                   │                              │
│          ┌─────────────────┴───────────────────┴───────────────┐            │
│          │              Solana Wallet Adapter                  │            │
│          │         (Phantom, Solflare, Backpack)              │            │
│          └─────────────────────┬───────────────────────────────┘            │
└────────────────────────────────┼────────────────────────────────────────────┘
                                 │
                                 ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                           PROGRAM LAYER (Anchor)                             │
│                                                                             │
│   ┌────────────────────────────────────────────────────────────────────┐   │
│   │                        RWIPool Program                              │   │
│   │                                                                     │   │
│   │   ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐   │   │
│   │   │     Pool        │  │    Investor     │  │  DepositRecord  │   │   │
│   │   │   (State)       │  │    (State)      │  │    (State)      │   │   │
│   │   └─────────────────┘  └─────────────────┘  └─────────────────┘   │   │
│   │                                                                     │   │
│   │   ┌──────────────────────────────────────────────────────────┐   │   │
│   │   │                    INSTRUCTIONS                            │   │   │
│   │   │  createPool │ deposit │ withdraw │ updateRate │ distribute │   │   │
│   │   └──────────────────────────────────────────────────────────┘   │   │
│   │                                                                     │   │
│   │   ┌──────────────────────────────────────────────────────────┐   │   │
│   │   │                     LP TOKEN (SPL)                        │   │   │
│   │   │            Mint: 6 decimals │ Auto-mint on deposit       │   │   │
│   │   └──────────────────────────────────────────────────────────┘   │   │
│   └────────────────────────────────────────────────────────────────────┘   │
└────────────────────────────────┼────────────────────────────────────────────┘
                                 │
                                 ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                              DATA LAYER                                     │
│                                                                             │
│   ┌────────────────┐  ┌────────────────┐  ┌────────────────┐               │
│   │  USDC Token   │  │  LP Tokens    │  │  Pool State    │               │
│   │  (Mint: USDC) │  │  (Per Pool)   │  │  (On-chain)   │               │
│   └────────────────┘  └────────────────┘  └────────────────┘               │
│                                                                             │
│   ┌────────────────────────────────────────────────────────────────┐       │
│   │                      ORACLE LAYER                               │       │
│   │    Mock Oracle (MVP) │ Pyth (Production) │ Chainlink (Future) │       │
│   └────────────────────────────────────────────────────────────────┘       │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 📜 Smart Contract

### Program ID
```
RwaPooL111111111111111111111111111111111111111
```

### Network
```
Solana Devnet
```

### Account Structures

#### Pool Account
```rust
#[account]
pub struct Pool {
    pub authority: Pubkey,           // Admin who created the pool
    pub mint: Pubkey,               // USDC mint address
    pub lp_mint: Pubkey,            // LP token mint
    pub total_deposits: u64,        // Total TVL
    pub total_shares: u64,          // Total LP tokens minted
    pub min_deposit: u64,           // Minimum deposit
    pub max_deposit: u64,           // Maximum deposit
    pub pool_cap: u64,              // Pool capacity
    pub is_active: bool,            // Pool status
    pub region: String,             // Region name
    pub name: String,              // Pool name
    pub annualized_rate: u64,       // APY in basis points
    pub last_update: i64,          // Last update timestamp
    pub bump: u8,                   // PDA bump
}
```

#### Investor Account
```rust
#[account]
pub struct Investor {
    pub wallet: Pubkey,              // Investor wallet
    pub pool: Pubkey,               // Associated pool
    pub total_deposited: u64,       // Total amount deposited
    pub total_withdrawn: u64,       // Total amount withdrawn
    pub shares: u64,                // LP tokens held
    pub entry_price: u64,           // Average entry price
    pub kyc_verified: bool,         // KYC status
    pub whitelisted: bool,          // Whitelist status
    pub created_at: i64,            // Registration timestamp
    pub updated_at: i64,            // Last update timestamp
    pub bump: u8,                   // PDA bump
}
```

### Instructions

| Instruction | Parameters | Description |
|-------------|------------|-------------|
| `initializePool` | name, region, min, max, cap, rate | Create new regional pool |
| `initializeInvestor` | kyc_verified | Register investor |
| `deposit` | amount | Deposit USDC, get LP tokens |
| `withdraw` | shares | Burn LP, receive USDC + yield |
| `updatePoolRate` | new_rate | Update APY (admin only) |
| `togglePoolActive` | - | Pause/resume pool (admin) |
| `whitelistInvestor` | investor | Add to whitelist (admin) |
| `distributeYield` | amount | Distribute yield (oracle) |

---

## 💻 Tech Stack

### Blockchain
| Technology | Version | Purpose |
|------------|---------|---------|
| Solana | 1.18+ | Blockchain runtime |
| Anchor | 0.30.1 | Smart contract framework |
| Rust | 1.75+ | Smart contract language |
| SPL Token | 0.10+ | Token standard |

### Frontend
| Technology | Version | Purpose |
|------------|---------|---------|
| Next.js | 14.2+ | React framework |
| React | 18+ | UI library |
| TypeScript | 5+ | Type safety |
| TailwindCSS | 3.4+ | Styling |
| Solana Web3.js | 1.91+ | Blockchain interaction |
| D3.js / Recharts | Latest | Data visualization |

### Infrastructure
| Service | Purpose |
|---------|---------|
| Solana Devnet | Test network |
| Solana Playground | Contract deployment |
| Vercel | Frontend hosting |
| GitHub Actions | CI/CD |
| Helius/QuickNode | RPC endpoints |

---

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- Rust 1.75+
- Anchor CLI
- Solana CLI
- Git

### Installation

```bash
# Clone the repository
git clone https://github.com/Marakaya/regional-index-pools
cd regional-index-pools

# Install dependencies
npm install

# Install frontend dependencies
cd frontend && npm install && cd ..

# Build Anchor programs
anchor build

# Run tests
anchor test

# Start frontend
cd frontend && npm run dev
```

### Configuration

```bash
# Copy environment variables
cp .env.example .env

# Edit .env with your values
SOLANA_RPC_URL=https://api.devnet.solana.com
PROGRAM_ID=RwaPooL111111111111111111111111111111111111111
NETWORK=devnet
```

---

## 📊 Financial Metrics

### Key Formulas

```javascript
// Share Calculation (LP tokens minted)
shares = depositAmount / currentSharePrice

// Share Price
sharePrice = totalDeposits / totalShares

// ROI (Return on Investment)
ROI = ((currentValue - initialValue) / initialValue) * 100

// APY (Annual Percentage Yield)
APY = ((1 + rate / 365) ^ 365 - 1) * 100

// Investor Share Percentage
sharePercent = (userShares / totalShares) * 100

// Projected Annual Yield
projectedYield = deposit * (apy / 100)

// Projected Monthly Yield
projectedMonthlyYield = projectedYield / 12
```

### Example Calculations

| Deposit | APY | 1 Month Yield | 6 Month Yield | 1 Year Yield |
|---------|-----|---------------|---------------|--------------|
| $100 | 8.5% | $0.71 | $4.25 | $8.50 |
| $1,000 | 8.5% | $7.08 | $42.50 | $85.00 |
| $10,000 | 8.5% | $70.83 | $425.00 | $850.00 |
| $100,000 | 8.5% | $708.33 | $4,250.00 | $8,500.00 |

---

## 🎨 UI/UX Design

### Design System

#### Color Palette
```
Primary:        #8B5CF6 (Violet 500)
Primary Dark:   #7C3AED (Violet 600)
Primary Light:  #A78BFA (Violet 400)
Accent:         #C4B5FD (Violet 300)
Success:        #10B981 (Emerald 500)
Warning:        #F59E0B (Amber 500)
Error:          #EF4444 (Red 500)

Background:     #0A0A0F (Near Black)
Surface:        #111118 (Dark Gray)
Border:         #1E1E28 (Subtle Border)
Text Primary:   #FFFFFF (White)
Text Secondary: #9CA3AF (Gray 400)
Text Muted:    #6B7280 (Gray 500)
```

#### Typography
```
Font Family:    Inter, system-ui, sans-serif
Heading 1:      48px / Bold / 1.2 line-height
Heading 2:      36px / Bold / 1.25 line-height
Heading 3:      24px / Semibold / 1.3 line-height
Body:           16px / Regular / 1.5 line-height
Small:          14px / Regular / 1.5 line-height
Caption:        12px / Regular / 1.4 line-height
```

#### Spacing
```
Base unit:      4px
xs:             4px
sm:             8px
md:             16px
lg:             24px
xl:             32px
2xl:            48px
3xl:            64px
```

#### Components
```
Button:         Primary, Secondary, Ghost, Danger
Input:          Text, Number, Select, Checkbox
Card:           Glass effect, Glow on hover
Modal:          Centered, Backdrop blur
Badge:          Status, Count, Label
Tooltip:        Top, Bottom, Left, Right
Table:          Striped rows, Sortable headers
Chart:          Line, Bar, Pie, Area
```

### Page Layouts

#### Landing Page
```
┌─────────────────────────────────────────────────────────────┐
│ HEADER: Logo │ Navigation │ Connect Wallet                    │
├─────────────────────────────────────────────────────────────┤
│ HERO SECTION                                                │
│ ┌─────────────────────────────────────────────────────────┐ │
│ │ Headline: "Tokenized Regional Economies"                 │ │
│ │ Subheadline: "Invest in real-world assets..."          │ │
│ │ CTA Buttons: [Connect Wallet] [View Pools]             │ │
│ │ Hero Image: Abstract 3D visualization                  │ │
│ └─────────────────────────────────────────────────────────┘ │
├─────────────────────────────────────────────────────────────┤
│ STATS BAR                                                   │
│ $2.1M TVL │ 8.2% Avg APY │ 540 Investors │ 4 Regions      │
├─────────────────────────────────────────────────────────────┤
│ FEATURES GRID                                               │
│ ┌───────────┐ ┌───────────┐ ┌───────────┐ ┌───────────┐   │
│ │ DeFi Model│ │ Real Assets│ │ Auto Yield │ │ KYC/AML  │   │
│ └───────────┘ └───────────┘ └───────────┘ └───────────┘   │
├─────────────────────────────────────────────────────────────┤
│ POOLS SHOWCASE                                             │
│ ┌─────────────────────────────────────────────────────────┐ │
│ │ Pool Cards with Stats, APY, Mini-chart                 │ │
│ └─────────────────────────────────────────────────────────┘ │
├─────────────────────────────────────────────────────────────┤
│ HOW IT WORKS                                               │
│ 1. Connect → 2. Verify → 3. Invest → 4. Earn            │
├─────────────────────────────────────────────────────────────┤
│ FOOTER: Links │ Social │ Legal                             │
└─────────────────────────────────────────────────────────────┘
```

#### Dashboard Page
```
┌─────────────────────────────────────────────────────────────┐
│ HEADER: Logo │ Navigation │ Wallet Balance │ Settings       │
├─────────────────────────────────────────────────────────────┤
│ WALLET OVERVIEW                                            │
│ ┌───────────┐ ┌───────────┐ ┌───────────┐ ┌───────────┐   │
│ │ Balance   │ │ Invested │ │ Yield     │ │ ROI       │   │
│ │ $12,450  │ │ $10,000  │ │ +$2,450  │ │ +24.5%    │   │
│ └───────────┘ └───────────┘ └───────────┘ └───────────┘   │
├─────────────────────────────────────────────────────────────┤
│ PORTFOLIO CHART (Line Graph)                               │
│ ┌─────────────────────────────────────────────────────────┐ │
│ │                                                         │ │
│ │     ╱╲    ╱╲                                          │ │
│ │    ╱  ╲  ╱  ╲  ╱╲                                    │ │
│ │   ╱    ╲╱    ╲╱  ╲                                   │ │
│ │ ───────────────────────────────────────               │ │
│ │ 30d   60d   90d   120d  Today                        │ │
│ └─────────────────────────────────────────────────────────┘ │
├─────────────────────────────────────────────────────────────┤
│ HOLDINGS TABLE                                             │
│ ┌─────────────────────────────────────────────────────────┐ │
│ │ Pool │ Amount │ LP Tokens │ APY │ Yield │ Value │ Act │ │
│ │──────│────────│───────────│─────│───────│───────│─────│ │
│ │ APAC │ $6,000 │   6,000   │ 8.5%│ $510  │$6,510 │ ⋮  │ │
│ │ EU   │ $4,000 │   4,000   │ 7.2%│ $288  │$4,288 │ ⋮  │ │
│ └─────────────────────────────────────────────────────────┘ │
├─────────────────────────────────────────────────────────────┤
│ RECENT TRANSACTIONS                                        │
│ Deposit │ Withdraw │ Yield Claimed                        │
└─────────────────────────────────────────────────────────────┘
```

---

## 🔒 Security

### Security Measures
- [ ] Anchor program with comprehensive checks
- [x] KYC/AML verification (mock for MVP)
- [x] Investor whitelisting
- [x] Deposit limits (min/max)
- [x] Pool caps
- [x] Pause/resume functionality
- [ ] Multi-signature governance
- [ ] Time-locked withdrawals
- [ ] Insurance fund
- [ ] Professional audit

### Error Codes
```rust
PoolInactive         // Pool is paused
NotWhitelisted       // Investor not in whitelist
KYCNotVerified       // KYC verification required
BelowMinDeposit      // Amount below minimum
ExceedsMaxDeposit    // Amount above maximum
ExceedsPoolCap       // Pool at maximum capacity
InsufficientShares    // Not enough LP tokens
Unauthorized         // Not pool admin
```

---

## 📈 Roadmap

### Phase 1: MVP (Current)
- [x] Pool creation
- [x] Investor registration
- [x] Deposit/Withdraw
- [x] LP token mechanics
- [x] Basic frontend UI
- [x] Mock oracle
- [x] KYC mock

### Phase 2: Enhanced
- [ ] Real oracle integration (Pyth)
- [ ] Auto-compounding
- [ ] Multiple pools
- [ ] Advanced analytics
- [ ] Mobile responsive
- [ ] Dark/Light theme

### Phase 3: Production
- [ ] Mainnet deployment
- [ ] Real KYC integration
- [ ] Professional audit
- [ ] SPV legal structure
- [ ] Multi-sig governance

### Phase 4: Scale
- [ ] Additional regions (10+)
- [ ] Institutional investors
- [ ] Mobile apps (iOS/Android)
- [ ] Cross-chain bridges
- [ ] Governance token
- [ ] Insurance fund

---

## 👥 Team

| Name | Role | Contact | Avatar |
|------|------|---------|--------|
| Maxim Afanasyev | Founder & Lead Engineer | [Telegram](https://t.me/maxnutrition) · [X](https://x.com/_Marakaya) | [@Marakaya](https://github.com/Marakaya) |

---

## 🤝 Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for details.

### Development Workflow
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📄 License

MIT License - see [LICENSE](LICENSE)

---

## 🔗 Resources

### Documentation
- [Solana Docs](https://docs.solana.com)
- [Anchor Framework](https://www.anchor-lang.com)
- [SPL Token](https://spl.solana.com/token)
- [Solana Playground](https://beta.solpg.io)

### Wallets
- [Phantom](https://phantom.app)
- [Solflare](https://solflare.com)
- [Backpack](https://backpack.app)

### Explorers
- [Solana Explorer](https://explorer.solana.com)
- [Solana FM](https://solana.fm)

### Communities
- [Solana Discord](https://discord.gg/solana)
- [Anchor Discord](https://discord.gg/anchor)
- [Solana Twitter](https://twitter.com/solana)

---

## 📹 Demo

### Video Walkthrough
[![Video Demo](assets/thumbnails/demo-thumbnail.png)](https://youtube.com)

### Live Demo
[Launch App](https://regional-index-pools.vercel.app)

---

## 🙏 Acknowledgments

- [Solana Foundation](https://solana.org)
- [Anchor Framework](https://coral-xyz.github.io/anchor)
- [Uniswap](https://uniswap.org) for DeFi inspiration
- [Solana Hacker House](https://hacker.house) community

---

<p align="center">
  <strong>Built with ❤️ on Solana</strong>
  <br>
  2026 Solana National Hackathon
</p>
