# Conflux Eliza Starter 🤖

A complete starter template for building Eliza agents with Conflux blockchain integration. This template includes all standard Eliza plugins plus specialized Conflux functionality.

## ✨ Features

### Core Features

- 🤖 Natural language processing
- 🎨 Image generation and description
- 📝 Text generation and analysis
- 🗣️ Speech synthesis and recognition
- 📊 Data visualization
- 🌐 Web browsing capabilities
- 📁 File handling and automation
- ☁️ Cloud storage integration

### Conflux Features

- 💰 Wallet management (Core Space and eSpace)
- 💸 Token transfers (CFX, USDT, etc.)
- 🌉 Cross-space bridging
- 💱 Token swapping via Swappi DEX
- 📊 Price and market data
- 🔍 Transaction tracking

## 🚀 Quick Start

### Prerequisites

- Node.js 23+
- pnpm 9+
- Git

### Installation

```bash
# Clone the repository
git clone https://github.com/0xn1c0/ConfluxElizaStarter
cd ConfluxElizaStarter

# Install dependencies
pnpm install

# Copy environment file
cp .env.example .env
```

### Configuration

Edit `.env` file and add your credentials:

```env
# Required for eSpace operations
CONFLUX_ESPACE_PRIVATE_KEY=your_private_key
CONFLUX_ESPACE_RPC_URL=https://evm.confluxrpc.com

# Required for Core Space operations
CONFLUX_CORE_PRIVATE_KEY=your_private_key
CONFLUX_CORE_RPC_URL=https://main.confluxrpc.com

# Choose an API provder and add the API_KEY on the env file (Choose one and configure it on the character file as well, openai is default)
OPENAI_API_KEY=                 # OpenAI API key, starting with sk-
ANTHROPIC_API_KEY=              # For Claude

# You can add additional clients by adding the env variables and including them in the character file like ["dicord","telegram"].
# Discord Configuration
DISCORD_APPLICATION_ID=
DISCORD_API_TOKEN=              # Bot token

# Telegram Configuration
TELEGRAM_BOT_TOKEN=

# Twitter/X Configuration
TWITTER_DRY_RUN=false
TWITTER_USERNAME=               # Account username
TWITTER_PASSWORD=               # Account password
TWITTER_EMAIL=                  # Account email

```

### Running the Agent

```bash
# Build the Agent
pnpm build

# Start the agent
pnpm start --characters="characters\conflux-dev.character.json"

# In a new terminal, start the client
cd client
pnpm run dev
```

## 💡 Supported Operations

### Token Operations

- Native CFX transfers (Core and eSpace)
- ERC-20 token transfers (USDT, ETH, BTC, USDC) (eSpace only)
- Cross-space bridging (Core to eSpace)
- Token swaps via Swappi DEX (eSpace only)

### Network Support

- Conflux Core Space
- Conflux eSpace
- Cross-space operations

### Supported Tokens (eSpace only)

- CFX (Native token)
- USDT
- ETH
- BTC


### Token Transfers

```
Send 0.00001 USDT to 0x092618c68f6A87615b02484adE2BC92D7716AB15 on eSpace
```

```
Send 0.0000000001 BTC to 0x092618c68f6A87615b02484adE2BC92D7716AB15 on eSpace
```

## 🔍 Important Notes

### Address Formats

- eSpace: Use `0x` addresses
- Core Space: Use `cfx:` addresses
- For bridging:
    - Core to eSpace: destination must be `0x` address
    - eSpace to Core: destination must be `cfx:` address

### Transaction Tips

- Always include enough CFX for gas fees
- Bridge operations may take a few minutes
- Swaps have a default 0.5% slippage tolerance

## 🛠️ Development

### Project Structure


### Adding New Features

1. Create new actions in `packages/plugin-conflux/src/actions/`
2. Register them in `packages/plugin-conflux/src/index.ts`
3. Add types in `packages/plugin-conflux/src/types/`
4. Update tests in `packages/plugin-conflux/tests/`

## 📚 Resources

- [Eliza Documentation](https://elizaos.github.io/eliza/)
- [Conflux Documentation](https://developer.confluxnetwork.org/)
- [Swappi DEX Docs](https://docs.swappi.io/)

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## 📄 License

MIT
