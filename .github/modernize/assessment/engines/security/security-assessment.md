# Security Assessment Report

**Generated:** 2026-06-22T07:03:54.0000000Z

## Summary

| Metric | Count |
|--------|-------|
| Total Findings | 21 |
| CVE Vulnerabilities | 7 |
| CWE Vulnerabilities | 14 |
| Total Rules Assessed | 59 |
| Rules Passed | 45 |

### By Severity

| Severity | Count |
|----------|-------|
| mandatory | 8 |
| optional | 3 |
| potential | 10 |

### By Category

| Category | Count |
|----------|-------|
| CVE | 7 |
| Code Quality | 4 |
| Concurrency & Synchronization | 3 |
| Credentials & Secrets | 1 |
| File & Path Security | 3 |
| Injection Attacks | 2 |
| Memory Safety | 1 |

## CVE Findings (Dependency Vulnerabilities)

### CVE-2023-6378: logback serialization vulnerability
- **Severity:** mandatory
- **Story Points:** 1
- **Files:** pom.xml:86

[CVE-2023-6378](https://github.com/advisories/GHSA-vmq6-5m68-f53m): logback serialization vulnerability

Severity: HIGH

Affected dependencies:
  - ch.qos.logback:logback-classic:1.2.3 (declared at pom.xml:86)
  - ch.qos.logback:logback-classic:1.2.3 (declared at pom.xml:86)
  - ch.qos.logback:logback-classic:1.2.3 (declared at pom.xml:86)

Recommended fix:
  - Upgrade ch.qos.logback:logback-classic to 1.4.12 or later
  - Upgrade ch.qos.logback:logback-classic to 1.3.12 or later
  - Upgrade ch.qos.logback:logback-classic to 1.2.13 or later

### CVE-2023-22102: MySQL Connectors takeover vulnerability
- **Severity:** mandatory
- **Story Points:** 1
- **Files:** pom.xml:48

[CVE-2023-22102](https://github.com/advisories/GHSA-m6vm-37g8-gqvh): MySQL Connectors takeover vulnerability

Severity: HIGH

Affected dependencies:
  - mysql:mysql-connector-java:5.1.47 (declared at pom.xml:48)


### CVE-2023-24162: Dromara Hutool Deserialization of Untrusted Data vulnerability
- **Severity:** mandatory
- **Story Points:** 1
- **Files:** pom.xml:138

[CVE-2023-24162](https://github.com/advisories/GHSA-77h8-5j3h-jcjf): Dromara Hutool Deserialization of Untrusted Data vulnerability

Severity: CRITICAL

Affected dependencies:
  - cn.hutool:hutool-all:5.6.4 (declared at pom.xml:138)


### CVE-2023-24163: Dromara hutool vulnerable to SQL Injection
- **Severity:** mandatory
- **Story Points:** 1
- **Files:** pom.xml:138

[CVE-2023-24163](https://github.com/advisories/GHSA-6c25-cxcc-pmc4): Dromara hutool vulnerable to SQL Injection

Severity: CRITICAL

Affected dependencies:
  - cn.hutool:hutool-all:5.6.4 (declared at pom.xml:138)

Recommended fix:
  - Upgrade cn.hutool:hutool-all to 5.8.21 or later

### CVE-2022-25845: Unsafe deserialization in com.alibaba:fastjson
- **Severity:** mandatory
- **Story Points:** 1
- **Files:** pom.xml:169

[CVE-2022-25845](https://github.com/advisories/GHSA-pv7h-hx5h-mgfj): Unsafe deserialization in com.alibaba:fastjson

Severity: HIGH

Affected dependencies:
  - com.alibaba:fastjson:1.2.74 (declared at pom.xml:169)

Recommended fix:
  - Upgrade com.alibaba:fastjson to 1.2.83 or later

### CVE-2021-0341: Square OkHttp can accept the wrong certificate
- **Severity:** mandatory
- **Story Points:** 1
- **Files:** pom.xml:310

[CVE-2021-0341](https://github.com/advisories/GHSA-3cqm-mf7h-prrj): Square OkHttp can accept the wrong certificate

Severity: HIGH

Affected dependencies:
  - com.squareup.okhttp3:okhttp:4.9.1 (declared at pom.xml:310)

Recommended fix:
  - Upgrade com.squareup.okhttp3:okhttp to 4.9.2 or later

### CVE-2018-3258: Improper Privilege Management in MySQL Connectors Java
- **Severity:** mandatory
- **Story Points:** 1
- **Files:** pom.xml:48

[CVE-2018-3258](https://github.com/advisories/GHSA-4vrv-ch96-6h42): Improper Privilege Management in MySQL Connectors Java

Severity: HIGH

Affected dependencies:
  - mysql:mysql-connector-java:5.1.47 (declared at pom.xml:48)

Recommended fix:
  - Upgrade mysql:mysql-connector-java to 8.0.13 or later

## CWE Findings (Code-Level Vulnerabilities)

### CWE-681: Incorrect Conversion between Numeric Types
- **Category:** Code Quality
- **Severity:** potential
- **Story Points:** 3
- **Files:** src/main/java/com/fangxuele/tool/push/ui/dialog/importway/ImportByWxMp.java

In ImportByWxMp.java at lines 262 and 345, wxMpUserList.getTotal() returns a long value that is cast to int via (int) without bounds checking. If the total number of WeChat subscribers exceeds Integer.MAX_VALUE (2,147,483,647), the cast truncates the value, causing the progress bar maximum to be set incorrectly and potentially causing UI logic errors.

### CWE-772: Missing Release of Resource after Effective Lifetime
- **Category:** Code Quality
- **Severity:** potential
- **Story Points:** 3
- **Files:** src/main/java/com/fangxuele/tool/push/util/HikariUtil.java

In HikariUtil.java, the executeQuery() method (lines 61-63) creates a database Connection and PreparedStatement but returns the ResultSet to the caller without closing them. The caller receives only the ResultSet and has no way to close the underlying Connection and PreparedStatement, leading to connection pool resource exhaustion over time.

### CWE-775: Missing Release of File Descriptor or Handle after Effective Lifetime
- **Category:** Code Quality
- **Severity:** potential
- **Story Points:** 3
- **Files:** src/main/java/com/fangxuele/tool/push/ui/dialog/TaskHisDetailDialog.java

In TaskHisDetailDialog.java (lines 148, 216, 284), DataInputStream is created wrapping a FileInputStream, then passed to CSVReader via InputStreamReader. Only the outer CSVReader (reader) is closed in the finally block. If the CSVReader or InputStreamReader constructor fails, the DataInputStream and FileInputStream are never closed, leaving file descriptors open.

### CWE-1057: Data Access Operations Outside of Expected Data Manager Component
- **Category:** Code Quality
- **Severity:** potential
- **Story Points:** 5
- **Files:** src/main/java/com/fangxuele/tool/push/ui/form/TaskForm.java

In TaskForm.java (lines 77-82), UI form classes directly instantiate and use MyBatis mapper objects (TTaskMapper, TPeopleMapper, TMsgMapper, etc.) obtained via MybatisUtil.getSqlSession().getMapper() to perform database operations. Data access is scattered across UI layer classes (TaskForm, PeopleEditForm, etc.) instead of being centralized in a dedicated data manager or service layer, violating separation of concerns.

### CWE-543: Use of Singleton Pattern Without Synchronization in a Multithreaded Context
- **Category:** Concurrency & Synchronization
- **Severity:** potential
- **Story Points:** 5
- **Files:** src/main/java/com/fangxuele/tool/push/ui/form/TaskForm.java

In TaskForm.java (lines 88-92), the getInstance() method checks 'if (taskForm == null)' and creates a new instance without any synchronization. The same unsynchronized singleton pattern exists in PeopleEditForm.java, MessageEditForm.java, and several other form classes. TaskRunThread.java calls TaskForm.getInstance() from a background thread (lines 284, 337, 395), creating a race condition where the singleton instance could be created multiple times or accessed in an inconsistent state.

### CWE-567: Unsynchronized Access to Shared Data in a Multithreaded Context
- **Category:** Concurrency & Synchronization
- **Severity:** potential
- **Story Points:** 5
- **Files:** src/main/java/com/fangxuele/tool/push/ui/form/MessageManageForm.java

In MessageManageForm.java at line 50, the public static boolean 'accountSwitchComboBoxListenIgnore' is a shared mutable static field that is read and written from both the Swing EDT and background task threads without synchronization. Additionally, the static 'accountMap' field (line 44) is a Map shared across threads without any synchronization guard, potentially leading to ConcurrentModificationException or stale reads.

### CWE-820: Missing Synchronization
- **Category:** Concurrency & Synchronization
- **Severity:** potential
- **Story Points:** 8
- **Files:** src/main/java/com/fangxuele/tool/push/ui/form/TaskForm.java

In TaskForm.java, the static singleton field 'taskForm' and mapper fields (taskMapper, taskHisMapper, peopleMapper, msgMapper at lines 77-82) are shared static resources accessed from both the Swing EDT and background TaskRunThread instances without any synchronization. The MyBatis SqlSession obtained via MybatisUtil.getSqlSession() is a single shared non-thread-safe session used concurrently from multiple threads through these static mapper references.

### CWE-778: Insufficient Logging
- **Category:** Credentials & Secrets
- **Severity:** potential
- **Story Points:** 3
- **Files:** src/main/java/com/fangxuele/tool/push/ui/dialog/importway/ImportByFile.java

The application has 44 occurrences of e.printStackTrace() across the codebase (e.g., ImportByFile.java lines 293, 307) instead of using the structured logger (log.error()). Security-critical failures such as file access errors, database connection failures, and message send failures are silently swallowed with only a console stack trace rather than being recorded in the application's security log. This makes post-incident analysis and security auditing difficult.

### CWE-22: Improper Limitation of a Pathname to a Restricted Directory ('Path Traversal')
- **Category:** File & Path Security
- **Severity:** optional
- **Story Points:** 8
- **Files:** src/main/java/com/fangxuele/tool/push/ui/dialog/importway/ImportByFile.java

In ImportByFile.java, the method importFromFile (line 127) accepts a filePath parameter obtained directly from user input (memberFilePathField.getText() at line 110) and passes it to new File(filePath) at line 136 without any canonicalization or path restriction check. A user can type an arbitrary path (e.g., ../../../etc/passwd) and the application will attempt to open it, bypassing any intended directory restriction.

### CWE-23: Relative Path Traversal
- **Category:** File & Path Security
- **Severity:** optional
- **Story Points:** 5
- **Files:** src/main/java/com/fangxuele/tool/push/ui/dialog/importway/ImportByFile.java

In ImportByFile.java at line 110-136, the filePath is taken from memberFilePathField.getText() and passed to new File(filePath) without neutralizing relative sequences such as '../'. An attacker could supply a path like '../../sensitive/file.csv' to read files outside any intended directory.

### CWE-36: Absolute Path Traversal
- **Category:** File & Path Security
- **Severity:** optional
- **Story Points:** 5
- **Files:** src/main/java/com/fangxuele/tool/push/ui/dialog/importway/ImportByFile.java

In ImportByFile.java at line 110-136, the user-supplied filePath (from memberFilePathField.getText()) is used directly in new File(filePath) without restricting or validating absolute paths. A user can type an absolute path such as '/etc/passwd' or 'C:\Windows\System32\config\SAM' to access sensitive files outside any intended directory.

### CWE-99: Improper Control of Resource Identifiers ('Resource Injection')
- **Category:** Injection Attacks
- **Severity:** potential
- **Story Points:** 3
- **Files:** src/main/java/com/fangxuele/tool/push/logic/msgsender/HttpMsgSender.java

In HttpMsgSender.java (lines 87-229), the URL for HTTP requests is taken directly from user-configured message data (httpMsg.getUrl()) without restriction or validation. The URL is passed directly to HttpRequest.get/post/put/delete/patch/head/options and OkHttp's urlBuilder, allowing requests to arbitrary internal or external resources including internal services (SSRF).

### CWE-502: Deserialization of Untrusted Data
- **Category:** Injection Attacks
- **Severity:** mandatory
- **Story Points:** 13
- **Files:** src/main/java/com/fangxuele/tool/push/util/UpgradeUtil.java

In UpgradeUtil.java at lines 36 and 45, remote JSON content is fetched via HTTP from a GitHub URL (UiConsts.CHECK_VERSION_URL) and immediately deserialized using fastjson 1.2.74 (JSON.parseObject). Fastjson 1.2.74 is affected by CVE-2022-25845 (unsafe deserialization), meaning that a compromised or man-in-the-middle server response containing a malicious '@type' field could trigger arbitrary code execution during deserialization.

### CWE-672: Operation on a Resource after Expiration or Release
- **Category:** Memory Safety
- **Severity:** potential
- **Story Points:** 5
- **Files:** src/main/java/com/fangxuele/tool/push/util/HikariUtil.java

In HikariUtil.java, the executeQuery() method (lines 61-63) opens a database connection and PreparedStatement but returns the ResultSet without closing the PreparedStatement or Connection. Callers that use the ResultSet cannot properly close the underlying Connection, causing connection pool resources to be held open after the ResultSet is consumed. This constitutes operating on a resource (connection pool slot) after the intended use scope has ended.
