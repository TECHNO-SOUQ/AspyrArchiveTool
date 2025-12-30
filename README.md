# Aspyr Archive Tool

**Aspyr Archive Tool** is a simple command-line utility for unpacking and packing Aspyr Android `.obb` archives.

## Supported Games
- Star Wars: Knights of the Old Republic II (Android)
- Jade Empire: Special Edition (Android)
- Fahrenheit: Indigo Prophecy Remastered (Android)

## What It Can Do
- Unpack `.obb` archives
- Pack folders back into `.obb`
- Full compression mode
- Selective compression via file list
- Append CRC64 checksum (required for Jade Empire)

## Usage

```bash
AspyrArchiveTool.exe <flags> [input] [output]
```

### Flags

| Flag | Description |
|-----|------------|
| `-u` | Unpack archive |
| `-p` | Pack folder |
| `-c` | Enable compression |
| `-c list.txt` | Selective compression |
| `-crc` | Append / refresh CRC64 checksum |

## Examples

### Unpack an OBB
```bash
AspyrArchiveTool.exe -u example.obb
```

### Pack folder (no compression)
```bash
AspyrArchiveTool.exe -p extracted_folder
```

### Pack with compression + CRC
```bash
AspyrArchiveTool.exe -p extracted_folder -c -crc
```

### Pack with selective compression
```bash
AspyrArchiveTool.exe -p extracted_folder example.obb -c compress_list.txt
```

### Add CRC to existing OBB
```bash
AspyrArchiveTool.exe -crc example.obb
```

## Selective Compression List (`compress_list.txt`)

```txt
# Folders
scripts/
dialogs/
sounds/

# File types
*.xml
*.tlk
*.txt

# Single files
global.2da
```
