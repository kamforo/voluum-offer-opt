# Offer Optimization

Maximize EPV (Earnings Per Visit) with risk-adjusted offer weights. This tool analyzes conversion data and recommends optimal weights for offers within a path, using stability analysis and portfolio optimization techniques.

## Web Interface

Open `index.html` in your browser - no installation required.

## Features

### Step 1: Upload Data
- Upload CSV with conversion data
- Auto-detect columns for path, offer, date, visits, clicks, conversions, revenue
- Preview data and configure column mapping

### Step 2: Configure Analysis
- Select path to optimize
- Choose risk tolerance:
  - **Conservative**: Max 30% per offer, heavy diversification
  - **Balanced**: Max 50% per offer, stability-weighted
  - **Aggressive**: Max 70% per offer, favor top performers

### Step 3: Results
View optimization results including:
- Path name/ID header
- Offer performance table with: Visits, Clicks, Conversions, Revenue, EPV
- Stability score and volatility indicator
- Trend detection (improving/stable/declining)
- Yesterday's traffic share vs suggested weight
- Expected EPV improvement
- Visual charts comparing current vs suggested weights
- Export to CSV

## Optimization Algorithm

### Stability Analysis
- Calculates EPV variance over time (coefficient of variation)
- Detects performance trends (comparing recent vs historical)
- Identifies gaps/pauses in offer activity
- Scores each offer 0-100 for reliability

### Weight Optimization
- Risk-adjusted scoring based on EPV and stability
- Portfolio diversification to protect against sudden offer issues
- Minimum weights to maintain data flow
- Maximum weight caps based on risk level and stability
- Constraints ensure weights sum to 100%

### Recency Weighting
- Recent data weighted more heavily when statistically significant
- Falls back to longer-term data for low-volume offers

## Data Format

Expected CSV columns:
- **Path ID/Name**: Identifies the traffic path
- **Offer ID/Name**: Identifies offers within paths
- **Date**: For time-based analysis
- **Visits**: Traffic volume
- **Clicks**: Click count (optional)
- **Conversions**: Conversion/lead count
- **Revenue**: Revenue amount

## Why Stability Matters

Offers can be unstable:
- Payout changes without notice
- Caps reached mid-day
- Sudden pauses
- Inconsistent conversion rates

This tool accounts for these risks by:
1. Limiting concentration on volatile offers
2. Maintaining diversification
3. Flagging declining/unstable offers
4. Adjusting weights based on reliability history
