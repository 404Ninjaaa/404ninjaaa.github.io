---
title: Reverse (ShadowCipher)
time: 2025-07-29 13:48:00
categories: [challenges]
tags: [challenges]
image: /assets/posts/challenges/1.jpg
 
---
 
 Here, I present the ShadowCipher CTF challenge, blending reverse engineering and a puzzle, inspired by elite hacking crews.
 
 # Intermediate
 
 ## ShadowCipher Challenge
 
 **Description**:
 
 A mysterious binary holds a secret flag, and a cryptic riddle hides a validation code. Can you reverse the binary to uncover the flag and solve the riddle to complete the challenge? Download the challenge files and validate your answers!
 
 **Download**:
 
 [shadowcipher_challenge.zip](https://mega.nz/file/tcJnnLgB#jTMdz-ybzdlCK0eP0CBJ8WpnVZhrQt7Ui-ctD52rgn8)
 
 ---
 
 **Files Provided**:
 
 ```
 validator.exe    ← Binary to reverse
 core.exe         ← Support component
 loader.ps1       ← Runs validator.exe
 riddle.txt       ← Riddle puzzle
 README.txt       ← Instructions
 ```
 
 **Solution Hints**:
 
 1. **Reverse Engineering**:
    - Use Ghidra or x64dbg to analyze `validator.exe`.
    - Look for strings or compare operations to uncover the hidden flag.
 
 2. **Puzzle**:
    - Open `riddle.txt` in Notepad.
    - Solve the riddle: "What has keys but can't open locks?"
    - Hint: Think musical instruments.
 
 3. **Validation**:
    - Run `powershell -ExecutionPolicy Bypass -File loader.ps1`.
    - Enter the flag and riddle answer into `validator.exe`.
    - Example output:
      ```
      ShadowCipher CTF Challenge
      Reverse this binary to find the flag, then enter it below.
      Enter the flag: [your_flag_here]
      Enter the riddle answer from riddle.txt: [your_answer_here]
      Correct! Validation successful.
      ```
 
 **Tools Recommended**:
 - [Strings](https://learn.microsoft.com/en-us/sysinternals/downloads/strings) for extracting all human-readable text from a binary file
 - [Ghidra](https://ghidra-sre.org/) for reverse engineering.
 - [x64dbg](https://x64dbg.com/) for debugging.
 - Notepad for riddle.txt.
 
 ---
