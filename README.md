# diskWasher

Wipe partition remnants from a replacement disk and run basic health checks.

## Usage

```
./diskWasher /dev/sdX
```

## What it does

1. Wipes the first and last 100 MB (clears MBR + GPT headers/tail)
2. Runs a SMART health check (if `smartctl` is available)
3. Benchmarks sequential write and read speed (1 GB each)

## Requirements

- Linux with `blockdev`, `dd`, and `smartctl` (optional)
- Root access to the target disk