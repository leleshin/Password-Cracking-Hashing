<div align="center">

# 🔐 Cybersecurity Internship – B084
## Week 3: PDF Password Auditing, Recovery & Capture-the-Flag

**Hands-On PDF Hash Extraction, Password Security Assessment & CTF Validation**

**NETWORKWALKS | CYBERSECURITY & PENETRATION TESTING INTERNSHIP**

<img src="https://img.shields.io/badge/Tool-Johnny-0070C0?style=flat-square" />
<img src="https://img.shields.io/badge/Tool-John_the_Ripper-C00000?style=flat-square" />
<img src="https://img.shields.io/badge/Tool-PDF_Hash_Extractor-238F89?style=flat-square" />
<img src="https://img.shields.io/badge/Skill-Password_Auditing-E87500?style=flat-square" />
<img src="https://img.shields.io/badge/Skill-Hash_Analysis-404040?style=flat-square" />
<img src="https://img.shields.io/badge/Skill-CTF-0070C0?style=flat-square" />
<img src="https://img.shields.io/badge/Batch-B084-C00000?style=flat-square" />

</div>

---

## 📌 Project Overview

This repository documents my Week 3 hands-on work in **PDF password security assessment, encrypted PDF hash extraction, authorized password recovery, and capture-the-flag (CTF) validation** during the **NetworkWalks Cybersecurity and Penetration Testing Internship (Batch B084)**.

I examined three password-protected training documents (`My Locked PDF1.pdf`, `My Locked PDF2.pdf`, and `My Locked PDF3.pdf`). I documented the locked-file prompts, used an online PDF hash extraction tool for a training file, and saved three PDF hash representations in `Hash.txt`, `Hash2.txt`, and `Hash3.txt`. I also reviewed the **Johnny** graphical interface and its **John the Ripper** engine, including a completed recovery result for one PDF hash.

The Johnny evidence confirms **one recovered training password, `good-luck`**, with the status **1 cracked, 0 remaining**. Separate screenshots show all three PDFs subsequently opened to NetworkWalks congratulatory or flag pages. These images **do not independently establish which password opened each document**, nor do they show the exact attack mode, wordlist, or cracking duration. This report distinguishes verified observations from details not visible in the evidence.

**Module focus:** PDF hash extraction, password auditing, Johnny / John the Ripper, and CTF evidence validation.  
**Evidence dates:** 19 and 21 November 2026 (visible in screenshots).

### Practical Activities

- Examine three password-protected training PDFs and document their locked states.
- Extract a PDF hash using the OnlineHashCrack PDF Hash Extractor.
- Save and inspect three John-compatible PDF hash records in text files.
- Verify the Johnny configuration and detected John the Ripper executable.
- Review Johnny’s hash import menu and completed password recovery output.
- Open the training PDFs and document the displayed challenge flags.
- Interpret security implications and record the limitations of the evidence.

---

## 🎯 Project Objectives

1. Understand PDF password protection and the purpose of an offline password audit.
2. Extract and preserve PDF hash representations from authorized training documents.
3. Distinguish PDF hash records from recovered plaintext passwords.
4. Configure Johnny to use the installed John the Ripper engine.
5. Identify the appropriate hash-import workflow and interpret recovery results.
6. Document locked and opened states of three training PDF files.
7. Record visible CTF flags accurately without inferring unsupported results.
8. Evaluate weak-password risks and recommend better protection practices.
9. Produce a reproducible, evidence-based report within the authorized scope.

---

## 🛠️ Tools and Supporting Environment

| Tool / component | Purpose |
|---|---|
| Windows desktop | Host environment for the documented exercise |
| OnlineHashCrack PDF Hash Extractor | Browser-based extraction of a PDF hash representation |
| Notepad (`Hash.txt`, `Hash2.txt`, `Hash3.txt`) | Save and inspect extracted hash strings |
| Johnny | GUI for John the Ripper password auditing |
| John the Ripper 1.9.0-jumbo-1 OMP | Password auditing engine detected by Johnny |
| PDF viewer | Observe password prompts and opened challenge documents |
| Three NetworkWalks training PDFs | Authorized CTF practice files |

