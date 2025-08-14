# Assignment 1 — ExifTool Metadata Analysis

**Analyst:** Ryan S Mathew  
**Date:** 2025-08-14  
**Evidence:** Forensics-image.png  

---

## 🔎 Image Overview
- **Filename:** Forensics-image.png
- **File Size:** 1,144 KB
- **Image Dimensions:** 1439×753 (W×H)
- **File Signature (Magic Bytes):** FF D8 FF E0 … → **JPEG (JFIF + EXIF)**  
  *Note:* Filename says `.png` but header is JPEG → renamed at some point.

## 📸 Camera / Software
- **Make:** Not present
- **Model:** GIMP 2.10.24
- **Editing Software:** Not present

## 🌍 Geolocation
- **GPS Latitude / Longitude:** No GPS data
- **Map Link:** N/A

## 🕐 Timestamps
- **DateTimeOriginal:** Not present
- **ModifyDate:** 2021:04:21 11:06:39
- **Comment on consistency:** None

## 🧰 Method (commands run)
```bash
# Full dump
exiftool -a -u -g1 Forensics-image.png

# Focused fields
exiftool -DateTimeOriginal -ModifyDate -Software -Make -Model -GPSLatitude -GPSLongitude -GPSAltitude Forensics-image.png

# Hex header (PowerShell)
Get-Content .\Forensics-image.png -Encoding Byte -TotalCount 32 | Format-Hex

# Strings (PowerShell)
$bytes = [IO.File]::ReadAllBytes('.\Forensics-image.png')
$text  = -join ([char[]]$bytes)
[regex]::Matches($text,'[\x20-\x7E]{6,}') | % { $_.Value } | Select -First 40

SHA256 Hash: EFECB358E1ADE19D08ACF1126B846971982FB8B3A82F67BDF7401A8972FD241A
