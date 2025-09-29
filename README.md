# BadBuddha_IBFibPro (NinjaTrader 8)
High-performance Initial Balance + Fibonacci extension mapper for intraday futures. IBFibPro draws the developing IB in real-time, projects configurable fib extensions (± levels), and flags breakouts with clean visual cues and optional alerts. Built for day-traders and prop-firm evaluations who want fast, consistent reference levels without chart clutter.

Works on NinjaTrader 8 (64-bit). No source required: import the compiled .zip add-on.

✨ Highlights

Developing IB: See the IB as it forms (no waiting for IB to finish).
Smart Fib Grid: Auto-projects user-defined fibs above/below IB range (e.g., 0.272 / 0.382 / 0.5 / 0.618 / 1.0 / 1.272 / 1.618 / 2.0).
Session-aware: Choose which session defines IB (e.g., RTH, ETH/Globex, London) and custom start/end times.
Breakout Signals: Optional arrows/labels when price crosses IB High/Low (and each fib). **Coming Soon
Clean Styling: Per-level colors, line styles, opacity, extend-right, auto-hide features.
Low Overhead: Optimized drawing + state caching; safe for multiple charts.

Pro conveniences:
Annotate IB midline / range (ticks, points, % of price)
Screenshot-ready labels (compact typography)

Licensing-ready: Compatible with NT8 Vendor Licensing (machine-bound keys).

🚀 Quick Start

Download the release
Grab the latest BadBuddha_IBFibPro_x.y.z.zip from the Releases page.

Import into NinjaTrader 8
Tools → Import → NinjaScript Add-On → select the .zip.
Restart NT8 if prompted.

Add to a chart
Right-click chart → Indicators… → BadBuddha_IBFibPro → OK.

Pick your session
Choose the session template and set IB Start / IB End.

Select fibs & styling
Edit the fib list, colors, line widths, and alert toggles.

Tip: Use minute bars (1–10m typical). Tick Replay off. “Calculate” = On Each Tick for the cleanest developing IB.
Update channel: Optional JSON manifest so NT8 can notify you of new releases.


⚙️ Parameters (most used)

IB Session Source
Use Chart Session Template (default)
Custom (manual IB Start and IB End in HH:mm)
Preset (RTH, ETH/Globex, London, NYSE, Custom)

IB Timing

IB Start Time, IB End Time
Anchor To Trading Day (resets each session)
Show Only Active Session / Show Only Today

Levels

Fib Levels (comma-separated decimals, e.g., 0.272,0.382,0.5,0.618,1,1.272,1.618,2)
Project Above/Below toggles
Extend Right, Hide Past Sessions

Visuals

IB High/Low Color, IB Fill Opacity
Midline Show/Color
Per-level color/width/style (optional auto-palette)
Label formats: Price, Pct, Ticks, Range×Fib

Signals & Alerts (**coming soon)

Alert On IB Breakout (first touch / every touch)
Alert On Fib Touch (once per level per session)
Sound, Rearm Seconds, Draw Arrows/Labels

