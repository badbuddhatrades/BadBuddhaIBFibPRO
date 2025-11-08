# BadBuddha IB Fib Extensions PRO

<div align="center">

![Version](https://img.shields.io/badge/version-v2.0.1.0-blue)
![Platform](https://img.shields.io/badge/platform-NinjaTrader%208-green)
![License](https://img.shields.io/badge/license-NinjaTrader%20Vendor-orange)
![Release](https://img.shields.io/badge/release-October%202025-lightgrey)

**Professional-grade Initial Balance indicator with customizable Fibonacci extensions and multi-session support**

[Features](#-key-features) • [Installation](#-installation) • [Configuration](#-configuration-guide) • [Use Cases](#-use-cases) • [Support](#-support--updates)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [PRO vs Lite Comparison](#-pro-vs-lite-comparison)
- [Screenshots](#-screenshots)
- [Installation](#-installation)
- [Configuration Guide](#-configuration-guide)
  - [Initial Balance Block Settings](#initial-balance-block-settings)
  - [Display / Style Settings](#display--style-settings)
  - [Fibonacci Settings](#fibonacci-settings)
- [How It Works](#-how-it-works)
- [Technical Architecture](#-technical-architecture)
- [Use Cases](#-use-cases)
- [Troubleshooting](#-troubleshooting)
- [Advanced Tips](#-advanced-tips)
- [Support & Updates](#-support--updates)

---

## 🎯 Overview

**BadBuddhaIBFibPRO** is a professional-grade NinjaTrader 8 indicator that plots Initial Balance (IB) ranges with fully customizable Fibonacci extension levels. Unlike the Lite version, PRO supports up to **four independent IB blocks per day**, making it ideal for tracking multiple trading sessions (pre-market, regular hours, after-hours, overnight) with complete flexibility.

### Version Information

| Info | Details |
|------|---------|
| **Version** | v2.0.1.0 |
| **Release Date** | October 20, 2025 |
| **Edition** | PRO (Unlocked) |
| **Author** | BadBuddha Customs LLC |
| **License** | NinjaTrader Vendor License |

---

## ✨ Key Features

### 1. **Multiple IB Blocks (Up to 4 per Day)**

Track up to four different Initial Balance periods simultaneously:

- **Block 1** (default: 09:30, 60 min) - Regular market open
- **Block 2** (default: 13:00, 60 min) - Lunch session / PM session
- **Block 3** (default: 20:00, 60 min) - Overnight session
- **Block 4** (default: 23:00, 60 min) - Asian session

Each block is independently configurable with its own:
- ✅ Start time (fixed HH:mm or offset from session open)
- ✅ IB duration (1-360 minutes)
- ✅ Calendar day vs session anchoring
- ✅ Line extension behavior

### 2. **Fully Customizable Fibonacci Levels**

Define any Fibonacci extension levels via CSV format:

```csv
Default: 0.25, 0.5, 1.0, 1.618, 2.0, 3.0
Traditional Fib: 0.382, 0.5, 0.618, 1.0, 1.618, 2.618
Extended: 0.25, 0.5, 0.75, 1.0, 1.25, 1.5, 2.0, 2.5, 3.0
```

- ✅ Add/remove levels freely
- ✅ Levels project both **up** from IB High and **down** from IB Low
- ✅ Automatically sorted and de-duplicated

### 3. **Advanced Stroke Styling (EMA-Style Editors)**

Professional line styling with NinjaTrader's native Stroke editors:

| Stroke Type | Default Style | Purpose |
|-------------|---------------|---------|
| **IB Stroke** | Solid, 2pt | Main IB High/Low lines |
| **Midline Stroke** | Dashed, 1pt | 50% midline |
| **Extension Up Stroke** | Solid, 2pt | Upward Fib levels |
| **Extension Down Stroke** | Solid, 2pt | Downward Fib levels |

Each stroke includes:
- 🎨 Brush color with full gradient support
- ⚡ Dash style (Solid, Dash, Dot, DashDot, etc.)
- 📏 Line width (float precision)

### 4. **Live Drawing During IB Period**

- ✅ **Enabled by default** - Watch IB range form in real-time
- ✅ Updates dynamically as new highs/lows form during the IB window
- ❌ Lite version: Static (only draws after IB completes)

### 5. **Customizable Labels & Fonts**

- 🔤 **Font Family**: Choose any installed font (default: Arial)
- 📐 **Font Size**: 8-32pt range (default: 12pt)
- 🎨 **Label Brush**: Separate color control for all text labels
- 🔘 **Toggle Labels**: Show/hide all labels with one switch

**Label formats:**
```
IB High / IB Low      - Main IB boundaries
IB 50%                - Midline
IB + 0.5R, IB + 1R    - Upward extensions (R = IB Range)
IB - 0.5R, IB - 1R    - Downward extensions
```

### 6. **Flexible Session Anchoring**

Per-block control over session logic:

| Mode | Description | Best For |
|------|-------------|----------|
| **Calendar Day** | IB resets at midnight (00:00) | 24-hour markets (Forex, Crypto) |
| **Session Anchoring** | IB resets at trading session open | Futures, Equities |

### 7. **Rectangle Fill with Opacity Control**

- 🖼️ **Rectangle Fill Brush**: Customizable solid or gradient fill
- 🔆 **Opacity**: 0-100% control (default: 20%)
- 👁️ Visual IB range highlighting for quick recognition

### 8. **Debug Mode (Developer Feature)**

Compile-time debug switches for troubleshooting:

```csharp
#define BB_DEBUG      // General debug logging to Output window
#define BB_DEBUG_UI   // Expose debug settings in property grid
```

Logs session calculations, IB range updates, and update checker events.

### 9. **Automatic Update Checker**

Built-in GitHub-based update notification:

- 📅 Checks for updates every **1 day** (configurable)
- 🔗 Fetches from GitHub: `badbuddhatrades/BadBuddhaIBFibPRO`
- 📊 Displays:
  - Version comparison (current vs latest)
  - Release date, file size, minimum NT build
  - Breaking changes warning
  - Detailed changelog
- 🪟 Custom WPF dialog with "Open Download" button
- ⚙️ Can be disabled in settings

---

## 📊 PRO vs Lite Comparison

| Feature | Lite (Free) | PRO (Paid) |
|---------|-------------|------------|
| **IB Blocks per Day** | 1 | ✅ Up to 4 |
| **Fibonacci Levels** | Fixed (0.5, 1.0, 1.618) | ✅ Fully customizable CSV |
| **Live Drawing** | ❌ No | ✅ Yes |
| **Font Customization** | Fixed (Arial, 12pt) | ✅ Any font, 8-32pt |
| **Line Styling** | Simple color pickers | ✅ Advanced Stroke editors (dash styles, gradients) |
| **Per-Block Settings** | N/A | ✅ Each block independently configured |
| **Debug Mode** | ❌ No | ✅ Yes (compile-time) |
| **Rectangle Fill** | Basic | ✅ Advanced with opacity control |
| **Session Anchoring** | Calendar only | ✅ Calendar or Session-based |
| **License** | Free | NinjaTrader Vendor License |
| **Update Frequency** | 7 days | 1 day |
| **Priority Support** | ❌ No | ✅ Yes |

---

## 📸 Screenshots

### Prerequisites

- ✅ NinjaTrader 8 (version 8.0.0.0 or higher)
- ✅ Windows 10 or higher

### Installation Steps

1. **Purchase License**

   Purchase from [BadBuddha Customs](https://badbuddhacustoms.com)
   - Vendor: BadBuddha Customs LLC

2. **Download the Indicator**

   Download `BadBuddhaIBFibPRO.zip` from: www.badbuddhacustoms.com store

3. **Import to NinjaTrader**

   ```
   1. Open NinjaTrader 8 Control Center
   2. Click Tools > Import > NinjaScript Add-On
   3. Browse to BadBuddhaIBFibPRO.zip
   4. Click Import
   5. Wait for "Import successful" message
   ```

. **Add to Chart**

   ```
   1. Right-click any chart
   2. Select Indicators
   3. Find "BadBuddhaIBFibPRO" in the list
   4. Click Add
   5. Configure settings (see Configuration Guide below)
   ```

### First-Time Setup Recommendations

✅ **Step 1**: Enable Block 1 with default settings (09:30, 60 min)
✅ **Step 2**: Disable Blocks 2-4 initially
✅ **Step 3**: Set Fibonacci Levels to your preference (default is good starting point)
✅ **Step 4**: Adjust Stroke Colors to match your chart theme
✅ **Step 5**: Toggle "Draw Live During IB" based on preference (enabled = more visual feedback)

---

## ⚙️ Configuration Guide

### Initial Balance Block Settings

Each block (1-4) has identical configuration options:

#### **05. IB Block 1** (Example - applies to all 4 blocks)

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| **Enabled** | bool | true | Toggle this block on/off |
| **Use Fixed Start (HH:mm)** | bool | true | `true` = Use specific clock time (e.g., 09:30)<br>`false` = Use offset from session open |
| **Fixed Start (HH:mm)** | string | "09:30" | Clock time in 24-hour format (e.g., `09:30`, `13:00`, `20:00`) |
| **Offset From Session Open (min)** | int | 0 | Minutes after session open (if not using fixed start) |
| **IB Length (minutes)** | int | 60 | Duration of IB period (1-360 minutes) |
| **Anchor To Calendar Day** | bool | false | `true` = Reset at midnight (calendar day)<br>`false` = Reset at trading session boundaries |
| **Extend To Session End** | bool | true | `true` = Lines extend to session close<br>`false` = Lines extend to current bar only |

#### Example: Multi-Session Setup

```ini
Block 1: 09:30, 60 min  → Regular Market Open (NYSE)
Block 2: 13:00, 30 min  → Lunch Session
Block 3: 20:00, 60 min  → Overnight Session
Block 4: 23:00, 60 min  → Asian Session
```

### Display / Style Settings

#### **03. Display / Style**

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| **Show IB Rectangle** | bool | true | Toggle shaded IB range box |
| **Show Midline (50%)** | bool | true | Toggle 50% midline |
| **Show Labels** | bool | true | Toggle all text labels |
| **IB Stroke** | Stroke | Solid, 2pt | Main IB High/Low line style |
| **Midline Stroke** | Stroke | Dashed, 1pt | 50% midline style |
| **Ext Up Stroke** | Stroke | Solid, 2pt | Upward Fibonacci extension style |
| **Ext Down Stroke** | Stroke | Solid, 2pt | Downward Fibonacci extension style |
| **Rectangle Fill Brush** | Brush | Semi-transparent | IB box fill color |
| **Rectangle Fill Opacity %** | int | 20 | 0-100% transparency |
| **Label Brush** | Brush | Chart default | Color for all text labels |
| **Label Font** | string | "Arial" | Font family name (e.g., "Consolas", "Segoe UI") |
| **Label Font Size** | int | 12 | 8-32pt range |
| **Draw Live During IB** | bool | true | Update drawing in real-time during IB period |

### Fibonacci Settings

#### **04. Fibonacci**

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| **Levels CSV (≥ 0)** | string | "0.25,0.5,1.0,1.618,2.0,3.0" | Comma-separated list of extension levels |

**Example Fibonacci Configurations:**

```csv
Default:       0.25, 0.5, 1.0, 1.618, 2.0, 3.0
Traditional:   0.382, 0.5, 0.618, 1.0, 1.618, 2.618
Extended:      0.25, 0.5, 0.75, 1.0, 1.25, 1.5, 2.0, 2.5, 3.0
Conservative:  0.5, 1.0, 1.618
```

---
## 💡 Use Cases

### 1. **Multi-Session Day Trading**

Track IB for different market sessions:

```
Pre-market     (04:00-09:30)  → Block 1
Regular hours  (09:30-16:00)  → Block 2
After-hours    (16:00-20:00)  → Block 3
```

### 2. **24-Hour Markets (Forex/Crypto)**

Define custom IB periods for global sessions:

```
London Open    08:00, 60 min  → Block 1
New York Open  13:00, 60 min  → Block 2
Tokyo Open     00:00, 60 min  → Block 3
```

### 3. **Institutional Trading Zones**

Use multiple Fib levels as profit targets:

| Level | Type | Purpose |
|-------|------|---------|
| 0.5R, 1.0R | Conservative | Initial targets |
| 1.618R, 2.0R | Extended | Swing targets |
| 3.0R | Maximum | Liquidity sweep zones |

### 4. **ICT/SMC Methodology**

Classic Initial Balance concepts:

- 📍 **IB High/Low** = Key liquidity levels
- 📊 **Extensions** = Fair value gaps, premium/discount zones
- ⚖️ **Midline (50%)** = Equilibrium

---

## 🔧 Troubleshooting

### Issue: Lines Not Appearing

**Check:**
- ✅ Block is enabled in settings (Block X_Enabled = true)
- ✅ Current time is after IB period (range must lock first)
- ✅ Stroke colors are not transparent
- ✅ Bars are loaded back far enough to cover IB start time

**Solution:**
```
1. Right-click chart > Reload NinjaScript
2. Verify settings under Indicators > BadBuddhaIBFibPRO > Properties
3. Check NinjaTrader Output window for errors (F5)
```

### Issue: Wrong IB Times

**Check:**
- ⚙️ **Calendar Day vs Session**: Toggle `Anchor To Calendar Day` setting
- ⏰ **Fixed Start Not Working**: Verify `Use Fixed Start` is true and time format is `HH:mm`
- ⏱️ **Offset Wrong**: Check `Offset From Session Open` value

**Solution:**
```
Calendar Day Mode:   IB resets at 00:00 (midnight)
Session Mode:        IB resets at session open (e.g., ES 18:00)
```

## 🎓 Advanced Tips

### Optimal Fibonacci Levels by Market

| Market | Recommended Levels | Reasoning |
|--------|-------------------|-----------|
| **ES (Equity Futures)** | `0.5, 1.0, 1.618, 2.0` | Volatility-based, strong reactions at whole numbers |
| **NQ (Tech Futures)** | `0.25, 0.5, 1.0, 1.618, 2.618` | Extended ranges due to higher volatility |
| **Forex (EUR/USD)** | `0.382, 0.5, 0.618, 1.0, 1.618` | Traditional Fibonacci ratios work well |
| **Crypto (BTC)** | `0.5, 1.0, 2.0, 3.0` | High volatility requires simplified levels |
| **Oil (CL)** | `0.5, 1.0, 1.5, 2.0` | Regular intervals for commodity trading |

---

## 📞 Support & Updates

### Official Channels

- 🌐 **Website**: [https://badbuddhacustoms.com](https://badbuddhacustoms.com)
- 💬 **Support**: support@badbuddhacustoms.com
- 📖 **Documentation**: [GitHub Repository](https://github.com/badbuddhatrades/BadBuddhaIBFibPRO)
- 🐛 **Bug Reports**: Submit via GitHub Issues

### Update Information

- 🔄 **Automatic Checks**: Every 1 day (configurable)
- 📦 **Current Version**: v2.0.1.0
- 📅 **Last Updated**: October 20, 2025
- 🔗 **Manifest URL**: `https://raw.githubusercontent.com/badbuddhatrades/BadBuddhaIBFibPRO/refs/heads/main/ibfib_pro_version.json`

### Recent Changelog

```
v2.0.1.0 (October 20, 2025)
  ✅ Update to user-based licensing system

v2.0.0.0 (September 28, 2025)
  ✅ Smoothed IB lock timing around session boundaries
  ✅ Added update popup with NTWindow
  ✅ Added four IB block calculation modes
  ✅ Added user control for line and color options
```
---

## 📝 Summary

**BadBuddhaIBFibPRO** is the complete Initial Balance solution for professional traders who need:

- ✅ **Multi-session IB tracking** (up to 4 blocks per day)
- ✅ **Unlimited custom Fibonacci levels** via CSV configuration
- ✅ **Real-time live drawing** during IB formation
- ✅ **Professional styling** (dash patterns, gradients, custom fonts)
- ✅ **Flexible session anchoring** (calendar day or trading session)
- ✅ **Debug logging** for troubleshooting
- ✅ **Automatic update notifications**
- ✅ **NinjaTrader Vendor License** with priority support

Perfect for:
- 📈 Day traders monitoring multiple sessions
- 🌍 Forex/Crypto traders (24-hour markets)
- 🤖 Algorithmic systems requiring IB-based logic
- 📊 ICT/SMC methodology practitioners
- 💼 Professional traders needing institutional-grade tools

---

<div align="center">

### 🚀 Upgrade from Lite?

**Gain complete control over your IB analysis with unlimited customization and multi-session support.**

[Purchase PRO](https://badbuddhacustoms.com)

---

**Made with ❤️ by BadBuddha Customs LLC** | *Empowering NinjaTrader 8 Traders Since 2024*

Copyright © 2025 BadBuddha Customs LLC | Licensed under NinjaTrader Vendor License

</div>
