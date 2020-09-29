# dRPG downloads and keeps your purchases from DriveThruRPG up to date

## Prerequisites

This script is tested with and requires Python 3.8.

You need to install dependencies from `requirements.txt` before running it:

```bash
python3.8 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

## How to use it

1. Go to [your account settings](https://www.drivethrurpg.com/account_edit.php)
   and generate a new application key.
2. Copy the key and run the script with: `DRPG_TOKEN=<YOUR_TOKEN> python drpg.py `.
3. Now just sit, relax and wait. Initial synchronization may take a while.  On
   consecutive runs the script will download only changed files.

## Advanced options

By default the script does not compare files by md5 checksum to save time. You
can turn it on by setting `DRPG_PRECISELY=true`.

You can change a log level by setting `DRPG_LOGLEVEL=<YOUR_LOG_LEVEL>`. Choices
are DEBUG, INFO, WARNING, FATAL.

## Development

Pull requests and bug reports are welcomed!

### Running tests

To run tests, install dependencies from `requirements.dev.txt` and run tests
with `unittest`:

```bash
pip install -r requirements.dev.txt
python -m unittest
```

### Building a binary distribution

Stand-alone executables are generated using PyInstaller. To generate a binary
for your platform install dev requirements and run PyInstaller:

```bash
pip install -r requirements.dev.txt
pyinstaller drpg.spec
```

The binary will be saved in a `dist/` directory.
