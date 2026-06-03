# Singlish → Sinhala Transliteration Test Suite

**Assignment 1 – Option 1 | IT3040 ITPM**

This repository contains 50 automated test cases that validate the **Chat Sinhala**
transliteration function at <https://www.pixelssuite.com/chat-translator>.  
Every test case is a scenario where the system **fails** to produce the correct Sinhala
output.  All 24 Singlish input types defined in Appendix 1 are covered (≥ 2 cases each).

---

## Prerequisites

| Requirement | Version |
|---|---|
| Python | 3.11 or 3.12 |
| pip | latest (run `pip install -U pip`) |
| Google Chrome | latest (recommended) |

---

## Installation (one-time)

```bash
# 1. Clone / extract this repository
cd D:\playwright_project          # Windows
# cd ~/playwright_project         # macOS / Linux

# 2. Install Python dependencies
pip install -U pip
pip install playwright openpyxl
playwright install
```

---

## Running the automation script (fills the Excel file)

```bash
python test_automation.py \
  --excel "test_data/Assignment 1 - Test cases.xlsx" \
  --url "https://www.pixelssuite.com/chat-translator" \
  --wait-ms 5000 \
  --type-delay-ms 80 \
  --slow-mo-ms 200 \
  --save-every 1 \
  --keep-open
```

After execution, open **`test_data/Assignment 1 - Test cases.xlsx`** to review the
auto-populated **Actual output** and **Status** columns.

---

## Running the pytest test suite

```bash
# Install pytest-playwright
pip install pytest pytest-playwright

# Run all 50 tests (headed browser)
pytest tests/test_transliteration.py -v

# Run headless
pytest tests/test_transliteration.py -v --headed=false
```

---

## Repository structure

```
playwright_project/
├── test_automation.py          # Main Playwright automation script (provided)
├── Assignment 1 - Test cases.xlsx                   # 50 pytest test cases
├── README.md                   # This file

```

---

## Test case coverage

| # | Singlish Input Type | Test IDs |
|---|---|---|
| 1 | Question forms | TC_0001, TC_0002 |
| 2 | Command forms | TC_0003, TC_0004 |
| 3 | Greetings | TC_0005, TC_0006 |
| 4 | Requests | TC_0007, TC_0008 |
| 5 | Responses | TC_0009, TC_0010 |
| 6 | Repeated Words | TC_0011, TC_0012 |
| 7 | Inputs with Punctuation Marks | TC_0013, TC_0014 |
| 8 | Romanization / Spelling Variants | TC_0015, TC_0016 |
| 9 | Isolated English Word Insertions in Singlish | TC_0017, TC_0018 |
| 10 | Multi-Word English Phrases in Singlish | TC_0019, TC_0020 |
| 11 | English Digital Terms in Singlish | TC_0021, TC_0022 |
| 12 | Platform/App Names in Singlish | TC_0023, TC_0024 |
| 13 | English Abbreviations/Acronyms in Singlish | TC_0025, TC_0026 |
| 14 | English Clipped Forms in Singlish | TC_0027, TC_0028 |
| 15 | Place Names Embedded in Singlish | TC_0029, TC_0030 |
| 16 | Person Names Embedded in Singlish | TC_0031, TC_0032 |
| 17 | Inputs with Numbers and Numeric Suffixes | TC_0033, TC_0034 |
| 18 | Inputs with Currency | TC_0035, TC_0036 |
| 19 | Inputs with Time Formats | TC_0037, TC_0038 |
| 20 | Inputs with Dates | TC_0039, TC_0040 |
| 21 | Inputs with Unit of Measurements | TC_0041, TC_0042 |
| 22 | Inputs with Slang and Casual Phrasing | TC_0043, TC_0044 |
| 23 | Online Identifiers in Singlish | TC_0045, TC_0046 |
| 24 | Inputs Containing Emojis | TC_0047, TC_0048 |
| – | Mixed / additional | TC_0049, TC_0050 |

---

## Notes

- **Scope**: Only the *Chat Sinhala* transliteration function is tested.  
  Standard Sinhala, backend APIs, and performance/security testing are out of scope.
- **Status values**: `PASS` = actual output matches expected; `FAIL` = mismatch (the expected failure);  
  `COLLECTED` = no expected output was provided.
- None of the examples from Appendix 1 or Appendix 2 of the assignment are used as test inputs.
