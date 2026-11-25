# Setting up LogLens and how to use it

This will explain how to get the LogLens files, find repository root, and run LogLens for the first time. This guide is for computing science student and new technical intern who have knowledge on CSV files and terminal. 

To understand how LogLens works, see the README file. 

## Quick Note before you start

* Python 3.10 or newer, pip is not required here.

## Step 1: Get the LogLens files

1. Open the repository page on the Github
2. Select the Code button, which you will then see Download ZIP
3. Extract zip from the download folder

## Step 2: Go to the respository root 
The repository root contains the `loglens.py` and `data` folder. Keep in mind that you must every LogLens command from the repository root.

Note:
1. In your terminal, change your working directory to the folder you extracted in Step 1.
2. List the contents of the current folder and confirms that `loglens.oy` is in the folder. If it does not, you are not in the repository root. Check which folder have the file and change the directory to that folder.

## Step 3: Verify your setup with the sample file

Do a test on the sample file first before you test your own file, verified that the output match the expected output. 

1. Count the `ERROR` records:
```bash
python loglens.py --file data/sample_logs.csv --level ERROR
```
Expected output:
```text
Records matching ERROR: 2
```
2. Count all records by omitting the optional the optional `--level`:
```bash
python loglens.py --file data/sample_logs.csv
```
Expected output: 
```text
Records matching ALL: 6
```

If the output result does not match the expected output, check the troubleshooting section.

## Step 4: Run LogLens on your own CSV file

1. Check that the CSV file's first row contains the column header, spelled exactly:
```text
timestamp, level, message
```
The level column only accept one of the accepted log level: `INFO`, `WARN`, or `ERROR` all in uppercase.
2. From the repository root, run either command from step 3, or replacing `data/sample_logs.csv` with your own file.
To count different level, replace `ERROR` with `INFO` or `WARN`.

Note: LogLens runs locally on your computer and it does not transmit or upload your data and it does not modify your data, just read only.

## Troubleshooting 
| Problem | Want to check |
|---|---|
|`python` command not found | Try `python3` or `py` instead. Make sure the python version is 3.10 or newer | 
| LogLens cannot find the `loglens.py` file or your CSV file | Check which folder is `loglens.py` or the CSV file at and change the directory to the directory where the file at | 
| Not sure which command-line to use | Run `python loglens.py --help |

## Reporting the problem 

If a command does not work:

Check the troubleshooting section in installation guide
Run python loglens.py --help to check the valid command-line.
Report the problem to the repository developers, describe what problem you ran into, what is the error message.

Note: it is important not to upload any file that contains private/sensitive logs publicly.
