# Polyshark Card Generator v1.2.0

**Standalone Python card generator for Polymarket whale alerts.**

## Overview

Generates v1.2 formatted cards for Polymarket alerts:
- 🏅 Whale badge (inline with question)
- 💵 Stack of bills = trade Size
- 🐋 Whale emoji for wallet addresses
- ⛓️ Chains emoji for links
- 🟢🟠🔴 Win rate color badges
- n=XX for trade count

## Usage

```python
from standalone_card_generator import (
    generate_win_card,
    generate_loss_card,
    generate_free_teaser,
    generate_consolidated_card
)

# WIN card
card = generate_win_card(
    market_question="Will BTC exceed $100K by June 2026?",
    direction="UP",
    outcome="YES",
    entry_price=0.442,
    stake=2900000,
    profit=3704561,
    roi=127,
    lifetime_wr=71,
    wr_30d=73,
    trade_count=47,
    streak=8,
    size=2900000,
    opened="Apr 15",
    closes="Jun 30",
    polymarket_url="https://polymarket.com/event/btc-100k-june-2026",
    wallet_address="0xa5cB1234567890abcdef1234567890abcdef12",
    is_high_priority=True,
    confidence=87
)
print(card)
```

## Card Types

| Function | Purpose |
|----------|---------|
| `generate_win_card()` | WIN alerts — green positive formatting |
| `generate_loss_card()` | LOSS alerts — red negative formatting |
| `generate_free_teaser()` | Free tier — stripped format, no profit/ROI |
| `generate_consolidated_card()` | Same wallet + same market — combined metrics |

## v1.2 Format Spec

```
🎯 Will BTC exceed $100K by June 2026?  🏅 HIGH-FREQ WINNING WHALE 🏅

💰 +$3,704,561 | ✅ +127% ROI
⬆️ BET UP on YES

🏆 🟢 71+% lifetime WR | 🔥🔥 8-win streak
📊 73% WR (30d) | n=47

💰 Profit: +$3,704,561 | 💵 Size: $2,900,000
⏰ Opened: Apr 15 | Closes: Jun 30 | Resolved: —
⛓️ https://polymarket.com/event/btc-100k-june-2026
🐋 0xa5cB1...cdef12
[Confidence: 87%]
```

## Emoji Key

| Emoji | Meaning |
|-------|---------|
| 💵 | Stack of bills = trade SIZE |
| 💰 | Money bag = Profit/Loss |
| 💲 | Stop sign = negative ROI |
| ✅ | Green check = positive |
| 🏅 | Whale badge (inline) |
| ⛓️ | Chains = hyperlink |
| 🐋 | Whale = wallet address |
| 🟢 | Green badge = WR ≥65% |
| 🟠 | Amber badge = WR 45-64% |
| 🔴 | Red badge = WR <40% |

## No External Dependencies

Pure Python 3.6+. Import and use anywhere.

---

*Author: KaiOC 🌊 for Jeff Milam*
*Version: 1.2.0*
*Built: 2026-04-25*