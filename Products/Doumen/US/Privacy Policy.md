# Doumen Privacy Policy

Last Updated: November 13, 2026
Operator: ZhangXu (Chinese name: 张旭; brand name: Xuyu Tech)
Contact: xuyutechnologies@outlook.com

Doumen is a local-first bead pattern maker and editor. This policy explains how Doumen handles your information and how you can manage it.

## 1. On-Device Processing

Doumen does not require registration or login. Images you import, patterns you create, project names, edits, inventory and making progress, export settings, and language and appearance preferences are stored on your device by default.

Image cropping, color sampling, OCR-assisted import, and background cleanup are performed on your device. Diagnostic records remain local by default; you can choose to send diagnostics through Report a Problem in the app or separately email materials to support.

Exported PNG files may contain project data and the source image. If you share such a file, its embedded data is shared with it.

### User-Initiated Share Codes

When you choose to create a share code, the encoded data for the selected pattern, including its dimensions, palette, and grid contents, is uploaded to the Doumen sharing service to create the code and allow people with the code to retrieve the pattern. The sharing service receives the IP address of network requests. A randomly generated installation credential used to manage shares is stored on your device and provided in related requests.

### User-Initiated Diagnostic Feedback

Only when you tap Send in Doumen’s Report a Problem form does Doumen send the permitted diagnostic records and your optional problem description and contact email to the diagnostic service. Neither a description nor an email address is required. Diagnostics are not uploaded automatically or silently. Materials you separately email to support are used only to handle your request.

In iOS versions that support installation association, a report you choose to send may also contain a SHA-256 digest of this installation’s credential, used to associate reports from the same installation. Doumen reuses the existing local sharing credential; if it is missing when you first open feedback, the existing mechanism creates it locally, without creating a separate diagnostic identity or sending the credential itself. This field belongs to the report environment, not to the failure-event summaries described below. It is neither an account nor a permanent hardware identity, and reinstalling, clearing data, or device migration may affect association. The field can be omitted if the credential is unavailable or retrieval times out, without preventing feedback. The local credential follows its existing retention mechanism; the digest is uploaded only when you choose to send a report, retained with that report for the seven-day period below, and not used for advertising tracking.

Diagnostic records may include app and OS versions, device model, random run/page/action associations, fixed operation and error codes, counts and durations, resource summaries, source-image dimensions and byte counts, normalized crop bounds, complete import links from supported sources, manual review coordinates and color-confirmation or undo records, and backup identifiers and snapshot times used to connect troubleshooting evidence. Sync diagnostics may also include anonymous object and content associations within one session, file-role categories, validation rules, and lifecycle categories, format versions, and necessary counts for local, remote, and previous-sync states. Sync object and content associations in feedback change between sessions; original project or cloud-record identifiers, original content hashes, account identities, and sync credentials are not sent. Complete import links may contain access tokens; please do not publish a feedback report. Feedback does not upload source images or project files. The new system summaries do not include raw system logs, call stacks, or arbitrary exception text.

OS-provided crash, hang, and exit-category summaries may cover approximately the previous 24 hours or older delayed reports. Their coverage interval, receipt time, and source build are recorded separately. They do not establish that an event occurred during your current action or app run, and missing records do not establish that no problem occurred.

Ordinary on-device diagnostics use a rolling 30-minute window. System summaries are retained only if received within 30 minutes, although their original OS coverage period may be older. Sanitized summaries and limited direct evidence of allowlisted startup upgrade failures, local data mount failures, and data-version protection blocks that ultimately prevent access to the app, as well as sync failures, may be retained locally for up to seven days. This does not extend the full activity history. Startup blocks and sync failures are recorded separately; sync cancellation and ordinary account or inventory selection prompts do not qualify for seven-day retention on that basis. A summary expires seven days after that failure is first recorded; each item of direct evidence expires seven days after its original occurrence. Repeated failures do not renew these periods, and recovery does not reset them. A genuinely successful sync may record recovery; dismissing a prompt does not establish recovery.

Seven-day failure summaries may include fixed failure and error codes, necessary migration or sync state, source builds, random incident or session associations, first and last recorded times, repeat counts, and recovery results. Limited sync-failure evidence may also contain the anonymous object and content associations within one session described above. They do not include arbitrary exception text, raw call stacks, project names, file paths, accounts, persistent device or project identifiers, original cloud-record identifiers, original content hashes, sync credentials, complete import links, source images, or project files. The startup-block area and sync-failure area each hold at most 16 incidents, each with at most 16 direct evidence records, and each area is limited to 512 KiB. Startup-block incidents are also limited to 32 KiB each. Ordinary events, system summaries, both types of failure records, and pending snapshots share a maximum local allowance of 2 MiB; storage pressure may remove records earlier. When the app is not running, physical files cannot be cleaned up at their exact expiry time. Cleanup runs first on the next launch, and expired records are not sent again.

