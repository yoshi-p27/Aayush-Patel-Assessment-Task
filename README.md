# Aayush-Patel-Assessment-Task
# Markdown to Google Docs Converter

A Python script that converts markdown meeting notes into a well-formatted Google Document with proper styling, bullet points, checkboxes, and mention formatting.

## Features

- ✅ **Heading Hierarchy**: Converts markdown headers (H1, H2, H3) to Google Docs heading styles
- ✅ **Nested Bullets**: Maintains proper indentation for nested bullet points
- ✅ **Checkboxes**: Converts `- [ ]` markdown checkboxes into actual Google Docs checkboxes
- ✅ **@Mention Styling**: Highlights user mentions (@name) with bold blue formatting
- ✅ **Footer Formatting**: Applies distinct italic styling to footer information
- ✅ **Error Handling**: Comprehensive error handling throughout the conversion process

## Prerequisites

- Google Account
- Google Colab environment
- Internet connection

## Dependencies

The script uses the following Python libraries (pre-installed in Colab):

```python
google.colab - For authentication
google-api-python-client - For Google Docs API
```

No additional installation required in Google Colab!

## Setup Instructions

### Option 1: Run in Google Colab (Recommended)

1. **Open Google Colab**: Go to [colab.research.google.com](https://colab.research.google.com)

2. **Create a new notebook** or upload the provided `.ipynb` file

3. **Copy the script** from `markdown_to_gdocs.py` into a code cell

4. **Run the cell**: Click the play button or press `Shift + Enter`

5. **Authenticate**: When prompted:
   - Click the authentication link
   - Select your Google account
   - Grant permissions to access Google Docs
   - Copy the authorization code back to Colab

6. **View your document**: The script will output a link to your newly created Google Doc

### Option 2: Using the Repository

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/markdown-to-gdocs.git
   cd markdown-to-gdocs
   ```

2. **Open in Google Colab**:
   - Go to [colab.research.google.com](https://colab.research.google.com)
   - File → Upload notebook
   - Select `markdown_to_gdocs.ipynb`

3. **Run all cells**

## How to Run

### Quick Start

In Google Colab, simply run:

```python
from markdown_to_gdocs import main
doc_id = main()
```

### Custom Usage

You can also use your own markdown content:

```python
from markdown_to_gdocs import MarkdownToGoogleDocs

# Your custom markdown
custom_markdown = """
# My Meeting Notes
## Attendees
- John Doe
- Jane Smith
"""

# Convert
converter = MarkdownToGoogleDocs()
doc_id = converter.convert(custom_markdown)
```

## File Structure

```
markdown-to-gdocs/
├── README.md                      # This file
├── markdown_to_gdocs.py          # Main Python script
├── markdown_to_gdocs.ipynb       # Colab notebook
└── requirements.txt              # Dependencies (for reference)
```

## Formatting Details

### Heading Styles
- `# Title` → **Heading 1** (Main title)
- `## Section` → **Heading 2** (Section headers)
- `### Subsection` → **Heading 3** (Sub-section headers)

### Bullet Points
- Regular bullets: `* item` or `- item`
- Nested bullets: Indentation preserved (2 spaces = 1 level)

### Action Items
- `- [ ] Task` → Checkbox (unchecked)
- `@username` → Bold blue text

### Footer
- Text after `---` → Italic, smaller font, gray color

## Troubleshooting

### Authentication Issues
- **Problem**: "Authentication failed"
- **Solution**: Clear browser cache and re-authenticate. Make sure you're using a Google account.

### Permission Errors
- **Problem**: "Insufficient permissions"
- **Solution**: Make sure to grant all requested permissions during authentication.

### API Errors
- **Problem**: "Failed to create document"
- **Solution**: Check your internet connection and verify Google Docs API is accessible.

## Example Output

The script converts markdown like this:

```markdown
# Product Team Sync
## Attendees
- Sarah Chen
## Action Items
- [ ] @sarah: Complete roadmap
```

Into a formatted Google Doc with:
- "Product Team Sync" as Heading 1
- "Attendees" as Heading 2
- Proper bullet formatting
- Checkbox for action item
- "@sarah" in bold blue

## API Reference

### Main Classes

#### `MarkdownToGoogleDocs`

**Methods:**
- `authenticate()` - Authenticates with Google API
- `create_document(title)` - Creates a new Google Doc
- `convert(markdown_text)` - Converts markdown to Google Doc
- `parse_and_convert(markdown_text)` - Parses markdown and generates API requests
- `apply_formatting()` - Applies all formatting to the document

## Contributing

Feel free to submit issues, fork the repository, and create pull requests for any improvements.

## License

MIT License - feel free to use this project for any purpose.

## Author

Created as part of a Software Engineer Assessment Task

## Acknowledgments

- Google Docs API documentation
- Google Colab team for providing the development environment

---

**Note**: This script is designed specifically for Google Colab. For local execution, you'll need to set up OAuth2 credentials separately.
