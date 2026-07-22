# Doumen Privacy Policy

Effective Date: With the Doumen v1.0.6 release (pending)
Operator: Individual developer (brand name: Xuyu Tech; identified by the developer/seller shown on the App Store product page)
Contact Email: xuyutechnologies@outlook.com

> Draft for v1.0.6. This version has not been published and is not yet effective. Legal/compliance review and the final effective date are required before release.

Doumen is a local-first bead pattern maker and editor. We designed the core workflow to work without registration, login, or developer-operated image uploads. Some optional features, such as iCloud sync, use Apple system services only when you enable or trigger them.

## 1. Data We Collect

Doumen does not create user accounts, require login, or upload imported images, project files, or exported patterns to servers operated by the individual developer. Starting with v1.0.6, limited mobile analytics may be enabled only when the device system region is set to Mainland China and the user separately opts in. Device, network, and usage information processed for analytics may constitute personal information, as described in Section 4.

If you contact us by email or another support channel, we may receive the contact information and message content you choose to provide. We use that information only to respond to feedback, support requests, or compliance matters.

## 2. Images, Project Data, and Local Processing

Images you import are used to generate, crop, recognize, edit, and export bead patterns on your device. Generated patterns, manual edits, project drafts, inventory inputs, making-session progress, import-plan recognition results, background-removal state, and exported files are stored locally on your device by default.

Image analysis features such as crop detection, color sampling, OCR-assisted pattern import, and background cleanup are designed to run on device. Doumen does not upload your images to Xuyu Tech servers for cloud processing.

PNG export includes an optional project metadata switch, with a second optional switch to embed the original image in PNG metadata. This data is written only into the local PNG file you choose to export, so the project can be restored if the PNG is imported again. If you share that PNG with someone else, the embedded project data or original image will be shared with the file.

## 3. Optional iCloud Sync

Doumen may offer an optional iCloud sync setting. When you enable it, project packages, source assets needed to restore projects, project sync metadata, conflict records, tombstones for deleted projects, and sync diagnostics needed to keep devices consistent may be stored in your Apple iCloud account using Apple system services.

iCloud sync is off unless you enable it or participate in a test build where sync diagnostics are explicitly enabled. Xuyu Tech does not operate a separate project-sync server and does not receive the contents of your iCloud project data through this feature. Apple may process iCloud data under Apple's own terms and privacy policy.

If you disable iCloud sync, Doumen stops initiating project sync for that device. Data that was already stored in iCloud may remain in your iCloud account until removed by app cleanup behavior, device/iCloud settings, or Apple's retention rules.

## 4. Mobile Analytics in Mainland China

Doumen offers the Umeng U-App analytics option only when the device system region is set to Mainland China (`CN`). This setting is used only to determine whether the Mainland China analytics option is offered; it does not mean that Doumen determines or records the user's actual geographic location. The SDK must not initialize or continue reporting before consent, after refusal, or after consent is withdrawn. Refusing analytics does not restrict Doumen's core pattern-tool features. Umeng analytics remains disabled for every other system region.

Analytics is used for app data analysis, including launches, sessions, usage trends, the effect of product improvements, and basic anti-fraud. Based on Umeng's official iOS compliance guide, its current privacy policy, and Doumen's integration scope, the SDK may automatically process and transmit:

- App information, including app version, distribution channel, and SDK version;
- Usage information, including launch/session timing and non-content feature events that pass privacy review;
- Device and system information, including device model, manufacturer, operating-system version, language, time zone, and disk, CPU, and battery information;
- Network information, including IP address, network state, and internet service provider; and
- Device or installation identifiers generated or accessed by the SDK, which on iOS may include IDFA, OpenUDID, GUID, or an Umeng device identifier.

Doumen does not send imported images, pattern contents, project files, project names, or exported files through this SDK. This integration does not request location permission, enable location-based regional analytics, or enable installed-app-list analytics. If archive or on-device testing shows processing outside this list, v1.0.6 must not be released until the wording, configuration, or dependency is corrected.

- SDK: Umeng Mobile Analytics SDK (U-App; current dependencies: UMCommon 7.6.4 / UMDevice 3.6.0)
- Operator: Umeng Tongxin (Beijing) Technology Co., Ltd. (`友盟同欣（北京）科技有限公司`)
- Registered address: Room 701-26, 7/F, No. 2 Haidian East Third Street, Haidian District, Beijing, China
- Processing: after consent, the SDK automatically collects and transmits data to Umeng servers to produce analytics reports; Doumen disables Umeng's overseas-domain path
- Storage scope: Umeng's current policy states that information about Mainland China end users is stored in China
- Retention: Umeng states that it retains information only as needed for service purposes, business records, security/quality, and legal requirements, then deletes or anonymizes it; it does not publish one fixed retention period
- Umeng Privacy Policy: <https://developer.umeng.com/docs/147377/detail/3038360>
- iOS Compliance Guide: <https://developer.umeng.com/docs/147377/detail/214848>
- End-device opt-out: <https://outdip.umeng.com/opt_out.html>
- Umeng privacy contact: `Umeng_Legal@service.umeng.com`

