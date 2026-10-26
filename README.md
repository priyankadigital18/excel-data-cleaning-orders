# excel-data-cleaning-orders

## Objective
Clean a messy dataset of 1,070 online store orders so it is ready for analysis.

## Dataset
Synthetic practice dataset (generated for learning, not real customer data).
Rows before: 1,070 | Rows after: 1,000 | Columns: 10

## Tools & Functions
Excel: Remove Duplicates, TRIM, CLEAN, SUBSTITUTE, PROPER, Text to Columns,
Find & Replace, DATEVALUE, VALUE, Data Validation

## Issues Found and Fixed
| Issue | Column | Rows affected | Fix |

| Exact + near duplicates | All | 70 | Remove Duplicates (after trimming names) |
| Extra spaces, line breaks, hidden spaces | Customer Name | 422 / 32 / 16 | TRIM, CLEAN, SUBSTITUTE |
| Inconsistent capitalisation | Customer Name | 112 | PROPER |
| Mixed phone formats | Phone | 729 | Removed symbols, kept last 10 digits |
| Blanks and placeholders (N/A, -, null) | Several | see log | Labelled or left empty, with reasons |
| Dates and amounts stored as text | Order Date, Amount | 1,070 / 1,037 | Converted to proper date and number types |
| Inconsistent labels | Category, Payment, City | see log | Find & Replace |

## Before vs After
<img width="1272" height="422" alt="raw" src="https://github.com/user-attachments/assets/f7161187-46ee-4e90-900f-b18133befd26" />

<img width="1270" height="476" alt="clean" src="https://github.com/user-attachments/assets/9d83c096-44c7-4e0f-9319-c96c8993142f" />


## Key Decisions
- Merged "Bombay" into "Mumbai".
- Did not invent missing Amount values; left them empty.
- Replaced line breaks with spaces before using CLEAN, so names did not join together.

## What I Learned
The order of cleaning steps matters. 
Trimming names before removing duplicates uncovered 20 extra duplicate rows that I would have missed. I also learned that TRIM and CLEAN don’t catch everything (line breaks and non-breaking spaces need SUBSTITUTE), and to document every decision, like leaving missing amounts blank instead of guessing.

