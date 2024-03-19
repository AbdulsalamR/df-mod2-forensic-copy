### 🖥️💻 df-mod2-forensic-copy 💻🖥️

### 🗃️Digital Forensics - PowerShell Skills 

Welcome to this repository, specifically crafted to aid users in honing their 
PowerShell expertise for digital forensics tasks. 
Our main objective revolves around duplicating forensic evidence and 
meticulously verifying the replicated data using hash values, 
thereby guaranteeing the integrity of the evidence.

Contained within this repository are a plethora of PowerShell scripts and 
supplementary resources meticulously curated to 
foster the development of practical proficiencies in the realm of digital forensics.

### 🧰 Recommended Tools
- Git
- PowerShell
- VS Code
- VS Code Extension: Remote Repositories (by Microsoft)
- VS Code Extension: PowerShell (by Microsoft)

### 🗒️ Technical Notes

# To run a script in PowerShell terminal using the `./` notation, follow these steps:

1. Open PowerShell terminal.
2. Navigate to the directory where your script is located using `cd` command.
3. Type `./script_name.ps1` and hit ENTER to execute the script.

Make sure to replace `script_name.ps1` with 
the actual name of your PowerShell script file. 
The `./` notation ensures that the script is executed from 
the current working directory and prevents any 
potential conflicts with system commands or aliases.

### 📗 PowerShell Commands

### 🔖✔️ 1. `New-Item -ItemType Directory -Force -Path [path]`
  - This command creates a new directory at the specified path.
  - `-ItemType Directory` specifies that a directory should be created.
  - `-Force` allows the command to overwrite existing directories with the same name.
  - `-Path [path]` specifies the location where the new directory will be created.

## 🔖✔️ 2. `Copy-Item [source] [destination]`:
  - This command copies files or folders from a source location to a destination location.
  - `[source]` represents the path of the file or folder to be copied.
  - `[destination]` represents the path where the copied file or folder will be placed.

## 🔖✔️ 3. `Get-FileHash [file] -Algorithm [algorithm]`:
  - This command computes the hash value of a specified file using the chosen hashing algorithm.
  - `[file]` represents the path of the file for which the hash value is to be computed.
  - `-Algorithm [algorithm]` specifies the hashing algorithm to be used.

## 🔖✔️  4. `Out-File [file_path]`:
  - This command saves the output of a command to a text file.
  - The output of a command can be piped to `Out-File`, and `[file_path]`
    specifies the location and name of the text file to be created.

These commands are essential tools for various tasks in PowerShell, 
particularly in scenarios like digital forensics 
where file manipulation and verification are common requirements.


### ❗📑 Case 001 

For Case 001, 

1. Create your own evidence files in a subfolder (e.g., 001-evidence).
2. Modify the script to create your own copy and hash resuts.

### 🏃🏃‍♀️ Run Script

## In VS Code 🧭  
 - use Terminal / New Terminal to open a terminal window. 
 - If the default terminal is cmd, use the drop-down to change to PowerShell.

### ❗📜 This Scripts makes a copy and writes the hash of the file to a text file

## Hit the up arrow to rerun the last command
## Hit the tab key to autocomplete

## ❕🛠️ Create a folder for our results 
New-Item -ItemType Directory -Force -Path ./001-RESULTS

## ❕🛠️ Create a folder for our forensic copy
New-Item -ItemType Directory -Force -Path ./001-evidence

## ❕🛠️ Copy the evidence files to a new folder
Copy-Item ./001-evidence/evidence1.txt ./001-evidence-COPY/evidence1.txt
Copy-Item ./001-evidence/evidence2.txt ./001-evidence-COPY/evidence2.txt

## ❕🛠️ Calcuate the hash of each evidence file and write it to a text file
Get-FileHash ./001-evidence/evidence1-1.txt -Algorithm SHA256 | Out-File ./001-RESULTS/hash1-1.txt
Get-FileHash ./001-evidence/evidence2-2.txt -Algorithm SHA256 | Out-File ./001-RESULTS/hash2-2.txt

## ❕🛠️ Calculate the hash of each copied file and write it to a text file
Get-FileHash ./001-evidence-COPY/evidence1.txt -Algorithm SHA256 | Out-File ./001-RESULTS/hash1-1-copy.txt
Get-FileHash ./001-evidence-COPY/evidence2.txt -Algorithm SHA256 | Out-File ./001-RESULTS/hash2-2-copy.txt

## ☑️ The commands above perform the follow.
1. Create an example evidence folder with files
2. Create a forensic copy of the evidence for analysis
3. Recheck hashes to ensure no changes have been introduced to the copy.
4. Undo all the files and clean things up. 

### 🦸‍♂️💻 Author
Abdulsalam Rasak
https://github.com/AbdulsalamR 
