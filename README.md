# CS 335 — Assignment 01: Working with AI & ML APIs
**Northeastern Illinois University — Introduction to Artificial Intelligence**  
By: Hiran Koshy 

---

| Field | Value |
|-------|-------|
| API Used | CoinGecko — Cryptocurrency Market Data |
| Docs | https://docs.coingecko.com |
| Auth | Free Demo API key (`x-cg-demo-api-key` header) |

---

## API Calls Implemented

| # | Function | Endpoint | Description |
|---|----------|----------|-------------|
| 1 | `call_one_get()` | `GET /simple/price` | Current USD/EUR prices + 24h % change for 4 coins |
| 2 | `call_two_post()` | `GET /coins/markets` | Top 10 coins ranked by market cap (table view) |
| 3 | `call_three_parameterized(coin)` | `GET /coins/{id}` | Deep profile for any coin: ATH, supply, genesis date |

---

## Step-by-Step Setup

### Step 1 — Clone the Course Repo
```bash
git clone https://github.com/osindy/NEIU335AI.git
cd NEIU335AI/assignments/assignment-01-api
```

### Step 2 — Create a Virtual Environment
```bash
# macOS / Linux
python3 -m venv venv
source venv/bin/activate

# Windows
python -m venv venv
venv\Scripts\activate
```

### Step 3 — Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4 — Set Up Your API Key
```bash
cp .env.example .env   # macOS/Linux
copy .env.example .env # Windows
```
Open `.env` and set:
```
MY_API_KEY=your_coingecko_demo_key_here
```
Get a free Demo key at: https://www.coingecko.com/en/api/pricing

> **Important:** Never commit your `.env` file — it is covered by `.gitignore`.

### Step 5 — Run the Script
```bash
python starter.py
```

### Step 6 — Push to GitHub
```bash
git remote set-url origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git add .
git commit -m "Assignment 01 — CoinGecko API implementation"
git push -u origin main
```

---

## Sample Terminal Output

```
==================================================
CALL 1 — GET Current Prices
==================================================

  BITCOIN
    Price (USD):   $94,210.0000
    Price (EUR):   €87,330.0000
    24h Change:    +2.41%
    Market Cap:    $1,862,445,123,456

  ETHEREUM
    Price (USD):   $3,210.5000
    Price (EUR):   €2,974.2000
    24h Change:    -0.72%
    Market Cap:    $385,234,987,654

  SOLANA
    Price (USD):   $172.3000
    Price (EUR):   €159.6000
    24h Change:    +1.05%
    Market Cap:    $81,234,567,890

  DOGECOIN
    Price (USD):   $0.1823
    Price (EUR):   €0.1688
    24h Change:    +3.12%
    Market Cap:    $26,789,012,345

==================================================
CALL 2 — GET Top 10 Coins by Market Cap
==================================================

  Rank  Symbol   Name            Price (USD)      24h %      Market Cap
  ---- ------- -------------- --------------- --------- --------------------
  1     BTC      Bitcoin         $94,210.00       +2.41%    $1,862,445,123,456
  2     ETH      Ethereum        $3,210.50        -0.72%    $  385,234,987,654
  3     USDT     Tether          $1.00            +0.01%    $  140,123,456,789
  4     BNB      BNB             $612.30          +0.88%    $   89,234,567,890
  5     SOL      Solana          $172.30          +1.05%    $   81,234,567,890

==================================================
CALL 3 — GET Coin Detail  |  coin: 'ethereum'
==================================================

  Name:               Ethereum (ETH)
  Market Cap Rank:    #2
  Genesis Date:       2015-07-30
  Description:        Ethereum is a decentralized open-source blockchain system.
  Current Price:      $3,210.50
  All-Time High:      $4,878.26 (on 2021-11-10)
  All-Time Low:       $0.4209
  Circulating Supply: 120,272,341 ETH
```

---

## Folder Structure

```
NEIU335AI/
├── .gitignore
├── README.md
└── assignments/
    └── assignment-01-api/
        ├── starter.py       ← Completed API script
        ├── .env.example     ← Copy to .env and add your key
        ├── requirements.txt
        └── README.md        ← This file
```
---

## Resources

| Resource | Link |
|---|---|
| CoinGecko API Docs | docs.coingecko.com |
| Free Public APIs | github.com/public-apis/public-apis |
| Python Requests Docs | docs.python-requests.org |
| python-dotenv | pypi.org/project/python-dotenv |
