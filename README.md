# LinkedIn Scraping Tool

This project automates the process of scraping comments from LinkedIn posts. Using Selenium, it logs into LinkedIn, navigates to a specified post, loads all comments, and selects the "Most Recent Comments" option. The scraped HTML page is saved for further processing with tools like BeautifulSoup.

---

## Features

- **Automated Login**: Logs into LinkedIn with user credentials.
- **Comment Sorting**: Selects "Most Recent Comments" from the post's comment menu.
- **Dynamic Comment Loading**: Automatically clicks "Load More Comments" until all comments are visible.
- **HTML Page Capture**: Saves the complete post's HTML for parsing and analysis.

---

## Prerequisites

1. **Python Environment**: Ensure you have Python 3.7 or later installed.
2. **Required Packages**: Install the dependencies listed in `requirements.txt`.
3. **Edge WebDriver**: Download and place the Microsoft Edge WebDriver executable in your system. Update the `executable_path` in the script to match its location.

---

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/Filippo2605/Scraping-Linkeding-Post-s-comments.git
   cd Scraping-Linkeding-Post-s-comments
   ```

2. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up the Edge WebDriver:
   - Download the WebDriver from [Microsoft Edge Driver](https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/).
   - Place it in a suitable location and update `executable_path` in the code.

---

## Usage

1. Open the Python script or Jupyter Notebook and configure the following variables:
   - **`your_edge_driver_path`**: Path to the Edge WebDriver.
   - **`your_email`**: Your LinkedIn login email.
   - **`your_password`**: Your LinkedIn login password.
   - **`post_url`**: URL of the LinkedIn post you want to scrape.

2. Run the script:
   ```bash
   python main.py
   ```

3. The script will:
   - Log in to LinkedIn.
   - Open the specified post.
   - Load and sort the comments by "Most Recent."
   - Save the page source as `debug_page.html`.

---

## Post-Processing

To parse and analyze the saved `debug_page.html` file, you can use tools like BeautifulSoup. For example:

```python
from bs4 import BeautifulSoup

# Read the saved HTML file
with open("debug_page.html", "r", encoding="utf-8") as file:
    soup = BeautifulSoup(file, "html.parser")

# Extract and process data
# Example: Extract all comment texts
comments = [comment.text.strip() for comment in soup.find_all("span", class_="comments-comment-item__main-content")]
print(comments)
```

---

## Disclaimer

This project is for educational purposes only. Scraping data from LinkedIn must comply with their [Terms of Service](https://www.linkedin.com/legal/user-agreement). Unauthorized scraping may result in account suspension or legal action.

---

## Contributions

Contributions are welcome! Feel free to open an issue or submit a pull request for enhancements or bug fixes.

---

