# Resume Studio

An editable library of resumes and cover letters in a single HTML file. Organize resumes by industry and section, edit them directly on a letter-size page, and download each one as PDF, Word or HTML. No build step, no server, no account.

## What it does

- **Industries and sections.** Industries are the main categories (Real Estate, E-commerce, Telecom, General to start). Sections are the sub-categories inside each one (Analysis, Product, Delivery, Marketing, Other). Add, rename or delete both from **Edit** in the sidebar.
- **Resumes.** Use **+ Add** on any section to start a resume from your blank template, from pasted text, or as a copy of another resume.
- **Editing on the page.** Click anywhere on the sheet and type. The **Insert** bar adds a section, a sub-section (a dated entry such as a job), a bullet or a paragraph after the cursor, and **Remove block** deletes the one you are in.
- **Cover letters.** Each resume has a matching letter built from a template. Fill in Company, Hiring manager, Role title and Date once and they appear everywhere in the letter. You can keep one common letter, or give an industry its own.
- **Templates.** The blank resume and the cover letters are pages you edit like any other. Put your name, contact line, employers and education in the blank resume once, and every new resume starts from it. In letter templates, write `{company}`, `{manager}`, `{role}` and `{date}` where those should be filled in.
- **Downloads.** PDF (selectable text, not an image), Word (.docx) and a print-ready HTML page for any resume, letter or template.
- **Library file.** **Export library** writes one `.json` file with every resume, letter, template, industry and section. **Import library** reads it back, here or in a companion tool. The format is described in [docs/library-format.md](docs/library-format.md).

## Use it

1. Download `index.html` (or clone the repo) and open it in Chrome, Edge, Firefox or Safari.
2. Open **Templates → Blank resume** and replace the placeholders with your own details.
3. Add resumes to the sections you need, edit them, and download what you send.

**Saving.** Edits are kept in your browser as you work. **Save changes** also downloads an updated copy of the page with your library inside it, so the file itself carries your work. Use **Export library** for a smaller backup you can move between browsers or tools.

**Printing.** Use **Print**, or download the PDF.

### Host it on GitHub Pages

Settings → Pages → Deploy from a branch → `main` / root. The studio is then available at `https://<your-username>.github.io/<repo-name>/`. Your library still lives only in your browser and in the files you download.

## Privacy

Nothing is uploaded anywhere. The page loads two libraries from cdnjs (jsPDF for PDF export and JSZip for Word export) and fonts from Google Fonts; your resume content never leaves the browser. Keep your exported library files and saved copies of the studio out of public repositories (the `.gitignore` already excludes the default file names).

## Paste format

Pasted text is turned into structure:

| You paste | It becomes |
| --- | --- |
| The first line | Your name |
| A line with `@`, `|` or a phone number right after it | The contact line |
| A short line in CAPITALS, or ending in `:` | A section heading |
| A line starting with `•`, `-` or `*` | A bullet |
| A line ending in a date range, such as `Senior Analyst | Acme, Boston | Jan 2020 – Present` | A dated entry with the title in bold |

## Contributing

Issues and pull requests are welcome. The whole app is `index.html`: styles in `#app-style`, logic in `#app-script`, and the starting library in `#resume-state`. Keep it dependency-free beyond the two CDN libraries.

## License

[MIT](LICENSE)