Users may withdraw analytics consent in the app settings or contact us to exercise applicable access, correction, deletion, or other privacy rights. For Umeng-side data, we will help route the request to Umeng; users may also use Umeng's end-device opt-out page or privacy email. The final data inventory, App Store privacy disclosure, retention explanation, and withdrawal workflow remain subject to SDK audit and legal/compliance review before v1.0.6 is released.

> **Quoted declarations from the Apple privacy manifest bundled with UMCommon 7.6.4:**
>
> - Collected data type: `NSPrivacyCollectedDataTypeAdvertisingData`;
> - Linked to identity: `NSPrivacyCollectedDataTypeLinked = false`;
> - Purpose: `NSPrivacyCollectedDataTypePurposeThirdPartyAdvertising`;
> - Used for tracking: `NSPrivacyCollectedDataTypeTracking = true`.
>
> These are declarations in the SDK's `PrivacyInfo.xcprivacy`; they do not by themselves prove that Doumen's current configuration actually accesses or transmits advertising data at runtime. They nevertheless conflict with Doumen's analytics-only, no-advertising purpose. Before release, Umeng must provide a verifiable explanation or corrected SDK, followed by archive privacy-report and on-device network verification. If this cannot be resolved, the Umeng SDK must be removed. This paragraph is a draft audit note and will be replaced by final user-facing wording after closure.

## 5. Permissions

Doumen may request the following system permissions:

- System photo picker: used to choose images and generate bead patterns on your device; Doumen does not request full photo library read access.
- Photo library add access: used to save exported PNG pattern images to Photos.
- File access or sharing features: used to import images, save projects, and export PNG or PDF files.
- iCloud container access: used only for optional project sync, account-change confirmation, and sync repair flows when sync is enabled.

We do not use these permissions for unrelated purposes.

## 6. Diagnostics and Support

Doumen includes local diagnostics to help verify imports, exports, background removal, OCR, making sessions, and iCloud sync behavior. These diagnostics are intended to avoid raw project content where possible and are stored locally unless you choose to share them for support.

If you send screenshots, exported diagnostic packages, sample files, or a support email to us, we use that information only to investigate the issue, respond to your request, maintain support records, or meet legal obligations.

## 7. Third-Party Services

Doumen does not display advertising or include third-party crash reporting, remote configuration, or third-party account login. Umeng U-App is enabled only within the region and consent boundary described in Section 4. Its current Apple privacy-manifest conflict is a v1.0.6 release blocker and does not authorize any expanded data use.

Doumen uses Apple platform services such as Photos, Files, Vision/OCR frameworks, Share Sheet, App Store distribution, and optional iCloud. Those services are governed by Apple's terms and privacy policy.

Before each release, the codebase and dependencies should be checked again. If advertising, analytics, crash reporting, remote configuration, community features, accounts, or developer-operated cloud services are added, this Privacy Policy and the App Store privacy details must be updated.

## 8. Data Retention and Deletion

Local projects, exported files, and images saved to Photos are managed by you on your device. You can delete projects inside the app, and you can delete exported content from Photos, Files, or other destinations where you saved it. Exported files that you have already shared are managed by the recipient or destination platform, and Doumen cannot delete them remotely.

Uninstalling Doumen usually removes project data stored in the app sandbox, but it does not automatically remove content you exported to Photos, Files, iCloud, or other locations.

Because Doumen does not provide Xuyu Tech accounts or Xuyu Tech server-side project storage, there is no Xuyu Tech remote account deletion process.

## 9. Children's Privacy

Doumen is intended for general craft and creative use and has a 4+ age rating on the App Store. That rating describes content suitability; it does not mean that Doumen identifies a user's age or automatically obtains parental or guardian consent. Doumen does not ask for a date of birth or age and does not implement age recognition, age gating, or profiling of minors.

For a user under 14, a parent or guardian should review this policy and the analytics notice and decide whether to consent to optional Umeng analytics. The parent or guardian may choose “Decline” without affecting core app features. If a parent or guardian believes that analytics information about a user under 14 was processed without their consent, they may contact us. We will stop further processing and, after verification, help submit a deletion request to Umeng. We will not introduce routine age collection solely to handle such requests.

## 10. User Content and Copyright

You are responsible for ensuring that you have the right to use images you import into Doumen. Doumen provides local conversion, editing, and export tools and does not review the copyright status of imported images.

## 11. Changes to This Policy

If Doumen later adds accounts, community features, analytics, crash reporting, advertising, developer-operated cloud services, or other network services, we will update this Privacy Policy and, when required, the App Store privacy details.

## 12. Contact Us

If you have questions about this Privacy Policy or Doumen's data practices, contact us at:

```text
xuyutechnologies@outlook.com
```
