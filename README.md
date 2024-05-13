# Web-Scraping---Downloading-King-of-Glory-Skin-Images

This Python script is designed to download hero skins from a specified JSON file containing hero data. It reads information about each hero and then fetches their skins from an online source.

## Prerequisites

Before running the script, ensure that the following libraries are installed in your Python environment:

- `json`: For parsing JSON files.
- `requests`: For making HTTP requests to fetch web pages and skin images.
- `lxml.html`: For parsing HTML content to extract skin names.
- `os`: For directory operations.
- `time`: For managing download intervals.

You can install the required libraries using pip:

```bash
pip install requests lxml
```

## JSON File Structure

The script expects a JSON file (`herolist.json`) with an array of hero entries. Each entry should have the following structure:

```json
{
    "ename": 105,          // Unique numeric ID corresponding to the hero.
    "cname": "廉颇",        // Hero's name.
    "title": "正义爆轰",    // Hero's title.
    "new_type": 0,         // Type of hero (new or existing).
    "hero_type": 3,        // Category of the hero.
    "skin_name": "正义爆轰|地狱岩魂",  // Names of the skins separated by '|'.
    "moss_id": 3627        // Additional identifier, not used in the script.
}
```

## How the Script Works

1. **Reading Hero Data:**
   - The script opens and reads the `herolist.json` file to extract hero data.

2. **Web Page and Skin Download:**
   - For each hero, the script constructs a URL to fetch the hero's detail page.
   - It sends a request to the URL and parses the returned HTML to extract skin names.
   - The script then creates a directory named after the hero (if it doesn't already exist).
   - It constructs URLs for each skin image and downloads them into the appropriate directory.

3. **File Naming and Saving:**
   - Skin images are saved with their respective names extracted from the hero's page.
   - Files are named according to the skin names, and all images are saved in JPG format.

## Usage

To run the script, make sure that you are in the directory containing the script and the `herolist.json` file, then execute:

```bash
python hero_skin_downloader.py
```

## Output

The script will output the download progress in the console, indicating when each skin download starts and completes. Skin images will be saved in directories named after each hero under the script's running directory.

## Note

This script is meant for educational purposes and to automate the process of downloading publicly available skin images for heroes listed in the `herolist.json` file. Always ensure that you have the right to access and download any content from the web.
