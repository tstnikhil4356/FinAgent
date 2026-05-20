Multi-Agent Stock Forecasting System via Time Series

About
Fin-Agent is an intelligent multi-agent stock analysis system that monitors stocks for unusual price movements, identifies the news driving them, analyzes market sentiment, forecasts price direction, and generates transparent BUY/HOLD/SELL signals — all while explaining every step of its reasoning in plain English so the user always knows exactly why a decision was made.

How It Works
Fin-Agent runs a 4-agent pipeline where each agent has one job:
[Agent 1: Anomaly Detector]
        ↓
[Agent 2: News Fetcher]
        ↓
[Agent 3: Sentiment Analyzer]
        ↓
[Agent 4: Signal Generator + Explainer]
Agent 1 — Anomaly Detector
Scans price data using Z-score, RSI, Bollinger Bands, and EMA to flag unusual stock movements.
Agent 2 — News Fetcher
Pulls relevant headlines from 6 news APIs the moment an anomaly is detected.
Agent 3 — Sentiment Analyzer
Runs FinBERT (a finance-specific NLP model) on fetched headlines to determine market sentiment.
Agent 4 — Signal Generator
Combines technical anomaly signals + sentiment scores to produce a final BUY/HOLD/SELL decision with confidence threshold and supporting headlines explaining the call.

Stocks Covered
TickerCompanyTSLATeslaNVDANVIDIAAAPLAppleMETAMetaAMZNAmazon

Key Results

+0.089 F1-score improvement over price-only baseline
Anomaly days showed 3.5× higher absolute returns
SHAP & LIME explainability on every signal
Granger causality validation between news sentiment and price movement


Tech Stack
Python | FinBERT | SHAP | LIME | Pandas | NumPy | REST APIs

Features

🔍 Technical anomaly detection (Z-score, RSI, Bollinger Bands, EMA)
📰 Real-time news fetching across 6 APIs
🧠 FinBERT NLP sentiment analysis
📊 Granger causality validation
💡 SHAP & LIME explainability on every decision
🟢 Transparent BUY/HOLD/SELL signals with confidence scores
📝 Plain English reasoning for every call


Project Structure
fin-agent/
│
├── agents/
│   ├── anomaly_detector.py
│   ├── news_fetcher.py
│   ├── sentiment_analyzer.py
│   └── signal_generator.py
│
├── data/
│   └── price_data/
│
├── utils/
│   ├── explainability.py
│   └── granger_test.py
│
├── requirements.txt
└── README.md

⚠️ Adjust the folder structure above to match your actual repo before publishing.


Installation
bashgit clone https://github.com/tstnikhil4356/FinAgent
cd fin-agent
pip install -r requirements.txt

Usage
bashpython main.py --ticker TSLA

Disclaimer

This project is built for educational and research purposes only. It is not financial advice. Do not make real investment decisions based on this system.


Built by Nikhil Singh — MSc Data Science, NMIMS Mumbai