**Scope:** This report covers only the supplied training materials. The screenshots do not establish that production documents or external systems were tested.

---

## 🔒 Step 1: Inspect the Password-Protected Training PDFs

I began by opening each training PDF and observing its password prompt. The content was not displayed until the documents were later opened.

### Screenshot 1: Locked PDF1

![Password prompt for PDF1](images/04-PDF1-Locked.png)

*Figure 1: `My Locked PDF1.pdf` requests a password.*

### Screenshot 2: Locked PDF2

![Password prompt for PDF2](images/05-PDF2-Locked.png)

*Figure 2: `My Locked PDF2.pdf` requests a password.*

### Screenshot 3: Locked PDF3

![Password prompt for PDF3](images/06-PDF3-Locked.png)

*Figure 3: `My Locked PDF3.pdf` requests a password.*

**Observation:** Each PDF displayed a password-entry dialog. This establishes that password protection was enabled, but does not establish password strength or that the files shared the same password.

---

## 🧾 Step 2: Extract a PDF Hash for the Authorized Test

I used the **OnlineHashCrack PDF Hash Extractor** in a browser to extract a hash representation from the training file `My Locked PDF3.pdf`. The website reported that extraction was complete and displayed an output beginning with `$pdf$`.

### Screenshot 4: Online PDF Hash Extraction

![OnlineHashCrack extraction for PDF3](images/10-PDF-Hash-Extractor.png)

*Figure 4: PDF3 selected in the extractor with a generated PDF hash record.*

| Field | Evidence |
|---|---|
| Selected file | `My Locked PDF3.pdf` |
| Status | Extraction complete |
| Output prefix | `$pdf$` |
| Site-advertised file size limit | 100 MB |
| Site-advertised handling | Files deleted after extraction (not independently verified) |

**Interpretation:** Hash extraction prepares data for password auditing; it does not itself recover a password. The screenshot does not prove that this exact hash was the one recovered in Johnny.

**Security consideration:** Uploading confidential documents to third-party services can expose sensitive information. For real client documents, use an approved local method and follow organizational data-handling requirements.

---

## 🧬 Step 3: Save and Review the Extracted PDF Hash Records

I recorded the PDF encryption/hash representations in three separate text files. These `$pdf$` records contain data used by compatible offline password-auditing tools; they are **not plaintext passwords**.

### Screenshot 5: `Hash.txt` — PDF1

![PDF1 hash text](images/11-PDF1-Hash-Text.png)

*Figure 5: PDF1 hash record saved in `Hash.txt`.*

### Screenshot 6: `Hash2.txt` — PDF2

![PDF2 hash text](images/12-PDF2-Hash-Text.png)

*Figure 6: PDF2 hash record saved in `Hash2.txt`.*

### Screenshot 7: `Hash3.txt` — PDF3

![PDF3 hash text](images/13-PDF3-Hash-Text.png)

*Figure 7: PDF3 hash record saved in `Hash3.txt`.*

| Training document | Text file | Format visible | Evidence |
|---|---|---|---|
| PDF1 | `Hash.txt` | `$pdf$` record | Figure 5 |
| PDF2 | `Hash2.txt` | `$pdf$` record | Figure 6 |
| PDF3 | `Hash3.txt` | `$pdf$` record | Figure 7 |

The screenshots display the full strings, but this README does not duplicate them as typed text to avoid transcription mistakes. The existence of three hash files does **not** mean that all three hashes were cracked.

---

## ⚙️ Step 4: Verify Johnny and John the Ripper Configuration

I inspected Johnny's **Settings** page and confirmed that the application detected its configured John the Ripper executable.

### Screenshot 8: Johnny Configuration

![Johnny settings and detected John the Ripper engine](images/01-Johnny-Configuration.png)

*Figure 8: Johnny Settings with the detected John the Ripper executable.*

| Setting | Observed value |
|---|---|
| Engine | John the Ripper 1.9.0-jumbo-1 OMP |
| Platform | Cygwin 64-bit x86_64 AVX2 AC |
| Executable | `C:/Users/USER/Downloads/01. JTR_John CLI Win x64/john-1.9.0-jumbo-1-win64/run/john.exe` |
| Update interval | 15 seconds |
| Interface language | English |

