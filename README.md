# Excel Comparison Tool

A web application that compares Modon and Sakneen Excel sheets to identify status discrepancies.

## Features

- Upload two Excel files (Modon and Sakneen)
- Compare Unit Number (Modon) with UnitID (Sakneen)
- Identify discrepancies when units have EOI data in Modon but show as "Available" in Sakneen
- Download highlighted Sakneen file with discrepancies marked in yellow
- Modern, responsive web interface

## How it works

1. **Modon Sheet**: Headers start at row 3

   - Uses "Unit Number" column for comparison
   - Uses "EOI" column to determine if unit is available (any data = not available)

2. **Sakneen Sheet**: Headers start at row 1

   - Uses "UnitID" column for comparison
   - Uses "Status" column to check availability

3. **Comparison Logic**:
   - Match units by Unit Number (Modon) = UnitID (Sakneen)
   - If Modon has EOI data (unit not available) but Sakneen shows "Available", highlight the discrepancy

## Installation

1. Install Python dependencies:

```bash
pip install -r requirements.txt
```

2. Run the application:

```bash
python app.py
```

3. Open your browser and go to: `http://localhost:5002`

## Usage

1. Upload your Modon Excel file
2. Upload your Sakneen Excel file
3. Click "Compare Files"
4. Review the discrepancies found
5. Download the highlighted Sakneen file

## File Structure

- `app.py` - Main Flask application
- `templates/index.html` - Web interface
- `requirements.txt` - Python dependencies
- `uploads/` - Temporary file storage (created automatically)

## Requirements

- Python 3.7+
- Flask
- pandas
- openpyxl
- Werkzeug

## Notes

- The application handles case-insensitive column matching
- Files are automatically cleaned up after processing
- Maximum file size: 16MB
- Supports .xlsx and .xls formats
