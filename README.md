# 🔍 Enhanced Wallet Risk Scoring System

A comprehensive blockchain wallet risk assessment tool that analyzes Ethereum wallets for DeFi lending protocols, with special focus on Compound Protocol interactions.

## 🚀 Overview

This system performs multi-dimensional risk analysis of Ethereum wallets by examining transaction patterns, DeFi engagement, and behavioral indicators. It provides actionable risk scores (0-1000) with categorical classifications to help assess wallet creditworthiness and potential default risk.

## ✨ Key Features

- **Comprehensive Risk Assessment**: 6-component risk model covering liquidation, volatility, concentration, activity, leverage, and liquidity risks
- **Multi-Protocol Support**: Analyzes interactions with Compound, Uniswap, Aave, MakerDAO, and other major DeFi protocols
- **Scalable Architecture**: Batch processing with error handling and progress tracking
- **Inactive Wallet Handling**: Specialized scoring for wallets with limited or no transaction history
- **Real-time Data**: Integrates with Etherscan API for live blockchain data
- **Comprehensive Output**: Detailed CSV reports with individual risk component scores

## 📊 Risk Score Categories


| Score Range | Category   | Description                                             |
|-------------|------------|---------------------------------------------------------|
| 0–150       | Very Low   | Highly reliable wallets with strong DeFi engagement     |
| 151–350     | Low        | Generally safe wallets with good activity patterns      |
| 351–550     | Medium     | Moderate risk requiring standard monitoring             |
| 551–750     | High       | Elevated risk requiring enhanced scrutiny               |
| 751–1000    | Very High  | High‑risk wallets requiring careful evaluation          |


## 🏗️ Installation

### Prerequisites
- Python 3.8+
- Etherscan API key

### Setup
```bash
# Clone the repository
git clone https://github.com/Adithipawar/wallet-risk-scorer.git

# Install dependencies
pip install pandas numpy requests

# Set your API key in the code
API_KEY = "your_etherscan_api_key_here"
```

## 📈 Output Format

The system generates comprehensive CSV reports with the following columns:


| Column                  | Description                                         |
|-------------------------|-----------------------------------------------------|
| `wallet_address`        | Ethereum wallet address                             |
| `risk_score`            | Overall risk score (0‑1000)                         |
| `risk_category`         | Risk category (Very Low to Very High)               |
| `eth_balance`           | Current ETH balance                                 |
| `total_tx_count`        | Total transaction count                             |
| `analyzed_transactions` | Number of transactions analyzed                     |
| `compound_transactions` | Compound protocol interactions                      |
| `defi_transactions`     | Total DeFi protocol interactions                    |
| `engagement_score`      | DeFi engagement metric (0‑1)                        |
| `is_active_wallet`      | Activity status boolean                             |
| `liquidation_risk_score`| Individual risk component: liquidation score        |
| `volatility_risk_score` | Individual risk component: volatility score         |
| `concentration_risk_score` | Individual risk component: concentration score   |
| `activity_risk_score`   | Individual risk component: activity score           |
| `leverage_risk_score`   | Individual risk component: leverage score           |
| `liquidity_risk_score`  | Individual risk component: liquidity score          |


## 🔧 Configuration

### Risk Component Weights
```python
risk_weights = {
    'liquidation_risk': 0.25,    # Position management quality
    'volatility_risk': 0.20,     # Transaction value stability
    'concentration_risk': 0.15,  # Portfolio diversification
    'activity_risk': 0.15,       # Engagement patterns
    'leverage_risk': 0.15,       # Leverage indicators
    'liquidity_risk': 0.10       # Liquidity management
}
```

### Supported Protocols
- **Compound V2 & V3**: Complete coverage of lending markets
- **Uniswap V2 & V3**: DEX interaction analysis
- **Aave V2 & V3**: Alternative lending protocol tracking
- **MakerDAO**: CDP and stablecoin interactions

## 📚 Documentation

- [Analysis Methodology](analysis.md) - Detailed explanation of scoring logic

- [Output](output/) - Results obtained after executing app.py

## 🔒 Security & Privacy

- **No Private Data**: Only analyzes public blockchain transactions
- **API Rate Limiting**: Respects Etherscan API limits
- **Error Handling**: Graceful failure recovery
- **Data Validation**: Input sanitization and validation

## 🚀 Performance

- **Processing Speed**: ~1.5-2 wallets per second
- **Batch Processing**: Handles 1000+ wallets efficiently
- **Memory Efficient**: Low memory footprint with streaming processing
- **Error Recovery**: Continues processing despite individual failures

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

**⚡ Built for the DeFi ecosystem to enable better risk assessment and lending decisions.**