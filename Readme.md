# Markdown to Google Docs Converter

A Python script that converts markdown meeting notes into a formatted Google Doc, running directly in Google Colab.

## Description

This tool automatically parses markdown content and creates a Google Doc with proper formatting including:
- Hierarchical heading styles (H1, H2, H3)
- Checkboxes for action items
- Styled mentions (@name) with bold and color formatting
- Special formatting for footer information

## Setup Instructions

### Prerequisites
- Google account
- Access to Google Colab

### Required Dependencies

The script automatically installs the following packages:
```
google-api-python-client
```

## How to Run in Colab

### Option 1: Direct Upload

1. **Open Google Colab**: Go to [https://colab.research.google.com](https://colab.research.google.com)

2. **Upload the Notebook**:
   - Click "File" → "Upload notebook"
   - Select the `markdown_to_gdocs.ipynb` file

3. **Run the Script**:
   - Click "Runtime" → "Run all" (or press `Ctrl+F9`)
   - When prompted, click the authentication link and authorize access
   - The script will create a new Google Doc and provide the link

### Option 2: From GitHub

1. **Open Google Colab**: Go to [https://colab.research.google.com](https://colab.research.google.com)

2. **Load from GitHub**:
   - Click "File" → "Open notebook"
   - Select "GitHub" tab
   - Paste the repository URL
   - Select the notebook file

3. **Run as described in Option 1, step 3**

## Usage

### Using the Provided Content

The script comes with pre-loaded meeting notes. Simply run the notebook and it will:
1. Authenticate with your Google account
2. Create a new Google Doc
3. Format and populate it with the meeting notes
4. Provide a direct link to view the document

### Using Custom Content

To convert your own markdown content:

1. Replace the `MARKDOWN_CONTENT` variable with your markdown text:
```python
MARKDOWN_CONTENT = """# Your Title Here

## Your Section

- Your bullet points
"""
```

2. Update the document title in the main execution:
```python
doc_id = create_google_doc('Your Document Title', MARKDOWN_CONTENT)
```

3. Run the notebook

## Output

The script creates a Google Doc with:

- **Heading 1**: Main title (e.g., "Product Team Sync - May 15, 2023")
- **Heading 2**: Section headers (e.g., "Attendees", "Agenda")
- **Heading 3**: Sub-section headers (e.g., "1. Sprint Review")
- **Bullet Points**: Indented lists
- **Action Items**: Checkboxes with bold, blue-colored mentions
- **Footer**: Italic, gray-colored metadata

## Code Structure

- **`create_google_doc()`**: Main function that creates the document and applies formatting
- **`parse_markdown()`**: Parses markdown and generates Google Docs API requests
- **Error handling**: Try-catch blocks for API errors
- **Clear documentation**: Comments explaining each section

## Troubleshooting

### Authentication Issues
- Make sure you're logged into your Google account in Colab
- Try clicking the authentication link again
- Clear browser cookies and retry

### API Errors
- Ensure the Google Docs API is enabled (usually automatic in Colab)
- Check your internet connection
- Verify you have permission to create documents in your Google Drive

### Formatting Issues
- Ensure markdown syntax is correct
- Check indentation uses spaces (not tabs)
- Verify checkbox format is exactly `- [ ]` with spaces

## Example Output

The script converts this markdown:
```markdown
## Action Items

- [ ] @sarah: Finalize Q3 roadmap by Friday
```

Into a formatted Google Doc with:
- "Action Items" as Heading 2
- A checkbox (☐)
- **@sarah** in bold blue text
- Followed by the task description

## License

MIT License - Feel free to use and modify for your needs.

## Contributing

Contributions, issues, and feature requests are welcome!

## Author

Rangasai Kumbhashi Raghavendra.