# VidSnapAI

A Flask web app that lets users upload images with a description, stores them in unique UUID folders, and generates text files useful for media processing. Includes a gallery view for saved reels.

## Features
- Upload multiple images (`png`, `jpg`, `jpeg`)
- Each upload session saved in a unique UUID folder
- Stores user description in `desc.txt`
- Creates `input.txt` containing file list with duration metadata
- Gallery page loads reels from static folder
- Secure filename handling
- Auto folder creation on first run

## Folder Structure
```
VidSnapAI/
│ app.py
│ README.md
│
├ user_uploads/               # Auto-created
│   └ <UUID>/                # Each upload session
│       │ desc.txt           # User text input
│       │ input.txt          # File list + duration
│       └ uploaded images
│
├ static/
│   └ reels/                 # Gallery loads from here
│
└ templates/
    │ index.html
    │ create.html
    │ gallery.html
    └ other UI files
```

## Allowed Upload Formats
```
png, jpg, jpeg
```

## Setup & Run
```bash
git clone <repo-link>
cd VidSnapAI
pip install flask werkzeug
python app.py
```

## Routes
| Route | Method | Purpose |
|-------|--------|---------|
| `/` | GET | Home page |
| `/create` | GET, POST | Upload images + save description |
| `/gallery` | GET | Display reels from static folder |

## Notes
- The app saves uploads in `user_uploads/<UUID>/`
- `desc.txt` is overwritten per request
- `input.txt` appends file names in FFmpeg-friendly format

## License
MIT

## Author
Pankaj Sulakhe
