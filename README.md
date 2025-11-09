# Metadata-Extraction-using-ExifTool-log2timeline-and-Hidden-Data-Search-using-Steganography-Tools
## AIM:
To extract metadata, perform timeline analysis, and search for hidden data using forensic tools like ExifTool, log2timeline, and steganography detection tools.
## REQUIREMENTS
- **Operating System:** Kali Linux (preferred) or any Linux distro with forensic tools
- **Tools:**
     -  ExifTool – For metadata extraction
     -  plaso/log2timeline – For timeline analysis
- **Steganography tools:** steghide, zsteg, binwalk
- **Test Data:** Image, video, and document files (some with embedded hidden data)
## ARCHITECTURE DIAGRAM
```mermaid
flowchart TD
    A[Sample Files - Images, Videos, Documents] --> B[Metadata Extraction with ExifTool]
    B --> C[Event Timeline Creation with log2timeline]
    C --> D[Hidden Data Search with Steganography Tools]
    D --> E[Evidence Analysis and Documentation]
```
## DESIGN STEPS:
### Step 1:
Use exiftool to extract metadata from files such as images, documents, and videos.

### Step 2:
Use log2timeline and plaso to create and analyze event timelines from system logs and file metadata.

### Step 3:
Apply steganography detection tools like steghide, zsteg, or binwalk to uncover hidden data in media files.

## PROGRAM:
| Step | Action                  | Tool                 | Output                           |
| ---- | ----------------------- | -------------------- | -------------------------------- |
| 1    | Extract file metadata   | ExifTool             | Metadata fields, GPS, timestamps |
| 2    | Generate event timeline | log2timeline / plaso | CSV/HTML timeline                |
| 3    | Search for hidden data  | steghide / binwalk   | Extracted hidden files           |
| 4    | Document findings       | Manual report        | Investigation record             |


## OUTPUT:
### A. Using ExifTool – for file metadata
- **Install:**
```bash
sudo apt update
sudo apt install exiftool -y
```
- **Extract metadata from a file:**
```bash
exiftool image.jpg
```
<img width="1919" height="1078" alt="Screenshot 2025-09-24 153057" src="https://github.com/user-attachments/assets/3165549c-d348-460b-8d0d-50dea6353cc9" />
- **Batch process a folder:**
```bash
exiftool -r /path/to/folder
```
<img width="1919" height="1078" alt="Screenshot 2025-09-24 153151" src="https://github.com/user-attachments/assets/5171597f-8581-46d7-950b-4fd5b87bc7e7" />
- **Useful flags:**
  
- ```-G: Show metadata group```

- ```-time:all: Show only timestamps```

- ```-GPSLatitude -GPSLongitude: Extract GPS data```



### install log2timeline
```
sudo apt install plaso -y
```

```
sudo apt install steghide -y
```
- **Embed data**
```
steghide embed -cf /home/kali/Downloads/wallpaper.jpg -ef /home/kali/Downloads/secret.txt
```
<img width="1919" height="1079" alt="Screenshot 2025-09-24 155714" src="https://github.com/user-attachments/assets/fcf78d77-92b5-467b-8ec2-29d104b489c7" />

<img width="906" height="429" alt="Screenshot 2025-06-13 094702" src="https://github.com/user-attachments/assets/724da2bd-4b7b-4085-98c3-651b96723857" />


- **Extract hidden data:**
```
steghide extract -sf hidden.jpg

```
<img width="673" height="267" alt="Screenshot 2025-06-13 094800" src="https://github.com/user-attachments/assets/2a685c2f-c6d4-43d9-b018-b7df22fd5799" />

### Using binwalk – for file analysis
```bash
sudo apt install binwalk -y
binwalk suspicious.jpg
```
```bash
binwalk /home/kali/Downloads/wallpaper.jpg
```
![WhatsApp Image 2025-09-24 at 16 27 22_cd9ca7bf](https://github.com/user-attachments/assets/ee5182c1-9823-4cd5-9eea-bb94cbfa8649)


## RESULT:
Metadata was successfully extracted, timeline analysis was completed, and hidden data was identified using steganography tools.
