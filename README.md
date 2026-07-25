# MediaShield CLI - Provenance & Protection Suite
Version: 1.0.0

Thank you for purchasing MediaShield CLI! This suite automatically protects your media assets using SHA-256 hashing, embeds visual watermarks, and writes copyright metadata directly into your files.

--------------------------------------------------------------------------------

## What is MediaShield CLI? & Who is it for?

MediaShield CLI is a professional-grade command-line utility built specifically for creators, photographers, videographers, and digital agencies who need absolute proof of ownership and content integrity.

It is designed for:
• Independent Content Creators & Photographers who want to secure their visual assets against unauthorized use or digital tampering.
• Digital Agencies & Media Houses that manage large volumes of media files and require automated, verifiable copyright embedding.
• Developers & Sysadmins looking for a lightweight, scriptable Bash solution to monitor and protect directories automatically.

> **Note on Compatibility:** MediaShield CLI functions perfectly for local archives, direct client deliveries (FTP/Cloud), and legal provenance. Please note that certain social media platforms automatically strip embedded metadata upon upload.

--------------------------------------------------------------------------------

## What the Installer Does

The included `install.sh` script automates the entire setup process. When executed, it automatically:

1. **Installs Required System Dependencies:**
   - `ffmpeg` (for video watermarking, frame rendering, and video metadata injection)
   - `libimage-exiftool-perl` (`exiftool` for precise EXIF/XMP metadata embedding in images)
   - `inotify-tools` (for real-time directory event monitoring)
2. **Sets Up Directory Structure & SFTP Permissions:**
   - Creates `/opt/mediashield/` with all necessary subdirectories (`input/`, `output/`, `archive/`, `logs/`, `bin/`).
   - Automatically grants full read/write permissions (`777`) to processing directories to allow seamless non-root uploads via SFTP, FTP, and SMB clients.
3. **Deploys Executables & Permissions:** Moves core processing and watching scripts to `/opt/mediashield/bin/` and sets execution rights (`+x`).
4. **Configures & Starts Systemd Service:** Registers `mediashield.service` so the automated background watcher starts on boot and restarts automatically if needed.

--------------------------------------------------------------------------------

## Quick Start Guide (3 Steps)

### 1. Extract & Navigate

Extract the downloaded ZIP archive into its dedicated directory and move into it:

  unzip MediaShield_Suite_v1.0.0.zip -d MediaShield_Suite_v1.0.0
  cd MediaShield_Suite_v1.0.0

### 2. Run Automated Installation

Make `install.sh` executable and run it with `sudo` permissions (required for package installation, permission setup, and systemd service registration):

  chmod +x install.sh
  sudo ./install.sh

### 3. Verify & Start Using

Once installed, the background service (`mediashield.service`) is active immediately and listening for new files.

• Check Service Status:
  sudo systemctl status mediashield.service

• Process Files (SFTP / FTP / Local): Simply copy or upload your images (`.jpg`, `.png`, etc.) or videos (`.mp4`, `.mov`, etc.) directly into:
  /opt/mediashield/input/

• Retrieve Protected Files: Your protected, watermarked media with embedded SHA-256 signatures will automatically appear in:
  /opt/mediashield/output/

--------------------------------------------------------------------------------

## Licensing & Pricing

MediaShield CLI is distributed as commercial software to protect your media assets against manipulation and unauthorized use through automated SHA-256 signatures and embedded copyright metadata. Choose the plan that fits your needs:

| License Tier | Price | Features | Buy |
| :--- | :--- | :--- | :--- |
| **Standard License** | **€29** | Lifetime access, up to 3 server activations | [**Buy Standard**](https://mediashield.lemonsqueezy.com/checkout/buy/0e4fc8c6-f6c9-488b-b36c-238540af489f) |
| **Agency License** | **€79** | Lifetime access, unlimited activations, priority support | [**Buy Agency**](https://mediashield.lemonsqueezy.com/checkout/buy/0e4fc8c6-f6c9-488b-b36c-238540af489f) |

> **Note:** After purchase, you will immediately receive your `.zip` archive containing all tools alongside your unique license key.

--------------------------------------------------------------------------------

## Compatibility Note

• Linux (Ubuntu / Debian / RHEL) : Fully supported natively via Bash/POSIX terminal and `systemd`.
• macOS                         : Supported natively via POSIX terminal (manual background process execution).
• Windows                       : Supported via WSL (Windows Subsystem for Linux).

--------------------------------------------------------------------------------

## Support

For technical assistance, updates, or license questions, please contact support or visit our official GitHub repository.
