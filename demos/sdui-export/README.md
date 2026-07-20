# SDUI + SheetJS Export Demo

Demonstrates how to combine **Server-Driven UI (SDUI)** with **SheetJS** to export CRM data to Excel.

## How to run

Open `index.html` directly in any browser. No server required.

## What it shows

1. A simulated SDUI config (in production: `fetch('/api/sdui/config')`) defines the table structure and data as JSON
2. The client renders the table from that JSON
3. Clicking "Export to Excel" uses SheetJS `XLSX.utils.aoa_to_sheet()` to generate a `.xlsx` file
4. Clicking "Export to CSV" uses SheetJS to generate a `.csv` file

## Key insight

With SDUI, the column schema lives in **one place** (the server JSON). SheetJS reads the same schema to build the spreadsheet — no duplication between UI code and export code.

```
SDUI JSON config
    │
    ├─► Table renderer (DOM)
    └─► SheetJS exporter (.xlsx)
```

## Integration with Byblos CRM

See the SDUI spec at: https://github.com/Byblos-sicherheit/cr/tree/main/sdui
