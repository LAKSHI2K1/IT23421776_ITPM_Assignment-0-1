# Test Automation for Singlish to Sinhala Translator

This project automates testing of the Singlish to Sinhala translation web application using Playwright and Python.

## Prerequisites

- **Python 3.11/3.12** (or later)
- **Google Chrome** or **Chromium** (Playwright can install it)
- **Excel file** with test cases (e.g., `IT23421776_ITPM_Assignment 01.xlsx`)

## Installation

1. **Install Python dependencies:**
   ```bash
   py -m pip install -U pip
   py -m pip install playwright openpyxl
   ```

2. **Install Playwright browsers:**
   ```bash
   py -m playwright install
   ```

## Project Structure

- `test_automation.py` - Main test automation script
- `IT23421776_ITPM_Assignment 01.xlsx` - Test cases Excel file
- `Assignment 1 - Test cases.xlsx` - Additional test cases

## Running Tests

### Basic Command
```bash
py test_automation.py --excel "IT23421776_ITPM_Assignment 01.xlsx" --url "https://www.pixelssuite.com/chat-translator"
```

### Full Command with Options
```bash
py test_automation.py --excel "IT23421776_ITPM_Assignment 01.xlsx" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 5000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1 --headless
```

### Command Options
- `--excel`: Path to Excel test case file
- `--url`: Web app URL (default: chat-translator)
- `--wait-ms`: Wait time after input (default: 5000ms)
- `--type-delay-ms`: Delay between typing characters (default: 30ms)
- `--slow-mo-ms`: Slow down browser actions (default: 0)
- `--save-every`: Save Excel after N tests (default: 0)
- `--headless`: Run browser in background (remove to see UI)
- `--keep-open`: Keep browser open after tests

### Viewing Tests in Browser
To see the tests running in Chromium:
```bash
py test_automation.py --excel "IT23421776_ITPM_Assignment 01.xlsx" --url "https://www.pixelssuite.com/chat-translator" --slow-mo-ms 1000 --keep-open
```

## Test Results

- Results are automatically saved to the Excel file
- Check `Actual output` and `Status` columns
- PASS = Test passed, FAIL = Test failed

## Troubleshooting

### Excel File Locked
- **Error**: Permission denied when saving
- **Solution**: Close Excel before running tests

### Browser Closes Unexpectedly
- The web app may close pages after interaction
- Use `--keep-open` to keep browser open for inspection

### npm Errors
- This is a Python project, not Node.js
- Use `py` commands instead of `npm` or `npx`

## Test Case Format

Excel file should have columns:
- `TC ID`: Test case identifier
- `Input`: Singlish text to translate
- `Expected output`: Expected Sinhala translation
- `Actual output`: Will be filled by script
- `Status`: PASS/FAIL (filled by script)

## Support

For issues with the test automation script, check the Python console output for error messages.
