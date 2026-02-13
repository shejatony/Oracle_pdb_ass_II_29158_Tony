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
<img width="741" height="436" alt="Creating pdb" src="https://github.com/user-attachments/assets/33586c68-bd17-40db-b573-5d6162744330" />
<img width="875" height="621" alt="PDB open" src="https://github.com/user-attachments/assets/30235688-04fd-498d-bbe7-1ae84baa40a1" />
<img width="702" height="521" alt="USER_EXISTS AND TEMP CREATION" src="https://github.com/user-attachments/assets/edeb649c-2f35-444a-927b-7b3aae169da0" />


---

## Task 2: Create and Delete Temporary PDB

*Temp PDB:* [RO_pdb_29152]

*Commands:*
sql
CREATE PLUGGABLE DATABASE [RO_pdb_29152]
ADMIN USER temp_admin IDENTIFIED BY [password]
FILE_NAME_CONVERT = ('pdbseed', '[RO_pdb_29152]');

ALTER PLUGGABLE DATABASE [RO_pdb_29152] CLOSE IMMEDIATE;
DROP PLUGGABLE DATABASE [RO_pdb_29152] INCLUDING DATAFILES;


*Evidence:* Screenshots show creation, both PDBs existing, deletion, and verification.
<img width="702" height="521" alt="USER_EXISTS AND TEMP CREATION" src="https://github.com/user-attachments/assets/4e2d1041-d7fa-4bd9-90d5-6aa884f4d79d" />
<img width="840" height="696" alt="BOTH PDBS" src="https://github.com/user-attachments/assets/c4c4a204-cd37-4a7b-9469-073f636c0b0a" />
<img width="911" height="661" alt="DROP PDB" src="https://github.com/user-attachments/assets/067a919c-e223-4e04-9adf-1e5c07b7fbae" />
<img width="781" height="427" alt="VERIFY DELETION" src="https://github.com/user-attachments/assets/906c7753-e6ae-4530-8e38-111384472719" />


---

## Task 3: Oracle Enterprise Manager

*Access:* https://localhost:5500/em (SYS as SYSDBA)

*Evidence:* OEM dashboard screenshot showing PDB status and username.
<img width="1344" height="628" alt="OEM_DASHBOARD" src="https://github.com/user-attachments/assets/2e2755c9-05d1-4bf7-94cc-df09ac49f896" />


---

## Challenges and Solutions

*Issue:* "Insufficient privileges" error when opening PDB  
*Solution:* Reconnected as SYSDBA using sqlplus / as sysdba  
*Learning:* Always verify SYSDBA connection for administrative tasks

---


---

## Academic Integrity Statement

I, *Rutayisire Gihozo Rolando* (ID: *29152*), declare this work is completed individually. All commands, screenshots, and documentation are my own. No AI tools or collaboration were used.

*Signed:* Rutayisire Gihozo Rolando
*Date:* 13 february 2026

---
