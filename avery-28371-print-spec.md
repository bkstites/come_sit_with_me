# Avery 28371 Business Card Print Spec

## Product Overview
- **Product Name:** Avery Premium Business Cards  
- **Product Number:** 28371  
- **Sheet Size:** 8.5" × 11" (US Letter)  
- **Card Size:** 2" × 3.5" (Standard Business Card)  
- **Cards Per Sheet:** 10 (2 columns × 5 rows)  
- **Paper Weight:** 80 lb / 216 gsm  
- **Finish:** Matte White, Uncoated  
- **Printer Type:** Inkjet  

## Layout Dimensions

```
┌─────────────────────────────────────────────────────┐  ← 8.5" wide
│               0.5"  top margin                      │
│  ┌─────────────────────┬─────────────────────┐      │
│  │                     │                     │  ↕ 2"│  0.75"
│  │      Card 1         │      Card 2         │      │  side
│  │   3.5" × 2"         │   3.5" × 2"         │      │  margin
│  ├─────────────────────┼─────────────────────┤      │
│  │      Card 3         │      Card 4         │  ↕ 2"│
│  ├─────────────────────┼─────────────────────┤      │
│  │      Card 5         │      Card 6         │  ↕ 2"│
│  ├─────────────────────┼─────────────────────┤      │
│  │      Card 7         │      Card 8         │  ↕ 2"│
│  ├─────────────────────┼─────────────────────┤      │
│  │      Card 9         │      Card 10        │  ↕ 2"│
│  └─────────────────────┴─────────────────────┘      │
│               0.5"  bottom margin                   │
└─────────────────────────────────────────────────────┘
         ←3.5"→               ←3.5"→
  ←0.75"→                             ←0.75"→
```

| Property             | Value                   |
|----------------------|-------------------------|
| Sheet width          | 8.5 in                  |
| Sheet height         | 11 in                   |
| Top margin           | 0.5 in                  |
| Bottom margin        | 0.5 in                  |
| Left margin          | 0.75 in                 |
| Right margin         | 0.75 in                 |
| Column width (pitch) | 3.5 in                  |
| Row height (pitch)   | 2.0 in                  |
| Columns              | 2                       |
| Rows                 | 5                       |
| Total cards          | 10                      |
| Aspect ratio         | 1.75 : 1 (3.5 ÷ 2.0)   |

## Print Sheet HTML Calibration Variables

These are defined at the top of `business-card-print-sheet.html`:

| Variable               | Default   | Purpose                                          |
|------------------------|-----------|--------------------------------------------------|
| `--template-offset-x`  | `0.75in`  | Left margin — matches Avery spec (do not change) |
| `--template-offset-y`  | `0.5in`   | Top margin — matches Avery spec (do not change)  |
| `--front-page-comp-x`  | `0in`     | Printer drift correction for front page (X axis) |
| `--front-page-comp-y`  | `0in`     | Printer drift correction for front page (Y axis) |
| `--back-page-comp-x`   | `0in`     | Duplex drift correction for back page (X axis)   |
| `--back-page-comp-y`   | `0in`     | Duplex drift correction for back page (Y axis)   |

### Calibration Procedure
1. Print at **100% / Actual Size** (no fit, no shrink-to-page).
2. Disable browser **headers and footers** in the print dialog.
3. Enable **Background graphics**.
4. Duplex: **Flip on long edge**.
5. Hold the printout behind an Avery 28371 sheet against a light source.
6. If the **front** is misaligned, adjust `--front-page-comp-x/y` in small steps (e.g. `0.01in`).
7. If the **back** does not match the front, adjust `--back-page-comp-x/y` independently.

## Features
- **Sure Feed technology** — anti-jam feed for reliable sheet handling
- **Micro-perforated edges** — smooth, clean separation after printing
- **Double-sided printable** — suitable for duplex / two-sided cards
