# Downloads Organizer

A simple script that automatically sorts files in your Downloads folder into subfolders by client name — no engineering experience required.

---

## What It Does

If you have hundreds of files scattered across your Downloads folder and the client's name is somewhere in the filename, this script will:

- Read a list of client names (and any name variations) from a CSV file you provide
- Scan your entire Downloads folder, including subfolders
- Show you a preview of exactly where every file will be moved **before** anything happens
- Create a folder for each client and move all matching files into it
- Move any files that don't match a client name into an `Other/` folder
- Leave your original Downloads folder untouched until you confirm

All organized files land in a new `Organized/` folder inside Downloads — nothing is deleted.

---

## Requirements

- A Mac computer
- Python 3 (comes pre-installed on most Macs)

To confirm Python is installed, open **Terminal** and type:
```
python3 --version
```
If you see a version number, you're good to go.

---

## Setup

### Step 1 — Download the script

Click the green **"Code"** button on this page → **"Download ZIP"**, unzip it, and move `organize_downloads.py` to your home folder (the one that has your name, e.g. `/Users/yourname/`).

### Step 2 — Create your client list

Create a file called `clients.csv` and save it directly in your **Downloads folder**.

Open it in Excel, Google Sheets, or any text editor. The format is:

| Column A (required) | Column B (optional) | Column C (optional) |
|---|---|---|
| Acme Corporation | Acme Corp | ACME |
| Blue Sky Partners | Blue Sky | BSP |
| Johnson Consulting | Johnson & Consulting | |

- **Column A** is the official client name — this becomes the folder name
- **Additional columns** are alternate versions of the name that might appear in your filenames
- No header row needed — just start with your first client on row 1

---

## How to Run It

1. Open **Terminal** (press `Cmd + Space`, type "Terminal", hit Enter)
2. Paste the following and press Enter:

```
python3 ~/organize_downloads.py
```

3. The script will show you a preview of every file and where it's going:

```
FILES TO BE ORGANIZED:
────────────────────────────────────────────────────────
  Acme Corporation/
      → Acme_proposal_2023.pdf
      → Acme_contract_final.docx

  Blue Sky Partners/
      → BlueSky_deck_Q3.pptx

  Other/  (no client match found)
      → amazon_receipt.png
      → random_download.pdf
────────────────────────────────────────────────────────
  42 file(s) matched to clients
  8 file(s) → Other
  Destination: /Users/yourname/Downloads/Organized/
────────────────────────────────────────────────────────

Type YES to move files, or NO to cancel:
```

4. Review the list. If everything looks right, type `YES` and press Enter. To cancel without moving anything, type `NO`.

---

## Result

After running, your Downloads folder will contain a new `Organized/` folder:

```
Downloads/
  Organized/
    Acme Corporation/
      Acme_proposal_2023.pdf
      Acme_contract_final.docx
    Blue Sky Partners/
      BlueSky_deck_Q3.pptx
    Other/
      amazon_receipt.png
      random_download.pdf
```

---

## Good to Know

- **Nothing moves until you type YES** — the preview is just a plan
- **Safe to run multiple times** — files already in `Organized/` won't be processed again
- **No files are deleted** — everything either goes to a client folder or `Other/`
- **Duplicate filenames are handled automatically** — if two files share a name, the second one is renamed (e.g. `filename_1.pdf`) so nothing gets overwritten
- **Name matching is flexible** — matching is case-insensitive, so `ACME`, `Acme`, and `acme` all match the same client
