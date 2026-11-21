<div align="center">🔐 Cybersecurity Internship – B084
Week 3: PDF Password Security Assessment Using Johnny & John the Ripper
NETWORKWALKS | CYBERSECURITY & PENETRATION TESTING INTERNSHIP

Hands-On Password Hash Auditing, PDF Password Recovery & Capture-the-Flag Validation
    
</div>📌 Project Overview
As part of my NetworkWalks Cybersecurity & Penetration Testing Internship (Batch B084), I practiced password auditing and recovery in a controlled training environment. The exercise used Johnny, the graphical interface for John the Ripper, to examine a PDF password hash and verify access to password-protected training documents.

The screenshots show a completed password-recovery session, three password prompts, and three subsequently opened PDFs containing congratulatory messages and training flags. This report documents the evidence and explains the security lessons. Only one recovered password is visible in the screenshots; passwords for the other PDFs are not independently shown.
🎯 Project Objectives
- Understand the difference between password-protected PDF files and password hashes extracted for offline auditing.
- Configure Johnny to use the John the Ripper executable.
- Review an authorized PDF hash in Johnny and observe the completed recovery result.
- Validate access to the three training PDF documents.
- Record challenge flags and preserve screenshot evidence.
- Explain the risks of weak passwords and the value of strong passphrases.
🧰 Tools and Environment
Component	Evidence / configuration
Host	Windows desktop, as shown in screenshots
Graphical tool	Johnny (John the Ripper GUI)
Password-auditing engine	John the Ripper 1.9.0-jumbo-1 OMP, Cygwin 64-bit x86_64 AVX2 AC
Engine executable	C:/Users/USER/Downloads/01. JTR_John CLI Win x64/john-1.9.0-jumbo-1-win64/run/john.exe
Hash format	PDF; displayed hash begins $pdf$4*4*128*… (truncated in GUI)
Johnny refresh interval	15 seconds
Test documents	My Locked PDF1.pdf, My Locked PDF2.pdf, My Locked PDF3.pdf
Scope	NetworkWalks training PDFs only


🪜 Lab Procedure and Screenshot Evidence
Step 1 — Configure the John the Ripper engine
I opened Johnny's Settings panel and confirmed that it detected the configured john.exe executable. The interface displayed the installed Jumbo build and a 15-second update interval.

Step 2 — Review the PDF hash and recovered password
In the Passwords panel, Johnny displayed a single PDF-format hash and the recovered password good-luck. The status bar showed 100% (1/1: 1 cracked, 0 left). This confirms a successful recovery for the single displayed hash, not necessarily all three documents.

Step 3 — Identify the supported input types
The Open password file menu offered a standard PASSWD-format input and an alternative *2john input option. The latter is intended for compatible hashes produced by extraction utilities. The screenshot does not document the original extraction command or attack mode, so those steps are not claimed as observed.

Step 4 — Observe the password protection on the training PDFs
Each of the three files initially displayed a password-entry dialog, demonstrating that the documents required a password before their contents could be viewed.

My Locked PDF1.pdf

My Locked PDF2.pdf

My Locked PDF3.pdf

Step 5 — Validate access and capture the flags
Later screenshots show all three training PDFs opened successfully, each with one page and a congratulatory message. The visible flags are recorded below; the third flag is reproduced from the screenshot and should be visually double-checked before submission because the text is small.

PDF3 — Opened challenge document

PDF1 — Opened challenge document

PDF2 — Opened challenge document

🏁 Results and Captured Flags
Evidence	Result
Johnny PDF hash	1 of 1 displayed hashes cracked (100%)
Recovered password shown	good-luck
My Locked PDF1.pdf	Opened; flag shown: nw{cybersecurity_flag_captured_2608}
My Locked PDF2.pdf	Opened; flag shown: nw{networkwalks_persistence_jtr_270521}
My Locked PDF3.pdf	Opened; flag shown: nw{networkwalks_flag_260821_1} (verify exact characters against original)


Evidence limitation: The screenshots show the files unlocked, but they do not show each password being entered. Do not infer that good-luck is the password for all three files.

🐞 Challenges and Troubleshooting
Engine configuration: Johnny depends on an accessible John the Ripper executable. Checking the detected engine in Settings is a useful first troubleshooting step if an audit does not start.

Input format: An encrypted PDF itself is not the same as a Johnny password-hash input. A compatible PDF hash representation must be prepared using an appropriate extraction utility in an authorized lab. The screenshots show the menu and loaded hash, not the extraction process.

Interpreting the results: A 100% status means the single loaded hash was recovered. It does not mean every PDF on the computer was tested.

Evidence quality: Keep filenames, timestamps, and clear screenshots together. Record the exact attack mode and wordlist in future exercises so another analyst can reproduce the assessment.
🔎 Security Findings and Recommendations
1. Guessable passwords are vulnerable to offline testing. The recovered value good-luck is short and based on common words; it is not a strong choice for protecting sensitive files.
2. Encryption strength and password strength are different controls. Strong PDF encryption can still be undermined by a predictable password.
3. Use long, unique passphrases. Prefer a password-manager-generated secret or a long, unpredictable passphrase for sensitive documents.
4. Limit exposure of protected files. Avoid distributing sensitive encrypted files and their passwords through the same channel.
5. Maintain authorization and evidence. Password audits should be scoped to systems and documents that the tester owns or is explicitly permitted to assess.
💡 What I Learned
This exercise strengthened my understanding of how password auditing tools work, how recovered credentials are displayed, and why offline password attacks can succeed against weak secrets. I also practiced validating access to protected documents, collecting screenshot evidence, and distinguishing directly observed results from assumptions.

I learned that the quality of a cybersecurity report depends not just on whether a challenge was completed, but also on whether the testing method, scope, results, and limitations are accurately documented.
🔐 Ethical and Responsible Use
All work described here relates to authorized NetworkWalks training documents. I will use password-recovery techniques only on materials I own or have explicit permission to test, and I will avoid publishing real credentials or sensitive data.
🔗 Tools and Resources
- John the Ripper project
- Johnny GUI project
- NetworkWalks
👤 Author
Lamidi Olatunji Micheal Eleshin
Cybersecurity Intern | NetworkWalks – Batch B084
Areas of Interest: Cybersecurity | Penetration Testing | Password Auditing | Network Security | IT Risk Management
GitHub: github.com/leleshin
📌 Project Information
Field	Value
Program	NetworkWalks Cybersecurity & Penetration Testing Internship
Batch	B084
Week	03 (report label)
Project	PDF Password Security Assessment Using Johnny & John the Ripper
Evidence	Nine screenshots (267–269, 271–276)
Outcome	One displayed PDF hash recovered; three training PDFs opened; three flags visible# Password-Cracking-Hashing