**Learning point:** Johnny provides a graphical interface, while John the Ripper performs the underlying password auditing.

---

## 📂 Step 5: Review the PDF Hash Import Workflow

Johnny provides an **Open password file** menu with options to load a password file or another supported John-format input. I reviewed this interface as part of preparing and inspecting the audit workflow.

### Screenshot 9: Johnny File-Import Menu

![Johnny menu showing password-file import choices](images/03-Open-Hash-Menu.png)

*Figure 9: Johnny's file-import options.*

**Evidence limitation:** The screenshot shows the available import choices; it does not independently show which file was selected or the exact sequence of the cracking run.

---

## 🔑 Step 6: Review the Completed Password-Recovery Result

I examined the Johnny **Passwords** view, where the application displayed one recovered password for a PDF hash.

### Screenshot 10: Recovered PDF Password

![Johnny password recovery result](images/02-Recovered-Password.png)

*Figure 10: Johnny displays a recovered password and a completed audit status.*

| Result | Value shown |
|---|---|
| Recovered training password | `good-luck` |
| Format | PDF |
| Hash prefix | `$pdf$4*4*128*…` (truncated in Johnny) |
| Status | `100% (1/1: 1 cracked, 0 left)` |
| User field | `?` |

**Finding:** One PDF hash was successfully cracked in the documented exercise. The screenshot does **not** identify the attack mode, wordlist, elapsed cracking time, or a separate password for each of the three PDFs.

---

## 🏁 Step 7: Validate Opened PDFs and CTF Flags

Later screenshots show the three training PDFs opened to congratulatory pages. I recorded the visible challenge evidence without assuming that all three files were opened using the single password shown in Johnny.

### Screenshot 11: Opened PDF3 — Congratulations Page

![Opened PDF3 with highlighted flag](images/07-PDF3-Flag.png)

*Figure 11: PDF3 opened to a NetworkWalks congratulatory page with a highlighted flag.*

**Flag note:** The flag is visible in the screenshot, but the small characters should be verified against the original PDF before submitting a typed value.

### Screenshot 12: Opened PDF1 — First Captured Flag

![Opened PDF1 with captured flag](images/08-PDF1-Flag.png)

*Figure 12: PDF1 opened to a congratulatory page.*

**Visible flag:** `nw{cybersecurity_flag_captured_2608}`

### Screenshot 13: Opened PDF2 — Second Captured Flag

![Opened PDF2 with captured flag](images/09-PDF2-Flag.png)

*Figure 13: PDF2 opened to a congratulatory page.*

**Visible flag:** `nw{networkwalks_persistence_jtr_270521}`

**Interpretation:** These screenshots document access to the challenge pages, but they do not independently identify which password was used to open each file.

---

## 📊 Findings and Interpretation

| Observation | Security significance | Recommended follow-up |
|---|---|---|
| Three PDFs displayed password prompts | Files used password-based opening restrictions | Verify appropriate PDF encryption and password controls |
| Three `$pdf$` hash records were saved | Extracted records can support an authorized offline audit | Protect the records and retain clear file-to-hash mapping |
| Johnny detected John the Ripper | GUI and cracking engine were configured | Record tool versions for reproducibility |
| One password was recovered (`good-luck`) | The tested training password was recoverable | Use stronger, unique passwords for sensitive documents |
| All three PDFs were later opened | CTF challenge pages became accessible | Record file-specific credentials only when supported by evidence |
| Challenge flags were displayed | Screenshot evidence supports challenge validation | Preserve exact flags and source evidence |

**Scope limitation:** These results describe a controlled educational exercise, not a production vulnerability assessment.

---

## 💡 Recommendations

1. Use long, unique, randomly generated passwords or strong passphrases for sensitive PDF files.
2. Avoid common words and predictable password patterns.
3. Use a password manager for secure password generation and storage.
4. Select modern, supported PDF encryption options where available.
5. Share document passwords through a separate approved communication channel.
6. Avoid sending confidential documents or hashes to unapproved third-party services.
7. Protect recovered credentials and hash records; never publish real client secrets.
8. Record the exact hash source, attack settings, wordlist (if any), and elapsed time in future labs.
9. Preserve original evidence and distinguish observed facts from assumptions.
10. Perform password audits only with appropriate authorization.

