# Instructions for Use

## 1. Registration Stage

1.1 Username: Email address (**only enterprise/company email addresses are accepted. The backend will review registrations. Non-company email addresses have lower permissions and can only access GitHub monitoring**)

1.2 Password: At least 6 characters

### 2. Code Leak Monitoring

#### Feature Overview:

- After configuring keywords in [Keyword Configuration], the system will monitor them periodically in cycles. To avoid excessive false positives, selected keywords should preferably be longer than 6 characters. Usage experience can be discussed at any time.
- During configuration, you can choose the [File Type] to monitor as needed, such as Java, Python, etc.
    - 1) Default: if `language` is empty, all file formats will be searched.
    - 2) When a language is selected: only the chosen file formats will be searched. If another file type is not available, please contact backend support.
- You can configure [Keyword Configuration] and [Whitelist Configuration] filters. If a monitored result matches the whitelist, the file will be ignored. The whitelist scope can also be configured. Currently supported:
    - (1) File path filtering (including file name)
    - (2) File content filtering
    - (3) Both of the above must match
- Optimize and adjust keywords based on actual operating results.
- [dashboard] will count the number of files associated with each repo. By clicking the repo link, you can participate in GitHub operations.
- GitHub has been implemented; Gitee is still under development.

#### Keyword Configuration:

- Examples include internal API addresses referenced in code, enterprise copyright notices in code headers, or code package names containing the enterprise's primary domain.
- Several common types of indicators:

```text
    Internal domains: Every company has some internal domains used by private APIs, test environments, HR systems,
    email login systems, OA systems, internal knowledge systems, operations systems, release systems, etc.
    These systems often follow specific internal domain naming patterns. Searching these domains helps quickly identify
    whether employees have uploaded notes or documents to the public internet,
    which is especially common among new employees using GitHub or similar tools for note-taking.

    External domains: Public-facing domains can also be selected, especially higher-risk ones such as mail.domain_outer.com
    Code copyright: Copyright notices in code header comments, such as Copyright XXX All Rights Reserved, Taobao.com 版权所有 2003-present
    Host domain: Server HOST names, for example when configuring a private Maven repository, hostnames such as repo.domain.com.cn may be written
    Code package names: Java package names, such as com.domain.projectname
```

- During operations, some keywords may match a large number of files, so multiple methods are provided to reduce false positives:
- Multi-feature keywords: combine code indicators with sensitive words, such as `taobao.com password`
- File type filtering: configure the range of monitored languages in the system and include the company’s main development languages to reduce operational noise
- Multi-dimensional statistics: count the number of hits across different repos as an indicator of correlation
- Asset extraction: determine whether the code is relevant from the perspective of extracted assets, such as internal server addresses, employee IDs, internal domains, package names, etc.
- Full repository scanning: repos will be pulled from GitHub (currently limited to smaller than 100 MB) for full asset scanning

### 3. Dark Web Data Monitoring

- After configuring keywords of interest, the feature can be used, for example for telecom operators or securities firms
- Use the search function to view already collected data
- Monitoring can be configured to enable message push notifications (see Section 5)

### 4. OSINT Asset Collection

#### Feature Overview:

- After configuring keywords in [Keyword Configuration], the system will connect to platforms such as Shodan and ZoomEye and periodically monitor asset data in cycles. To avoid excessive false positives, selected keywords should preferably be longer than 4 characters. Usage experience can be discussed at any time.
- Two monitoring types are currently supported: `hostname` and `title`, such as `baidu.com` or `百度一下`
- Optimize and adjust keywords based on actual operating results
- [dashboard] will provide statistical analysis of associated suspicious assets

### 5. Monitoring Result Notifications

- Supports email and WeChat message notifications
- The notification email address defaults to the email used during registration
- For WeChat notifications, log in and click [Account Information] - [Notification Settings] - [Scan with WeChat] in the upper-right corner
- The backend will periodically monitor and notify users of data from within the last 3 days
