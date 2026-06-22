# WePush

## Summary

| Metric | Value |
|--------|-------|
| Total Issues | 30 |
| Mandatory Blockers | 12 |
| Potential Issues | 11 |

## Component Information

| Property | Value |
|----------|-------|
| Language | Java |
| Frameworks | N/A |
| Build tools | Maven |
| JDK version | 21 |

## Cloud Readiness Issues

| Issue Name | Criticality | Story Points | Occurrences |
|------------|-------------|--------------|-------------|
| Use of unsecured network protocols or URI libraries | Mandatory | 3 | [7](#Use_of_unsecured_network_protocols_or_URI_libraries) |
| CRA: Certificate validation bypass - TrustAllCerts | Mandatory | 8 | [2](#CRA_Certificate_validation_bypass_-_TrustAllCerts) |
| Avoid File System Logging in Configuration | Mandatory | 1 | [2](#Avoid_File_System_Logging_in_Configuration) |
| No Dockerfile found | Mandatory | 3 | 1 |
| MySQL database found | Potential | 5 | [2](#MySQL_database_found) |
| Avoid using hardcoded URLs (HTTP protocol) in source code | Optional | 3 | [31](#Avoid_using_hardcoded_URLs_HTTP_protocol_in_source_code) |
| Quartz Scheduler usage detected | Optional | 13 | [1](#Quartz_Scheduler_usage_detected) |
| SQLite usage detected | Optional | 5 | [1](#SQLite_usage_detected) |

### Issue Details

<details id="Use_of_unsecured_network_protocols_or_URI_libraries">
<summary><b>Use of unsecured network protocols or URI libraries</b> — affected files</summary>

- `src/main/java/com/fangxuele/tool/push/ui/component/TopMenuBar.java (line 226)`
- `src/main/java/com/fangxuele/tool/push/ui/dialog/CommonTipsDialog.java (line 71)`
- `src/main/java/com/fangxuele/tool/push/ui/dialog/NewTaskDialog.java (line 215)`
- `src/main/java/com/fangxuele/tool/push/ui/dialog/NewTaskDialog.java (line 979)`
- `src/main/java/com/fangxuele/tool/push/ui/form/account/WxMpAccountForm.java (line 295)`
- `src/main/java/com/fangxuele/tool/push/ui/form/msg/MailMsgForm.java (line 72)`
- `src/main/java/com/fangxuele/tool/push/ui/form/msg/MailMsgForm.java (line 242)`

</details>

<details id="CRA_Certificate_validation_bypass_-_TrustAllCerts">
<summary><b>CRA: Certificate validation bypass - TrustAllCerts</b> — affected files</summary>

- `src/main/java/com/fangxuele/tool/push/logic/msgsender/HwYunMsgSender.java (line 21)`
- `src/main/java/com/fangxuele/tool/push/logic/msgsender/HwYunMsgSender.java (line 170)`

</details>

<details id="Avoid_File_System_Logging_in_Configuration">
<summary><b>Avoid File System Logging in Configuration</b> — affected files</summary>

- `src/main/resources/logback.xml (line 9)`
- `src/main/resources/logback.xml (line 20)`

</details>

<details id="MySQL_database_found">
<summary><b>MySQL database found</b> — affected files</summary>

- `pom.xml (line 156)`

</details>

<details id="Avoid_using_hardcoded_URLs_HTTP_protocol_in_source_code">
<summary><b>Avoid using hardcoded URLs (HTTP protocol) in source code</b> — affected files</summary>

- `src/main/java/com/fangxuele/tool/push/ui/form/account/WxMpAccountForm.java (line 295)`
- `src/main/java/com/fangxuele/tool/push/logic/msgsender/DingMsgSender.java (line 232)`
- `src/main/java/com/fangxuele/tool/push/logic/msgsender/DingMsgSender.java (line 258)`
- `src/main/java/com/fangxuele/tool/push/ui/UiConsts.java (line 93)`
- `src/main/java/com/fangxuele/tool/push/ui/UiConsts.java (line 98)`
- `src/main/java/com/fangxuele/tool/push/ui/UiConsts.java (line 103)`
- `src/main/java/com/fangxuele/tool/push/ui/UiConsts.java (line 108)`
- `src/main/java/com/fangxuele/tool/push/ui/UiConsts.java (line 110)`
- `src/main/java/com/fangxuele/tool/push/ui/component/TopMenuBar.java (line 226)`
- `src/main/java/com/fangxuele/tool/push/ui/component/TopMenuBar.java (line 266)`
- `src/main/java/com/fangxuele/tool/push/ui/dialog/AboutDialog.java (line 98)`
- `src/main/java/com/fangxuele/tool/push/ui/dialog/AboutDialog.java (line 134)`
- `src/main/java/com/fangxuele/tool/push/ui/dialog/AboutDialog.java (line 214)`
- `src/main/java/com/fangxuele/tool/push/ui/dialog/NewTaskDialog.java (line 160)`
- `src/main/java/com/fangxuele/tool/push/ui/dialog/NewTaskDialog.java (line 215)`
- `src/main/java/com/fangxuele/tool/push/ui/dialog/NewTaskDialog.java (line 979)`
- `src/main/java/com/fangxuele/tool/push/logic/msgsender/UpYunMsgSender.java (line 32)`
- `src/main/java/com/fangxuele/tool/push/ui/dialog/UpdateDialog.java (line 84)`
- `src/main/java/com/fangxuele/tool/push/ui/dialog/UpdateInfoDialog.java (line 84)`
- `src/main/java/com/fangxuele/tool/push/ui/dialog/importway/ImportByDing.java (line 94)`
- `src/main/java/com/fangxuele/tool/push/ui/dialog/importway/ImportByDing.java (line 162)`
- `src/main/java/com/fangxuele/tool/push/ui/dialog/importway/ImportByDing.java (line 289)`
- `src/main/java/com/fangxuele/tool/push/ui/dialog/importway/ImportByDing.java (line 462)`
- `src/main/java/com/fangxuele/tool/push/ui/dialog/importway/ImportByDing.java (line 540)`
- `src/main/java/com/fangxuele/tool/push/ui/listener/HelpListener.java (line 28)`
- `src/main/java/com/fangxuele/tool/push/ui/form/msg/DingMsgForm.java (line 103)`
- `src/main/java/com/fangxuele/tool/push/ui/form/AboutForm.java (line 123)`
- `src/main/java/com/fangxuele/tool/push/ui/listener/AboutListener.java (line 45)`
- `src/main/java/com/fangxuele/tool/push/ui/listener/AboutListener.java (line 81)`
- `src/main/java/com/fangxuele/tool/push/ui/form/msg/MailMsgForm.java (line 72)`
- `src/main/java/com/fangxuele/tool/push/ui/form/msg/MailMsgForm.java (line 242)`

</details>

<details id="Quartz_Scheduler_usage_detected">
<summary><b>Quartz Scheduler usage detected</b> — affected files</summary>

- `pom.xml (line 306)`

</details>

<details id="SQLite_usage_detected">
<summary><b>SQLite usage detected</b> — affected files</summary>

- `pom.xml (line 291)`

</details>

## Upgrade Issues

| Issue Name | Criticality | Story Points | Occurrences |
|------------|-------------|--------------|-------------|
| Java Version is not the latest LTS | Optional | 8 | [2](#Java_Version_is_not_the_latest_LTS) |

### Issue Details

<details id="Java_Version_is_not_the_latest_LTS">
<summary><b>Java Version is not the latest LTS</b> — affected files</summary>

- `pom.xml (line 40)`
- `pom.xml`

</details>

## Security Issues

> **Note:** These issues were generated by AI and may contain inaccuracies or incomplete information. Please review carefully.

| Issue Name | Criticality | Story Points | Files |
|------------|-------------|--------------|-------|
| CWE-502: Deserialization of Untrusted Data | Mandatory | 13 | [1](#CWE-502_Deserialization_of_Untrusted_Data) |
| CVE-2023-6378: logback serialization vulnerability | Mandatory | 1 | [1](#CVE-2023-6378_logback_serialization_vulnerability) |
| CVE-2023-22102: MySQL Connectors takeover vulnerability | Mandatory | 1 | [1](#CVE-2023-22102_MySQL_Connectors_takeover_vulnerability) |
| CVE-2023-24162: Dromara Hutool Deserialization of Untrusted Data vulnerability | Mandatory | 1 | [1](#CVE-2023-24162_Dromara_Hutool_Deserialization_of_Untrusted_Data_vulnerability) |
| CVE-2023-24163: Dromara hutool vulnerable to SQL Injection | Mandatory | 1 | [1](#CVE-2023-24163_Dromara_hutool_vulnerable_to_SQL_Injection) |
| CVE-2022-25845: Unsafe deserialization in com.alibaba:fastjson | Mandatory | 1 | [1](#CVE-2022-25845_Unsafe_deserialization_in_com_alibaba_fastjson) |
| CVE-2021-0341: Square OkHttp can accept the wrong certificate | Mandatory | 1 | [1](#CVE-2021-0341_Square_OkHttp_can_accept_the_wrong_certificate) |
| CVE-2018-3258: Improper Privilege Management in MySQL Connectors Java | Mandatory | 1 | [1](#CVE-2018-3258_Improper_Privilege_Management_in_MySQL_Connectors_Java) |
| CWE-820: Missing Synchronization | Potential | 8 | [1](#CWE-820_Missing_Synchronization) |
| CWE-1057: Data Access Operations Outside of Expected Data Manager Component | Potential | 5 | [1](#CWE-1057_Data_Access_Operations_Outside_of_Expected_Data_Manager_Component) |
| CWE-543: Use of Singleton Pattern Without Synchronization in a Multithreaded Context | Potential | 5 | [1](#CWE-543_Use_of_Singleton_Pattern_Without_Synchronization_in_a_Multithreaded_Context) |
| CWE-567: Unsynchronized Access to Shared Data in a Multithreaded Context | Potential | 5 | [1](#CWE-567_Unsynchronized_Access_to_Shared_Data_in_a_Multithreaded_Context) |
| CWE-672: Operation on a Resource after Expiration or Release | Potential | 5 | [1](#CWE-672_Operation_on_a_Resource_after_Expiration_or_Release) |
| CWE-681: Incorrect Conversion between Numeric Types | Potential | 3 | [1](#CWE-681_Incorrect_Conversion_between_Numeric_Types) |
| CWE-772: Missing Release of Resource after Effective Lifetime | Potential | 3 | [1](#CWE-772_Missing_Release_of_Resource_after_Effective_Lifetime) |
| CWE-775: Missing Release of File Descriptor or Handle after Effective Lifetime | Potential | 3 | [1](#CWE-775_Missing_Release_of_File_Descriptor_or_Handle_after_Effective_Lifetime) |
| CWE-778: Insufficient Logging | Potential | 3 | [1](#CWE-778_Insufficient_Logging) |
| CWE-99: Improper Control of Resource Identifiers ('Resource Injection') | Potential | 3 | [1](#CWE-99_Improper_Control_of_Resource_Identifiers_Resource_Injection) |
| CWE-22: Improper Limitation of a Pathname to a Restricted Directory ('Path Traversal') | Optional | 8 | [1](#CWE-22_Improper_Limitation_of_a_Pathname_to_a_Restricted_Directory_Path_Traversal) |
| CWE-23: Relative Path Traversal | Optional | 5 | [1](#CWE-23_Relative_Path_Traversal) |
| CWE-36: Absolute Path Traversal | Optional | 5 | [1](#CWE-36_Absolute_Path_Traversal) |

### Security Issue Details

<details id="CWE-502_Deserialization_of_Untrusted_Data">
<summary><b>CWE-502: Deserialization of Untrusted Data</b> — affected files</summary>

- `src/main/java/com/fangxuele/tool/push/util/UpgradeUtil.java`

</details>

<details id="CVE-2023-6378_logback_serialization_vulnerability">
<summary><b>CVE-2023-6378: logback serialization vulnerability</b> — affected files</summary>

- `pom.xml:86`

</details>

<details id="CVE-2023-22102_MySQL_Connectors_takeover_vulnerability">
<summary><b>CVE-2023-22102: MySQL Connectors takeover vulnerability</b> — affected files</summary>

- `pom.xml:48`

</details>

<details id="CVE-2023-24162_Dromara_Hutool_Deserialization_of_Untrusted_Data_vulnerability">
<summary><b>CVE-2023-24162: Dromara Hutool Deserialization of Untrusted Data vulnerability</b> — affected files</summary>

- `pom.xml:138`

</details>

<details id="CVE-2023-24163_Dromara_hutool_vulnerable_to_SQL_Injection">
<summary><b>CVE-2023-24163: Dromara hutool vulnerable to SQL Injection</b> — affected files</summary>

- `pom.xml:138`

</details>

<details id="CVE-2022-25845_Unsafe_deserialization_in_com_alibaba_fastjson">
<summary><b>CVE-2022-25845: Unsafe deserialization in com.alibaba:fastjson</b> — affected files</summary>

- `pom.xml:169`

</details>

<details id="CVE-2021-0341_Square_OkHttp_can_accept_the_wrong_certificate">
<summary><b>CVE-2021-0341: Square OkHttp can accept the wrong certificate</b> — affected files</summary>

- `pom.xml:310`

</details>

<details id="CVE-2018-3258_Improper_Privilege_Management_in_MySQL_Connectors_Java">
<summary><b>CVE-2018-3258: Improper Privilege Management in MySQL Connectors Java</b> — affected files</summary>

- `pom.xml:48`

</details>

<details id="CWE-820_Missing_Synchronization">
<summary><b>CWE-820: Missing Synchronization</b> — affected files</summary>

- `src/main/java/com/fangxuele/tool/push/ui/form/TaskForm.java`

</details>

<details id="CWE-1057_Data_Access_Operations_Outside_of_Expected_Data_Manager_Component">
<summary><b>CWE-1057: Data Access Operations Outside of Expected Data Manager Component</b> — affected files</summary>

- `src/main/java/com/fangxuele/tool/push/ui/form/TaskForm.java`

</details>

<details id="CWE-543_Use_of_Singleton_Pattern_Without_Synchronization_in_a_Multithreaded_Context">
<summary><b>CWE-543: Use of Singleton Pattern Without Synchronization in a Multithreaded Context</b> — affected files</summary>

- `src/main/java/com/fangxuele/tool/push/ui/form/TaskForm.java`

</details>

<details id="CWE-567_Unsynchronized_Access_to_Shared_Data_in_a_Multithreaded_Context">
<summary><b>CWE-567: Unsynchronized Access to Shared Data in a Multithreaded Context</b> — affected files</summary>

- `src/main/java/com/fangxuele/tool/push/ui/form/MessageManageForm.java`

</details>

<details id="CWE-672_Operation_on_a_Resource_after_Expiration_or_Release">
<summary><b>CWE-672: Operation on a Resource after Expiration or Release</b> — affected files</summary>

- `src/main/java/com/fangxuele/tool/push/util/HikariUtil.java`

</details>

<details id="CWE-681_Incorrect_Conversion_between_Numeric_Types">
<summary><b>CWE-681: Incorrect Conversion between Numeric Types</b> — affected files</summary>

- `src/main/java/com/fangxuele/tool/push/ui/dialog/importway/ImportByWxMp.java`

</details>

<details id="CWE-772_Missing_Release_of_Resource_after_Effective_Lifetime">
<summary><b>CWE-772: Missing Release of Resource after Effective Lifetime</b> — affected files</summary>

- `src/main/java/com/fangxuele/tool/push/util/HikariUtil.java`

</details>

<details id="CWE-775_Missing_Release_of_File_Descriptor_or_Handle_after_Effective_Lifetime">
<summary><b>CWE-775: Missing Release of File Descriptor or Handle after Effective Lifetime</b> — affected files</summary>

- `src/main/java/com/fangxuele/tool/push/ui/dialog/TaskHisDetailDialog.java`

</details>

<details id="CWE-778_Insufficient_Logging">
<summary><b>CWE-778: Insufficient Logging</b> — affected files</summary>

- `src/main/java/com/fangxuele/tool/push/ui/dialog/importway/ImportByFile.java`

</details>

<details id="CWE-99_Improper_Control_of_Resource_Identifiers_Resource_Injection">
<summary><b>CWE-99: Improper Control of Resource Identifiers ('Resource Injection')</b> — affected files</summary>

- `src/main/java/com/fangxuele/tool/push/logic/msgsender/HttpMsgSender.java`

</details>

<details id="CWE-22_Improper_Limitation_of_a_Pathname_to_a_Restricted_Directory_Path_Traversal">
<summary><b>CWE-22: Improper Limitation of a Pathname to a Restricted Directory ('Path Traversal')</b> — affected files</summary>

- `src/main/java/com/fangxuele/tool/push/ui/dialog/importway/ImportByFile.java`

</details>

<details id="CWE-23_Relative_Path_Traversal">
<summary><b>CWE-23: Relative Path Traversal</b> — affected files</summary>

- `src/main/java/com/fangxuele/tool/push/ui/dialog/importway/ImportByFile.java`

</details>

<details id="CWE-36_Absolute_Path_Traversal">
<summary><b>CWE-36: Absolute Path Traversal</b> — affected files</summary>

- `src/main/java/com/fangxuele/tool/push/ui/dialog/importway/ImportByFile.java`

</details>

---

## Codebase Insights

> **Note:** These documents are generated by AI and may contain inaccuracies or incomplete information. Please review carefully.

> **Codebase Insights aren't available yet.**
>
> These documents are generated when assessment runs with **Full analysis** coverage. Re-run the assessment and set `analysisCoverage: full` to enable them.

[Share feedback](https://aka.ms/ghcp-appmod/feedback)
