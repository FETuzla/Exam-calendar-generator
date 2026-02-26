# 📆 Exam Calendar Generator

A student-led tool that extracts exam schedules published by the college and lets students generate a personalized `.ics` calendar file with just the subjects they care about.

🔗 **Live at:** [fetuzla.github.io/Exam-calendar-generator](https://fetuzla.github.io/Exam-calendar-generator/)

## Overview

The college publishes exam schedules as PDF files. This tool extracts that data using `pdftotext`, parses it into structured JSON with `parser.js`, and serves it through a simple form interface where students can select their subjects and instantly download an `.ics` file ready to import into any calendar app.

## Features

- **PDF Data Extraction** — Uses `pdftotext` to extract raw text from the college's official exam schedule PDF.
- **Automatic Parsing** — `parser.js` processes the extracted text into clean, structured JSON.
- **Subject Picker** — A simple form lets students select only the subjects relevant to them.
- **`.ics` Export** — Generates a calendar file with all selected exam dates, importable into Google Calendar, Apple Calendar, Outlook, and more.
- **No login required** — Runs entirely in the browser, no account needed.

## How It Works

1. The college publishes an exam schedule PDF.
2. `pdftotext` extracts the raw text from the PDF.
3. `parser.js` parses that text and saves the structured data to `data/ispiti.json`.
4. Students open the app, select their subjects from the form.
5. Click generate thats downloads your `.ics` file and import it into your calendar app.

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (for running the parser)
- `pdftotext` [Linux man page](https://linux.die.net/man/1/pdftotext)
- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) VS Code extension (for local development)

### Updating the Exam Data

When the college publishes a new exam schedule PDF:

```bash
# 1. Extract text from the PDF
pdftotext assets/docs/ispiti.pdf assets/docs/ispiti.txt

# 2. Parse the extracted text into JSON
node js/parser.js
```

This updates `data/ispiti.json` with the latest exam data.

### Running Locally

Open the project in VS Code and click **Go Live** in the bottom status bar to launch with Live Server.  
Then open your browser and go to `http://localhost:5500`.

## Project Structure

```
├── assets/
│   ├── docs/               # Source PDF and extracted text
│   └── images/
├── css/
│   └── style.css
├── data/
│   └── ispiti.json         # Parsed exam schedule data
├── js/
│   ├── icsGenerator.js     # Generates .ics calendar file
│   ├── index.js            # UI logic and form handling
│   └── parser.js           # Parses extracted PDF text into JSON
├── index.html
└── package.json
```

## Contributing

This project is built by students, for students. Contributions are welcome!

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

## License

This project is open-source.

---
