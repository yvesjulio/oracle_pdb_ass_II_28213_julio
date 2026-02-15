\ Oracle Pluggable Database (PDB) Management – Assignment II

\\Course:\\ Database Development with PL/SQL (INSY 8311\)    
\\Student Name:\\ISHIMWE Yves Julio    
\\Student ID:\\ 28213    
\\*Repository Visibility:\\Public  

\---

\#\# 1\. Overview  
This repository documents the practical implementation of Oracle Multitenant Architecture concepts. The assignment demonstrates the creation, configuration, monitoring, and deletion of Pluggable Databases (PDBs), as well as system observation using Oracle Enterprise Manager (OEM) Express.

\---

\#\# 2\. Oracle Environment  
\- \*\*Database Version:\*\* Oracle Database 21c Enterprise Edition Release 21.0.0.0.0 – Production    
\- \*\*Platform:\*\* Docker (oracle/database:21.3.0-ee)    
\- \*\*Tools Used:\*\* SQL\*Plus, Oracle Enterprise Manager (OEM) Express  

\---

\#\# 3\. Task Execution Details

\#\#\# Task 1: Permanent PDB Creation  
\\Goal:\\ Create a persistent PDB for future coursework.

\- \*\*PDB Name:\*\* \`ju\_pdb\_28213\`  
\- \*\*Admin User:\*\* \`julio\_plsqlauca\_28213\`

\*\*Actions Performed:\*\*  
1\. Created the PDB from \`PDB$SEED\`.  
2\. Opened the PDB in \`READ WRITE\` mode.  
3\. Saved the PDB state to ensure persistence across database restarts.  
4\. Created a local administrative user and granted appropriate privileges (\`CONNECT\`, \`RESOURCE\`).

\---

\#\#\# Task 2: Temporary PDB Lifecycle  
\*\*Goal:\*\* Demonstrate complete creation and removal of a temporary PDB.

\- \*\*Temporary PDB Name:\*\* \`ju\_to\_delete\_pdb\_28213\`

\*\*Actions Performed:\*\*  
1\. Created the temporary PDB using the required naming convention.  
2\. Verified its existence using \`SHOW PDBS\`.  
3\. Dropped the PDB using the \`INCLUDING DATAFILES\` clause to ensure full cleanup.  
4\. Confirmed successful deletion via a final \`SHOW PDBS\` command.

\---

\#\#\# Task 3: Oracle Enterprise Manager (OEM)  
\- \*\*Status:\*\* Configured and accessible via HTTPS (port 5500).  
\- \*\*Observation:\*\* The OEM Express dashboard displays the health and status of the Container Database (CDB) and all active Pluggable Databases.

\---

\#\# 4\. Challenges Faced & Solutions  
\- \*\*Issue:\*\* Encountered Oracle multitenant-related errors ( \`ORA-65005\`, \`ORA-65096\`) during PDB creation.  
\- \*\*Root Cause:\*\* Typographical errors in the \`FILE\_NAME\_CONVERT\` parameter and incorrect container context.  
\- \*\*Solution:\*\* Corrected the file path pattern to match the \`/opt/oracle/oradata/\` directory and ensured operations were executed in the appropriate container (\`CDB$ROOT\`).

\---

\#\# 5\. Academic Integrity Statement  
I, \*\*ISHIMWE Yves Julio\*\*, confirm that this assignment is my own original work. All commands were executed manually in my personal Oracle environment. No screenshots, scripts, or configurations were copied from other students or external sources.

\---

\#\# 6\. Evidence (Screenshots)  
All supporting evidence is available in the \`/screenshots\` directory:  
1\. \`Task1\_PDB\_Creation.png\`  
2\. \`Task1\_User\_Verification.png\`  
3\. \`Task2\_PDB\_Drop.png\`  
4\. \`Task3\_OEM\_Dashboard.png\`

