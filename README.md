# Manga Downloader

A powerful Python program designed to simplify the process of downloading manga from popular online sources. This application supports `mangakakalot.gg`, `natomanga.com`, and `nelomanga.net`, offering both a command-line interface (CLI) for automation and a user-friendly graphical user interface (GUI) for easy navigation.

## Features

-   **Multi-site Support:** Download manga from popular sites like MangaKakalot, Natomanga, and Nelomanga.
-   **Search Functionality:** Easily search for manga by title across supported websites.
-   **Chapter Management:** View and select specific chapters for download.
-   **Configurable Settings:** Customize download directory and other preferences.
-   **CLI & GUI:** Choose between a command-line interface for scripting or a user-friendly graphical interface.
-   **Cloudflare Bypass (via Cookies):** Supports bypassing Cloudflare protection on certain sites by utilizing browser-provided cookies.

## Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/Yui007/mangakakalot.git
    cd mangakakalot
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    # On Windows
    .\venv\Scripts\activate
    # On macOS/Linux
    source venv/bin/activate
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r manga_downloader/requirements.txt
    ```

## Usage

After completing the installation steps and activating your virtual environment, ensure your current working directory is the root of the cloned repository (`mangakakalot`). From this directory, you can run the application using either the Command-Line Interface (CLI) or the Graphical User Interface (GUI).

### Command-Line Interface (CLI)

For detailed CLI usage, refer to [manga_downloader/cli/usage.md](manga_downloader/cli/usage.md).

**Basic Search Example:**
```bash
python -m manga_downloader.cli.main search "solo leveling" --site mangakakalot
```

**Download Example:**
```bash
python -m manga_downloader.cli.main download --manga-url "https://www.natomanga.com/manga/immortal-undertaker" --chapter-range "1-5"
```

### Graphical User Interface (GUI)

For detailed GUI usage, refer to [manga_downloader/gui/USAGE.md](manga_downloader/gui/USAGE.md).

**Launch the GUI:**
```bash
python -m manga_downloader.gui.main
```

## Configuration

### `manga_downloader/core/config.py`

This file contains base URLs for manga websites and default HTTP headers.

### `manga_downloader/core/cookies.json`

This file is used to store cookies for sites protected by Cloudflare (e.g., `nelomanga.net`). If you encounter issues searching or accessing content from such sites, you may need to manually update this file with cookies from your browser.

**Example `cookies.json` structure:**
```json
{
    "nelomanga": {
        "__cflb": "YOUR_CF_LB_COOKIE_VALUE",
        "cf_clearance": "YOUR_CF_CLEARANCE_COOKIE_VALUE",
        "__cf_bm": "YOUR_CF_BM_COOKIE_VALUE"
    }
}
```
**Note:** Do not commit your personal cookie values to public repositories. The `cookies.json` file should be kept empty or with placeholder values when sharing on GitHub.

## Contributing

Contributions are welcome! Please feel free to open issues or submit pull requests.

## License

This project is licensed under the [MIT License](LICENSE).
