# AgriHedge Platform

A Django-based agricultural risk management platform that brings together commodity price prediction, farmer/buyer workflows, hedging, and blockchain-backed transaction records in one web application.

## Overview

Agricultural commodity prices can change quickly, making it difficult for farmers and buyers to plan their income and costs. This project provides a digital platform for managing that risk through:

- AI/ML-based commodity price insights
- Farmer and buyer accounts
- Hedging and contract workflows
- Wallet and transaction tracking
- Blockchain integration for transparent transactions
- Multilingual application support
- Administrative and monitoring dashboards

The application is designed as a full-stack prototype for exploring how machine learning and blockchain can be combined to improve transparency and risk management in agricultural markets.

## Key Features

### Farmer Module
- Farmer registration and account management
- Crop and contract management
- Hedging workflows
- Market-price and profit/loss tracking
- Wallet-related operations

### Buyer Module
- Buyer account management
- Contract and hedge management
- Matching workflows
- Position and profit/loss monitoring

### AI/ML
The project includes trained models and processed datasets for selected commodities, including:

- Groundnut
- Mustard
- Soybean

These models can be used to generate commodity-price-related predictions and support decision-making.

### Blockchain
The blockchain layer contains integrations for:

- Web3 connectivity
- Token operations
- Forward-sale contracts
- Hedging contracts
- IPFS/Pinata-based data storage

Blockchain functionality is separated into its own application package to keep the web application and decentralized components organized.

### Dashboard & Administration
The project includes dedicated views and dashboards for managing users, contracts, hedges, transactions, and other platform data.

### Multilingual Support
The application includes Django translation infrastructure and language-related middleware/templates to support a multilingual user experience.

## Technology Stack

| Layer | Technology |
|---|---|
| Backend | Python, Django |
| Frontend | HTML, CSS, JavaScript, Django Templates |
| Database | MySQL |
| Machine Learning | Python ML models |
| Blockchain | Web3 / Smart Contracts |
| Decentralized Storage | IPFS / Pinata |
| Authentication | Django Authentication |
| Configuration | Environment Variables |

## Project Structure

```text
project/
├── accounts/             # User accounts and profiles
├── buyers/               # Buyer workflows
├── farmers/              # Farmer workflows
├── core/                 # Core models, matching, ML and platform logic
├── blockchain/           # Web3, token, contract and IPFS integrations
├── panel/                # Dashboard/panel functionality
├── krushi_portal/        # Django project configuration
├── templates/            # HTML templates
├── static/               # CSS and images
├── manage.py              # Django management entry point
├── requirements.txt      # Python dependencies
└── README.md
```

## Getting Started

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd <your-project-folder>
```

### 2. Create a virtual environment

Windows:

```bash
python -m venv venv
venv\Scripts\activate
```

macOS/Linux:

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Create a local `.env` file and provide the values required by your development environment.

Example:

```env
WEB3_RPC_URL=your_rpc_url
WEB3_PRIVATE_KEY=your_private_key
WEB3_PUBLIC_ADDRESS=your_public_address

ERC20_TOKEN_ADDRESS=your_token_contract
FORWARD_CONTRACT_ADDRESS=your_forward_contract
HEDGE_CONTRACT_ADDRESS=your_hedge_contract

PINATA_JWT=your_pinata_jwt
```

Do not commit `.env` to GitHub.

### 5. Configure the database

The project is configured to use MySQL.

Create a database and update your local Django database configuration with your own credentials. Never commit database passwords or API credentials.

### 6. Apply migrations

```bash
python manage.py migrate
```

### 7. Create an administrator account

```bash
python manage.py createsuperuser
```

### 8. Start the development server

```bash
python manage.py runserver
```

Then open:

```text
http://127.0.0.1:8000/
```

## Security Notes

Before publishing this project publicly, check the repository for sensitive information.

Do **not** commit:

- `.env` files
- Private blockchain keys
- API tokens
- Email passwords/app passwords
- Database passwords
- Production Django secret keys
- Personal user data
- Local SQLite/database files containing real data

A `.gitignore` file should be used to prevent accidental uploads.

Example:

```gitignore
.env
venv/
__pycache__/
*.pyc
*.sqlite3
.DS_Store
```

For production, move all secrets to environment variables or a dedicated secret-management system and set Django's `DEBUG` setting appropriately.

## Machine Learning Models

The repository contains model artifacts and processed datasets for selected agricultural commodities.

The ML component is intended to support price-analysis and decision-support features rather than provide guaranteed market forecasts. Predictions should therefore be treated as informational outputs and not as financial guarantees.

## Blockchain Architecture

The blockchain component is organized around reusable Python modules for interacting with deployed contracts.

The integration includes:

1. Web3 provider configuration
2. Token-related operations
3. Forward-sale contract interactions
4. Hedging contract interactions
5. IPFS/Pinata integration
6. Contract ABI files

Contract addresses, RPC endpoints, and private keys should always be supplied through environment variables.

## Development

Useful Django commands:

```bash
python manage.py check
python manage.py makemigrations
python manage.py migrate
python manage.py runserver
```

To run the project's tests:

```bash
python manage.py test
```

## Current Scope

This repository represents a development/prototype implementation. Some integrations, including blockchain services, external APIs, email services, and trained ML models, require additional configuration before the complete application can run in another environment.

## Future Improvements

Potential improvements include:

- Improved model evaluation and retraining pipelines
- Real-time commodity market data
- Better risk analytics and visualization
- More robust smart-contract testing
- Automated deployment
- Containerized development with Docker
- Stronger production security configuration
- Expanded multilingual coverage
- Automated CI/CD testing

## License

Add the license that applies to your project before publishing the repository.

If this code is being redistributed with permission from the original author/team, make sure the repository's license and attribution requirements are respected.

## Acknowledgements

This project builds on open-source technologies and frameworks including Django, Python, Web3 tooling, MySQL, and IPFS-related services.
