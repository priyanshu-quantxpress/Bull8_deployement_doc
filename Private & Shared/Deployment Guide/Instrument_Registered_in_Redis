# Instrument Registered in Redis

## 1. Overview

This module is responsible for:

- Parsing raw instrument files received from NSE & BSE
- Normalizing and combining them into a single `instruments.csv`
- Enriching instruments with derived fields (Instrument IDs, Index instruments, ELM%)
- Storing the final instruments data into **Redis** under a single key

It is designed to be run as a **CLI application** and can be safely re-run multiple times per day.

# InstrumentsRegisterInRedis — Folder Structure

`InstrumentsRegisterInRedis/
│
├── application.py                # Main CLI entry point
├── instrument_parser.py          # Core parsing & CSV generation logic
├── auto_run.bat                  # Windows helper script
├── ael_elm_updater.py            # Updates ELM% from AEL
├── common.py                     # Enums & shared constants
├── utils.py                      # Utility helpers (token generation, etc.)
│
├── config/
│   └── column_info.py            # Column definitions & rename mappings
│
├── parsers/                      # Exchange-specific parsers
│   ├── bse_parser.py
│   ├── bsecm_parser.py
│   ├── bsefo_parser.py
│   ├── nse_parser.py
│   ├── nsecm_parser.py
│   ├── nsefo_parser.py
│   └── indexes_parser.py
│
├── InstrumentFiles/              # Raw input files (exchange-provided)
│   ├── contract
│   ├── contract_1706
│   ├── contract_11082025
│   ├── EQD.csv
│   ├── indexes
│   ├── SCRIP
│   ├── security
│   ├── security_1706
│   └── security_11082025
│
├── Instruments/                  # Generated output
│   └── instruments.csv
│
├── __pycache__/
└── .gitignore`

## File Descriptions

### Root Files

| File | Description |
| --- | --- |
| `application.py` | Main CLI entry point |
| `instrument_parser.py` | Core parsing & CSV generation logic |
| `auto_run.bat` | Windows helper script |
| `ael_elm_updater.py` | Updates ELM% from AEL |
| `common.py` | Enums & shared constants |
| `utils.py` | Utility helpers (token generation, etc.) |

### Directories

| Directory | Description |
| --- | --- |
| `config/` | Column definitions & rename mappings |
| `parsers/` | Exchange-specific parser modules |
| `InstrumentFiles/` | Raw input files provided by exchanges |
| `Instruments/` | Generated output (e.g., `instruments.csv`) |

### Parsers

| File | Exchange |
| --- | --- |
| `bse_parser.py` | BSE |
| `bsecm_parser.py` | BSE Capital Market |
| `bsefo_parser.py` | BSE Futures & Options |
| `nse_parser.py` | NSE |
| `nsecm_parser.py` | NSE Capital Market |
| `nsefo_parser.py` | NSE Futures & Options |
| `indexes_parser.py` | Indexes |

[Setting Up Steps ](Instrument%20Registered%20in%20Redis/Setting%20Up%20Steps%2030a2dc291ad68008ac19f656a4b4de97.md)
