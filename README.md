# Excel Comparison Tool

A client-side web application that compares Modon and Sakneen Excel sheets to identify status discrepancies. Runs entirely in your browser - no server required!

## 🌐 Live Demo

[![Deploy to GitHub Pages](https://github.com/images/modules/site/buttons/deploy-to-github-pages.svg)](https://github.com/yourusername/excel-comparison-tool)

## Features

- **Client-side processing** - All processing happens in your browser
- Upload two Excel files (Modon and Sakneen)
- Compare Unit Number (Modon) with UnitID (Sakneen)
- Identify discrepancies when units have EOI data in Modon but show as "Available" in Sakneen
- Export discrepancies in CSV, Excel, and JSON formats
- Modern, responsive web interface
- No server required - works offline after first load

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

## 🚀 Deploy to GitHub Pages

1. **Fork this repository**
2. **Enable GitHub Pages**:
   - Go to your repository settings
   - Scroll to "Pages" section
   - Select "Deploy from a branch"
   - Choose "main" branch and "/ (root)" folder
   - Click "Save"
3. **Your app will be live at**: `https://yourusername.github.io/excel-comparison-tool`

## Local Usage

1. **Clone the repository**:

```bash
git clone https://github.com/yourusername/excel-comparison-tool.git
cd excel-comparison-tool
```

2. **Open `index.html` in your browser** or use a local server:

```bash
# Using Python
python -m http.server 8000

# Using Node.js
npx serve .

# Using PHP
php -S localhost:8000
```

3. **Visit**: `http://localhost:8000`

## Usage

1. Upload your Modon Excel file
2. Upload your Sakneen Excel file
3. Click "Compare Files"
4. Review the discrepancies found
5. Export discrepancies in your preferred format (CSV, Excel, JSON)

## File Structure

- `index.html` - Complete client-side application
- `README.md` - This file
- `LICENSE` - MIT License

## Technology Stack

- **HTML5** - Structure
- **CSS3** - Styling with modern features
- **JavaScript (ES6+)** - Client-side processing
- **SheetJS** - Excel file reading and writing
- **No dependencies** - Everything runs in the browser

## Browser Compatibility

- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+

## Notes

- **Privacy**: All processing happens locally in your browser - no data is sent to any server
- **Performance**: Handles large Excel files efficiently
- **Offline**: Works without internet connection after first load
- **Security**: No server-side vulnerabilities
- **Case-insensitive**: Column matching is case-insensitive
- **File formats**: Supports .xlsx and .xls formats
- **Export options**: CSV, Excel, and JSON formats available

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

This project is open source and available under the [MIT License](LICENSE).
