<div align="center">

<img src="./logo.png" alt="Offside Logo" width="400" height="250">

# Offside Video Catalog

**A simple local video gallery and catalog for browsing, searching, and playing video files.**

</div>

> **Note:** Offside is a simple, personal side project created purely for fun and personal convenience. It is provided "as-is" without any guarantees or maintenance obligations.

---

## 🌟 Features

* **Thumbnail Preview** — Displays a custom image next to each video for quick visual recognition.
* **Video Gallery** — Automatically organizes videos into a simple scrollable gallery.
* **Fast Search** — Search videos by their file names.
* **Built-in Playback** — Click a video thumbnail to open and play the corresponding video.
* **Local Folder Indexing** — Automatically scans the `MyVideos` directory for supported video files.
* **Scrollable Interface** — Browse large collections of videos using the mouse wheel and scrollbar.
* **Cross-Platform Playback** — Attempts to use VLC first and falls back to the operating system's default video player.

---

## 📁 Project Structure

The application expects your videos and their corresponding preview images to be placed inside a folder named `MyVideos`.

```text
Offside/
│
├── main.py
├── logo.png
│
└── MyVideos/
    ├── Video 01.mp4
    ├── Video 01.png
    │
    ├── Video 02.mkv
    ├── Video 02.jpg
    │
    ├── Video 03.avi
    ├── Video 03.jpeg
    │
    └── ...
```

### Important

The preview image should have the **same filename as the video**, while the image extension can be different.

For example:

```text
MyVideos/
├── Match.mp4
└── Match.jpg
```

or:

```text
MyVideos/
├── Match.mkv
└── Match.png
```

The video and image are matched based on their filename.

---

## 🎬 Supported Video Formats

The current implementation supports the following video extensions:

* `.mp4`
* `.mkv`
* `.avi`
* `.mov`
* `.3gp`

The application can be extended to support additional formats by adding their extensions to the `VIDEO_EXTENSIONS` list in the source code.

---

## 🖼️ Thumbnail Images

Each video can have a corresponding preview image.

The image should use the **same base filename** as the video.

For example:

```text
MyVideos/
├── Example.mp4
└── Example.png
```

The image format can be:

* PNG
* JPG / JPEG
* WebP
* Other formats supported by Pillow

> **Note:** The current source code specifically searches for a `.png` file. To support all Pillow-compatible image extensions automatically, the thumbnail lookup logic needs to be extended.

---

## 🔎 Searching

Offside includes a search box for quickly filtering videos.

The search is performed against the **video filename**.

For example, if the folder contains:

```text
Barcelona vs Real Madrid.mp4
Manchester United vs Chelsea.mkv
Barcelona Training.avi
```

Searching for:

```text
Barcelona
```

will display:

```text
Barcelona vs Real Madrid.mp4
Barcelona Training.avi
```

The search is case-insensitive.

Press **Enter** after entering the search query to update the gallery.

---

## ▶️ Playing Videos

Clicking on a video's thumbnail opens the corresponding video.

Offside first attempts to launch the video using **VLC Media Player**:

```text
VLC → Operating System Default Player
```

If VLC is not available, the application falls back to the operating system's default video player.

This allows the application to work with different video formats as long as the installed player supports them.

---

## 🚀 How to Use

### 1. Prepare the Project

Clone or download the repository and make sure the project has the following basic structure:

```text
Offside/
├── main.py
├── logo.png
└── MyVideos/
```

### 2. Add Your Videos

Place your video files inside:

```text
MyVideos/
```

For example:

```text
MyVideos/
├── Match 01.mp4
├── Match 01.png
├── Match 02.mkv
├── Match 02.jpg
└── Match 03.avi
```

### 3. Run the Application

Run the Python program:

```bash
python main.py
```

The application will scan `MyVideos` and display the available videos.

### 4. Browse and Search

* Scroll through the gallery to browse videos.
* Use the search box to filter videos by filename.
* Click a thumbnail to play the corresponding video.

---

## 🐍 Requirements

The Python implementation uses:

* Python
* Tkinter
* Pillow

Install Pillow with:

```bash
pip install Pillow
```

`Tkinter` is normally included with standard Python installations on Windows.

For the best playback compatibility, **VLC Media Player** is recommended.

---

## ⚠️ Important Behavior

If the `MyVideos` directory does not exist, Offside automatically creates it.

If no matching videos are found, the application displays an appropriate message.

A video without a corresponding thumbnail image is currently not displayed in the gallery.

---

## 🏗️ Executable Build

A standalone `.exe` build can also be provided for users who do not want to run the Python source code directly.

The executable can be configured to work with a designated `MyVideos` directory.

---

## 🗺️ Roadmap & Future Plans

* [ ] **Flexible Thumbnail Extensions** — Automatically detect `.png`, `.jpg`, `.jpeg`, `.webp`, and other supported image formats.
* [ ] **Custom Folder Selection** — Allow users to dynamically select or change the target video directory.
* [ ] **Improved Search** — Add more advanced filtering and sorting capabilities.
* [ ] **Automatic Thumbnail Generation** — Generate video thumbnails automatically when no preview image exists.
* [ ] **Better Metadata Support** — Display additional information such as duration, resolution, and file size.
* [ ] **C++ Rewrite** — Re-implement the core indexing and gallery logic in C++ for faster performance and lower resource consumption.
* [ ] **C++ Executable Release** — Provide a compiled `.exe` version of the C++ implementation.

---

## 📜 License

Distributed under the [MIT License](LICENSE).

See the `LICENSE` file for the complete license text.

---

## 📌 Disclaimer & Liability

* **AS-IS Basis:** This software is provided "as is", without warranty of any kind, express or implied.
* **Personal Hobby:** Offside was created as a personal experiment and convenience project. It is not intended for commercial or production environments.
* **No Liability:** The author takes no responsibility or liability for errors, performance issues, compatibility problems, or potential data loss resulting from the use of this software.
* **Casual Maintenance:** Updates, improvements, and bug fixes may occur sporadically or may not occur at all.