---

## 📚 Learning Outcomes

Through this practical project, I improved my understanding of:

1. PDF password protection and encryption/hash records.
2. Extracting a PDF hash for a controlled security test.
3. Saving and identifying three distinct `$pdf$` records.
4. Differentiating a hash representation from a recovered password.
5. Configuring Johnny with the John the Ripper engine.
6. Recognizing hash-import options in Johnny.
7. Interpreting the completed cracking status and recovered credential.
8. Comparing locked and opened PDF states.
9. Recording CTF evidence and visible challenge flags.
10. Explaining the risks of weak passwords and third-party file uploads.
11. Reporting accurately when evidence does not establish every detail.

---

## 📎 Evidence and Report Files

| File | Description |
|---|---|
| [04-PDF1-Locked.png](images/04-PDF1-Locked.png) | PDF1 password prompt (Figure 1) |
| [05-PDF2-Locked.png](images/05-PDF2-Locked.png) | PDF2 password prompt (Figure 2) |
| [06-PDF3-Locked.png](images/06-PDF3-Locked.png) | PDF3 password prompt (Figure 3) |
| [10-PDF-Hash-Extractor.png](images/10-PDF-Hash-Extractor.png) | PDF3 hash extraction (Figure 4) |
| [11-PDF1-Hash-Text.png](images/11-PDF1-Hash-Text.png) | `Hash.txt` (Figure 5) |
| [12-PDF2-Hash-Text.png](images/12-PDF2-Hash-Text.png) | `Hash2.txt` (Figure 6) |
| [13-PDF3-Hash-Text.png](images/13-PDF3-Hash-Text.png) | `Hash3.txt` (Figure 7) |
| [01-Johnny-Configuration.png](images/01-Johnny-Configuration.png) | Johnny settings (Figure 8) |
| [03-Open-Hash-Menu.png](images/03-Open-Hash-Menu.png) | Johnny import menu (Figure 9) |
| [02-Recovered-Password.png](images/02-Recovered-Password.png) | Completed recovery (Figure 10) |
| [07-PDF3-Flag.png](images/07-PDF3-Flag.png) | PDF3 challenge page (Figure 11) |
| [08-PDF1-Flag.png](images/08-PDF1-Flag.png) | PDF1 challenge page (Figure 12) |
| [09-PDF2-Flag.png](images/09-PDF2-Flag.png) | PDF2 challenge page (Figure 13) |

**GitHub setup:** Upload `README.md` and the entire `images` folder to the same repository root. Keep filenames and folder structure unchanged so every image renders correctly. Badges use externally hosted Shields.io images.

---

## 🛡️ Ethical Security Statement

I completed this activity as part of an authorized educational cybersecurity exercise using NetworkWalks training files. Password recovery must be limited to documents and systems for which permission has been granted. The recovered password belongs to this training exercise; real client credentials, confidential files, and private hashes must not be published.

---

## 👨‍💻 About the Author

**Lamidi Olatunji Micheal Eleshin**

Cybersecurity & Penetration Testing Intern | Aspiring Cybersecurity Analyst | IT Auditor | IT Support Engineer | GRC & Risk Management

**Specialization Areas:** Cybersecurity | Network Security | IT Auditing | Governance, Risk & Compliance | Penetration Testing | SOC Operations

**Internship:** NetworkWalks Cybersecurity & Penetration Testing  
**Batch:** B084 | Week 3  
**Project Focus:** PDF Hash Extraction, Password Auditing, Johnny, John the Ripper & CTF Validation  
**LinkedIn:** [Lamidi Olatunji Eleshin](https://www.linkedin.com/in/lamidi-olatunji-eleshin-4834252ab/)

---

<div align="center">

**“Cybersecurity begins with vigilance. Failure to prevent a threat today may become tomorrow's data disaster.”**

*— Lamidi Olatunji Micheal Eleshin*

</div>