Reports still upload only when you tap Send and are used only for restricted internal troubleshooting. Server rules remain unchanged: reports are retained for seven days after server receipt, become unavailable to internal readers on expiry, and are removed by scheduled cleanup. The local and server retention periods start separately, so the server retention period may end nearly fourteen days after the original failure. Only a minimal used-report-code marker is kept long term to prevent an old code from referring to another report.

## 2. Optional iCloud Sync on iOS/iPadOS

iCloud sync is available only on iOS/iPadOS; the Android version does not provide iCloud sync. If you enable iCloud sync on iOS/iPadOS, project files, source assets, and sync metadata are stored in your iCloud account through Apple services. Doumen does not operate a separate project-sync server and does not receive your iCloud project content through this feature.

After sync is disabled, the current device stops syncing. Data already stored in iCloud remains under your control through Doumen, device settings, or iCloud. Apple processes this data under its terms and privacy policy.

## 3. Analytics

Doumen enables Umeng (U-App) mobile analytics only after you agree. The Android version may call Umeng pre-initialization before you agree; according to Umeng, this step does not collect or transmit device information. Umeng is fully initialized after you agree. If you decline, Doumen exits and you can open it again to choose.

Umeng analytics is used to understand app launches, sessions, and feature usage so we can improve the product and perform basic anti-fraud checks. The information that may be processed includes:

- App information: app version, release channel, and SDK version;
- Usage information: launch time, session duration, and feature events that do not include images, patterns, or project content;
- Device and system information: device model, operating system version, language, time zone, disk, CPU, and battery information;
- Network information: IP address, network status, and network service provider;
- Device or installation identifiers: which may include Android ID, OAID (on Android devices), IDFA, OpenUDID, GUID, or the Umeng device identifier.

Doumen does not upload your imported images, pattern content, project files, project names, or exported files through Umeng, and does not collect precise location or a list of installed apps through Umeng.

- Service name: Umeng Mobile Analytics SDK (U-App)
- Service provider: Umeng Tongxin (Beijing) Technology Co., Ltd. (友盟同欣（北京）科技有限公司)
- How it is used: after you agree, the SDK automatically collects the information above and transmits it to Umeng servers to generate analytics reports
- Storage location: under the Umeng privacy policy, the information is stored in China
- Retention: kept only for the shortest period needed to serve the analytics and anti-fraud purposes and to meet security and legal obligations, then deleted or anonymized
- [Umeng Privacy Policy](https://www.umeng.com/page/policy)
- [Umeng device opt-out page](https://outdip.umeng.com/opt_out.html)
- Umeng privacy contact: Umeng_Legal@service.umeng.com

We require third parties to protect your information in accordance with this policy and applicable law.

## 4. Extracting Images from Share Links

When you choose to extract images from a share link, Doumen requests the linked content and downloads images directly from the source platform and its image services. Those services receive the link information needed for the request (which may include a share token), your IP address, and network information such as request headers, and process it under their own rules. Doumen does not relay these requests through developer-operated servers; pattern recognition and editing remain on device. Saving images to Photos depends on your selection and system permission.

### Announcement Requests

Versions of Doumen that support announcements request them from the announcement service, for example when refreshing on the home screen or returning to the foreground. The request includes the app version, release channel, operating system version, and device model; the server also receives the IP address needed for the network request.

## 5. System Permissions

Doumen uses the following system features only when required for the related function:

- System photo or file picker: choose images to process;
- Photo-library add permission: save exported images to Photos;
- File and sharing features: import, save, or share files; and
- iCloud (iOS/iPadOS only): sync projects after you enable sync.

## 6. Retention, Deletion, and Your Rights

You manage local projects on your device; diagnostic records and submitted reports follow the windows and retention periods above. Uninstalling Doumen usually removes data in the app sandbox. Content saved to Photos, Files, iCloud on iOS/iPadOS, or shared with others must be managed or deleted in those locations.

Support email is retained only as needed to respond, maintain necessary records, or meet legal obligations.

You can access, export, correct, or delete local data through Doumen and system features. You may also contact us to request access, correction, deletion, or other applicable privacy rights.

### Children's Personal Information

If a user is under 14, their parent or other guardian should read this policy with them and decide whether to consent before their personal information is processed. The relevant sections of this policy describe the purposes, methods, types, third parties, and specified retention periods for information processing. A guardian may use the contact email below to request access, correction, deletion, withdrawal of consent, or to make a complaint.

Doumen does not request a date of birth or age and does not use age identification, age gates, or profiling of minors.

## 7. Policy Updates and Contact

If our information practices change materially, we will update this policy and seek consent again where required by law.

For questions, comments, or complaints, contact: xuyutechnologies@outlook.com
