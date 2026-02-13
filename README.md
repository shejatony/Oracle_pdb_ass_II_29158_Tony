# Oracle PDB Management Assignment

## Student Information
- *Name:* SHEJA HUGUES TONY
- *Student ID:* 29158
- *Course:* INSY 8311 - Database Development with PL/SQL
- *Date:* February 13, 2026

---

## Overview

Hands-on Oracle Multitenant Architecture assignment demonstrating PDB creation, deletion, user management, and OEM dashboard access.

---

## Oracle Environment
- *Database:* Oracle 21c Express Edition (21.3.0.0.0)
- *OS:* [Windows 11]
- *Tools:* SQL*Plus, Oracle Enterprise Manager

---

## Task 1: Create Main PDB

*PDB Created:* [To_pdb_29158]  
*Username:* [TONY_PLSQLAUCA_29158]

*Commands:*
sql
CREATE PLUGGABLE DATABASE [pdb_name]
ADMIN USER [TONY_PLSQLAUCA_29158] IDENTIFIED BY [12345]
FILE_NAME_CONVERT = ('pdbseed', '[pdb_To_pdb_29158]');

ALTER PLUGGABLE DATABASE [pdb_To_pdb_29158] OPEN;
GRANT CONNECT, RESOURCE, DBA TO [TONY_PLSQLAUCA_29158];


*Evidence:* Screenshots show PDB creation, open state (READ WRITE), and user verification.
<img width="944" height="232" alt="pdb creation" src="https://github.com/user-attachments/assets/0319e4a2-e04e-4116-978c-fd894f34339b" />

<img width="922" height="645" alt="pdb open" src="https://github.com/user-attachments/assets/6802b5a8-9022-4cbc-a259-20f147b5805a" />


<img width="935" height="274" alt="user exists" src="https://github.com/user-attachments/assets/804752e9-6c2c-4ec5-9ade-4602ba632833" />


---

## Task 2: Create and Delete Temporary PDB

*Temp PDB:* [To_pdb_29158]

*Commands:*
sql
CREATE PLUGGABLE DATABASE [To_pdb_29158]
ADMIN USER temp_admin IDENTIFIED BY [12345]
FILE_NAME_CONVERT = ('pdbseed', '[To_pdb_29158]');

ALTER PLUGGABLE DATABASE [To_pdb_29158] CLOSE IMMEDIATE;
DROP PLUGGABLE DATABASE [To_pdb_29158] INCLUDING DATAFILES;


*Evidence:* Screenshots show creation, both PDBs existing, deletion, and verification.
<img width="940" height="482" alt="temp creation" src="https://github.com/user-attachments/assets/55c2be5a-aa1c-42d1-ba96-8bbaefb8df29" />

<img width="945" height="787" alt="both pdbs" src="https://github.com/user-attachments/assets/aa80b278-d705-4c6a-bf8f-717b7a1f1bf7" />


<img width="933" height="333" alt="drop pdb" src="https://github.com/user-attachments/assets/37bb2dab-d2d2-4016-9878-64abeb9fc550" />


<img width="951" height="531" alt="verify deletion" src="https://github.com/user-attachments/assets/e28ab762-391e-45fe-a078-3b2a4ea2576e" />

---

## Task 3: Oracle Enterprise Manager

*Access:* https://localhost:5500/em (SYS as SYSDBA)

*Evidence:* OEM dashboard screenshot showing PDB status and username.

<img width="1892" height="851" alt="oem dashboard" src="https://github.com/user-attachments/assets/c6fc2f3b-4825-4c1a-8346-3ee363d0e66c" />

---




---

## Academic Integrity Statement

I, *SHEJA HUGUES TONY* (ID: *29158*), declare this work is completed individually. All commands, screenshots, and documentation are my own. No AI tools or collaboration were used.

*Signed:* SHEJA HUGUES TONY
*Date:* 13 february 2026

---
