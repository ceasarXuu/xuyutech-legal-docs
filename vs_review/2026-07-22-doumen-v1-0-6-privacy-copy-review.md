# Subagent VS Review: Doumen v1.0.6 隐私文案

- Created: 2026-07-22 17:15 +08:00
- Updated: 2026-07-22 18:05 +08:00
- Report schema: adversarial-v1
- Task: 对 Doumen v1.0.6 中英文隐私政策草案执行基于最新法规、平台规则与行业常见写法的对抗性审查。
- Report path: `vs_review/2026-07-22-doumen-v1-0-6-privacy-copy-review.md`
- Review mode: fresh internal subagents
- Source session policy: no inherited main-agent context; reviewer receives only the review packet
- Status: blocked

## Round 1: 法律文案与用户理解风险审查

### Review Input

#### Objective

识别草案中可能导致告知无效、单独同意不足、第三方 SDK 披露不完整、权利行使路径不清、事实表述无法举证或中英文不一致的问题，并与中国现行规则、Apple 最新要求、友盟官方材料和主流隐私政策结构比较。

#### Review Target

安全、隐私、数据处理与用户可理解性文档审查；只审查，不修改目标文案。

#### Target Locations

- `Products/Doumen/CN/隐私政策.md`
- `Products/Doumen/US/Privacy Policy.md`
- `Products/Doumen/CN/index.html`
- `Products/Doumen/US/index.html`
- `/Volumes/xu-512/Projects/doumen/docs/release/v1.0.6/埋点专题/README.md`
- `/Volumes/xu-512/Projects/doumen/ios/Doumen/Doumen/UmengAnalyticsBootstrap.swift`

#### Change Introduction

草案新增友盟 U-App 移动统计披露，拟仅在系统地区为中国大陆且用户明确同意后启用；其他地区不启用。文案尚未发布，隐私弹窗和撤回流程尚未实现。

#### Risk Focus

- 告知事项是否覆盖处理者、目的、方式、种类、保存期限、权利行使方式及第三方接收方要求。
- “明确同意”是否足以覆盖向第三方提供个人信息所需的单独同意及弹窗颗粒度。
- SDK、运营主体、数据字段、权限、设备标识符、网络端点、保存期限和退出机制是否准确且可证明。
- “仅系统地区 CN”与法律适用范围、实际所在地和用户预期是否混淆。
- Markdown 与 HTML、中英文之间是否完整一致。

#### User-Perspective Review Focus

- 普通用户能否在首次弹窗和完整政策中理解谁收集什么、为什么、给谁、保存多久、如何拒绝或撤回。
- 用户是否会把“系统地区”误解为实际地理定位。
- 权利请求入口、响应流程与拒绝后的产品影响是否明确。

#### Implementation Completeness Focus

- 文案声称的同意、拒绝、撤回与停止上报能力尚未落地，需判断发布前阻断是否充分。
- HTML 是否只是摘要而非完整政策，是否遗漏 Markdown 新增的关键法定告知事项。
- SDK 数据清单、PrivacyInfo、App Store Privacy 与网络取证尚待审计。

#### Target Benefit Focus

- “有限统计、范围不扩大、拒绝不影响核心功能”的合规与信任收益尚未通过数据清单和运行证据证明，检查是否存在反向误导风险。

#### Assumptions To Attack

- 友盟官方隐私政策链接、主体和 SDK 数据范围足以支撑现有表述。
- 系统地区代码可以作为唯一启用边界且不会被视为定位或歧视性判断。
- 设置页撤回能立即停止所有后续处理。
- 双语摘要页与完整政策具有同等告知效力。

#### Adversarial Lenses

- requirements
- data
- security
- usability
- comprehension
- implementation-completeness
- maintenance
- observability

#### Verification Status

- 文案为本地草案，未发布。
- App 已有 CN 地区门控，但隐私同意、拒绝和撤回尚未实现。
- SDK 自带隐私清单已通过 plist 语法检查，实际数据清单和网络行为尚未完成真机取证。
- 主代理将另行核对最新官方法规、Apple 与友盟资料。

#### Reviewer Instructions

- Fresh internal subagent session.
- No inherited main-agent context.
- Read target files directly.
- Do not modify files.
- Search current official sources and distinguish binding law, platform rule, vendor guidance, and mainstream drafting convention.
- Cite evidence paths, line numbers, source titles, URLs and access dates when possible.
- Return structured findings matching the report template, with counterexamples for every blocking or major finding.

### Internal Subagent Unavailable Fallback

- Internal subagent unavailable reason: n/a
- Local CLI discovery commands: n/a
- Discovered CLI candidates: n/a
- User-recommended alternative agent requested: n/a
- User-recommended agent command: n/a
- User-recommended agent verification: n/a
- User approval requested: n/a
- User-approved CLI command: n/a
- User decision: n/a
- Fallback outcome: n/a

### Reviewer Timeout Policy

| Complexity | Initial Wait | Extension | Max Attempts Per Role | Blocking Closure Behavior |
|---|---:|---:|---:|---|
| high-risk | 20 minutes | one bounded 10-minute extension | 2 | cannot pass if review is unavailable |

### Reviewer Selection

| Reviewer | Reason Selected | Risk Area |
|---|---|---|
| security-adversary | 文案涉及第三方 SDK、个人信息、跨主体提供、同意与撤回，最高价值风险是隐私与数据边界失实 | data, privacy, consent, third-party disclosure |

### Reviewer Launch Records

| Reviewer | Internal Mechanism | Session / Job ID | Trace Source | Context Forked | Input Packet | Context Explicitly Excluded | Read-only |
|---|---|---|---|---|---|---|---|
| security-adversary | internal `spawn_agent` | `/root/privacy_copy_adversary` | collaboration spawn event | `fork_turns=none` | Round 1 Review Input | main-agent history, reasoning, drafts, conclusions and full diff | yes |

### Reviewer Timeout Records

| Reviewer | Attempt | Wait Window | Outcome | Action |
|---|---:|---:|---|---|
| security-adversary | 1 | 20 minutes | completed | 接收完整报告，无需延期或替代审查员 |

### Reviewer Outputs

#### 审查结论

**不允许发布当前 v1.0.6 隐私文案，也不允许提交当前包含友盟 SDK 的构建。** 审查员识别出 7 项发布阻断和 5 项重要非阻断风险。最严重的事实冲突是：中国区冷启动会在取得同意前初始化友盟；所集成 UMCommon 7.6.4 的 `PrivacyInfo.xcprivacy` 声明 `AdvertisingData`、`ThirdPartyAdvertising` 和 `NSPrivacyTracking=true`，而草案称不用于广告或跨应用跟踪。

#### 发布阻断

| ID | Finding | Counterexample / Evidence |
|---|---|---|
| B1 | 中国区冷启动在同意前初始化友盟，违反草案自身承诺及“同意前不得收集”的监管口径。 | `DoumenApp.swift:72-75` 调用启动逻辑；`UmengAnalyticsBootstrap.swift:24-36` 直接执行 `UMConfigure.initWithAppkey`，没有持久化同意状态门控。首次运行且系统地区为 CN 的用户尚未作出选择时即会初始化。 |
| B2 | 第三方接收方告知和单独同意要素不完整。 | 草案以“友盟+（具体运营主体以现行隐私政策为准）”替代准确主体，仅笼统列举“设备信息、网络信息、应用使用情况”，缺少接收方准确名称/联系方式、逐项字段、处理方式、保存期限、权利路径及角色判断。若友盟为独立处理者，尚缺《个人信息保护法》第 23 条要求的单独同意。 |
| B3 | “撤回后停止上报”的承诺没有实现依据。 | App 没有同意状态模型、撤回 API、SDK 停止/禁用、缓存清理或服务端删除流程；仅有初始化路径。离线事件、SDK 本地缓存和已上传数据均没有已验证的处置方式。 |
| B4 | SDK 自带隐私清单与草案核心陈述直接冲突。 | 本地 UMCommon 7.6.4 的隐私清单声明广告数据、第三方广告目的及跟踪；二进制可见 IDFA/AdSupport 相关符号。它不等于已证明运行时实际读取 IDFA，但足以要求在发布前取得厂商解释、升级或替换 SDK，并通过 Xcode Privacy Report 和网络取证闭环。 |
| B5 | “系统地区为 CN”不是用户实际位于中国大陆的证明。 | 海外用户可将系统地区设为中国，中国境内用户也可设置为其他地区。当前产品边界可保留，但文案必须准确称为“系统地区设置”，不得表述为实际地理位置；仍需证明这一门控符合友盟适用范围和产品承诺。 |
| B6 | 未成年人路径不足。 | 草案仅笼统表示重视未成年人保护；没有 14 周岁以下识别、禁用统计或监护人同意路径。若可能处理未满 14 周岁用户的设备和使用数据，应在发布前选择“默认不启用统计”或建立专门规则与监护人同意。 |
| B7 | 公网页 HTML 是不完整摘要，且与 Markdown 草案存在矛盾。 | HTML 缺少新增友盟的完整主体、字段、期限、权利和同意要素；中文页仍称不同意政策应停止使用服务，与“拒绝非必要统计不影响核心功能”冲突。用户从公网页无法获得与完整政策等价的信息。 |

#### 重要非阻断风险

| ID | Finding | Counterexample / Evidence |
|---|---|---|
| N1 | “默认不收集可识别个人身份数据/PII”口径过窄且可能误导。 | 设备标识、IP、网络和使用记录可能属于个人信息，即使不含姓名或实名身份。应改为准确的数据分类和用途说明。 |
| N2 | 禁止海外域名不能证明不存在跨境传输。 | 域名字符串检查无法证明 DNS、CDN、供应商后台存储和后续访问地点；需厂商材料与运行网络证据。 |
| N3 | “聚合统计”可能使用户误认为上传前已匿名化。 | SDK 可能先上传设备/事件级数据，再在服务端聚合；应区分采集阶段与报表呈现阶段。 |
| N4 | “Xuyu Tech”可能只是品牌名，不足以识别个人信息处理者。 | 政策应给出可核验的法定主体名称、联系地址和有效联系方式。 |
| N5 | 英文摘要罗列 GDPR、CCPA、APPI、PIPA，但没有对应地区权利说明。 | 若并未面向相应地区提供完整区域性告知，应删除装饰性法域清单；若确有分发，则补齐实质性地区条款。 |

#### 实现完整性与收益警告

- 隐私弹窗、同意版本记录、拒绝、撤回、儿童保护、缓存/删除路径、App Store Privacy 对照和真机网络证据均未完成。
- 当前实现使“同意前零请求”这一目标发生事实回归；“有限统计”“不扩大范围”“拒绝不影响核心功能”尚未有可复验的运行证据。
- 在 SDK 清单冲突未解决前，继续使用“不用于广告或跟踪”的绝对表述会放大用户信任和 App Review 风险。

#### 审查员要求的修复、测试和日志

**Required fixes**

- RF1：移除无条件初始化，建立同意后才可初始化的唯一入口。
- RF2：补齐准确法律角色、主体、联系方式、字段、目的、处理方式、期限和权利路径。
- RF3：若友盟为独立处理者，增加向其提供个人信息的单独同意。
- RF4：实现真实可验证的撤回、停止、缓存处置及删除/退出流程后再作承诺。
- RF5：解决 SDK 隐私清单的广告/跟踪冲突；若无法可信解决，则移除 SDK。
- RF6：准确说明系统地区门控边界，并取得厂商适用范围证据。
- RF7：确定 14 周岁以下用户方案：禁用统计，或建立监护人同意和专门规则。
- RF8：为 Markdown、HTML、弹窗、设置页和 App Store Privacy 建立单一事实源。
- RF9：以准确法定主体替换品牌占位表达。
- RF10：发布前冻结生效日期、文档版本并完成法律签核。

**Missing tests**

- T1：首次启动、同意前零 SDK 初始化、零网络、零 SDK 存储。
- T2：同意后只初始化一次，并记录同意版本与时间。
- T3：拒绝后不初始化、不反复强迫弹窗，核心功能正常。
- T4：撤回在当前进程、重启、离线缓存后恢复联网等场景均停止处理。
- T5：系统地区切换、旅行、海外 CN 与中国非 CN 等边界场景。
- T6：未满 14 周岁和监护人路径。
- T7：中英文弹窗、设置页和 VoiceOver 可理解性。
- T8：Markdown、HTML、弹窗、第三方清单和 App Store Privacy 的一致性。
- T9：归档产物和 Xcode Privacy Report 自动阻断广告/跟踪声明冲突。
- T10：按 SDK 版本核验端点、字段、权限、磁盘写入和后台行为。
- T11：访问、更正、删除、撤回等权利请求的时限和工单演练。

**Missing logs / audit evidence**

- L1：隐私安全的同意状态、政策版本和迁移记录。
- L2：不启动原因：`no_consent`、`refused`、`withdrawn`、`under_age`、`unsupported_scope`。
- L3：撤回、SDK 停止、缓存处置和删除请求的审计记录。
- L4：处理目的、字段或政策发生实质变化时的重新同意记录。
- L5：每个发布构建对应的 SDK 版本、隐私清单和网络证据。
- L6：App Store Privacy 与 Xcode Privacy Report 的核对和签核记录。
- L7：个人权利请求工单、完成状态和 SLA 记录。
- L8：审计系统地区门控日志是否不必要地暴露用户设置偏好。

### Main Agent Response

#### Findings triage

| ID | Decision | Rationale | Action / Owner |
|---|---|---|---|
| B1 | accept | 代码证据直接成立，且与监管规则和文案承诺冲突。 | v1.0.6 发布阻断；App 工程修复后复审。 |
| B2 | accept | 《个人信息保护法》第 17、23 条和《网络数据安全管理条例》第 21 条要求的告知要素未齐。 | 法律文案与厂商角色材料补齐后复审。 |
| B3 | accept | 当前没有能支撑撤回承诺的产品或 SDK 控制能力。 | 先实现并验证，再采用确定性文案。 |
| B4 | accept | 本地归档证据与草案绝对陈述冲突，不能仅依赖厂商概括性说明。 | 要求友盟书面说明/升级方案；无法解决则不集成。 |
| B5 | accept | 保留用户已决定的“系统地区 CN”产品边界，但必须消除“实际位于中国”的暗示。 | 产品与法律文案共同冻结准确表述；验证厂商接受该边界。 |
| B6 | accept | 统计数据可能落入未满 14 周岁敏感个人信息处理场景，不能留作上线后处理。 | 产品负责人决定禁用或监护人同意方案。 |
| B7 | accept | 公网页与完整草案确有遗漏和冲突。 | 发布前从单一事实源生成双语完整页面。 |
| N1 | accept | PII 不是中国法下“个人信息”的等价边界。 | 删除“默认不收集 PII”式概括，改用具体清单。 |
| N2 | accept | 静态域名审计不能证明数据驻留。 | 增加供应商证明和真机网络取证。 |
| N3 | accept | “聚合”描述了报表，不一定描述原始处理。 | 分开说明原始采集与聚合报表。 |
| N4 | accept | 处理者身份必须可核验。 | 等待提供准确法定主体信息。 |
| N5 | accept | 法域罗列不能代替实质性区域通知。 | 依据实际发行范围删除或补齐。 |

#### Required-fix triage

| IDs | Decision | Tracking |
|---|---|---|
| RF1–RF10 | accept | 全部纳入 v1.0.6 隐私与埋点发布门禁；本轮仅审查，不实施目标文案或 App 修复。 |

#### Test triage

| IDs | Decision | Tracking |
|---|---|---|
| T1–T11 | accept | 作为修复完成后的 focused smoke/regression 与发布候选隐私审计清单。 |

#### Logging and evidence triage

| IDs | Decision | Tracking |
|---|---|---|
| L1–L8 | accept | 纳入 v1.0.6 可观测性与发布证据包；日志不得包含原始设备标识或新的非必要个人信息。 |

#### 主审补充依据

- 《个人信息保护法》第 14–17、19、23、47、50、55 条分别覆盖知情自愿同意、便捷撤回、非必要处理不得影响服务、告知要素、最短保存期限、向其他处理者提供时的单独同意、删除、权利机制和影响评估。
- 《网络数据安全管理条例》第 21–23 条进一步要求以清单等形式集中展示收集和向其他处理者提供的个人信息，并禁止通过频繁弹窗等方式强迫同意。
- 《App 违法违规收集使用个人信息行为认定方法》明确要求首次运行通过弹窗提示、逐项列出第三方 SDK 的目的/方式/范围、同意前不得收集，并提供撤回路径。
- 2025 年网信部门执法通报已将“未逐一列出 SDK”“目的、方式、范围披露不准确”列为现实处罚问题。
- Apple 要求开发者准确申报所有第三方 SDK 的数据收集、关联和跟踪情况，并对第三方代码承担责任；Xcode 会合并依赖项隐私清单。
- 2026 年《互联网应用程序个人信息收集使用规定（征求意见稿）》仅作为趋势参考，不作为现行强制法源；其中结构化功能清单、SDK 名称/版本/运营者/字段和首次弹窗等方向与现行监管实践一致。
- 主流写法不是把所有内容塞进一段政策，而是采用“首层简短弹窗 + 完整隐私政策 + 个人信息收集清单 + 第三方 SDK/共享清单 + 设置页隐私选择”的分层结构。支付宝等成熟产品也采用独立 SDK 和第三方共享说明附件；该结构同时更符合现行条例的清单式要求。

### Closure Status

- Blocking findings found: yes (7)
- Accepted blocking findings fixed: no（用户本轮要求审查，不要求修改）
- Blocking re-review completed: no（修复尚未实施，不启动形式化 closure round）
- Blocking re-review passed: no
- Rejected findings backed by evidence: n/a（无 rejected finding）
- Deferred findings documented: n/a（无 deferred finding）
- Implementation completeness gaps resolved or accepted by user: no
- Target benefit warnings recorded: yes
- Blocked reason: 7 项发布阻断尚未修复，尤其是同意前初始化和 SDK 隐私清单广告/跟踪冲突。
- Allowed to proceed: no

## Final Conclusion

本轮对抗性审查完成，结论为 **blocked**。当前草案不得发布，当前含友盟 SDK 的 v1.0.6 构建不得提交审核。应先实施 RF1–RF10，完成 T1–T11 和 L1–L8 的证据闭环，再由一个新的独立审查员执行 Round 2 closure review；只有阻断项全部关闭后才可进入法律文档发布和版本提交流程。

本报告属于产品与工程合规审查记录，不替代执业律师针对具体运营主体、数据角色和发行地区出具的正式法律意见。

## Requester Clarification Follow-up（2026-07-22）

- 用户确认豆门是个人开发 App。草案已将运营者改为“个人开发者（品牌名 Xuyu Tech；以 App Store 产品页显示的开发者/销售方为准）”，并保留可直接联系的隐私邮箱。N4 的“误写为公司主体”风险已处理；最终发布仍应核对 App Store 展示身份与政策完全一致。
- 已通过友盟开发者中心文档接口核验 2026-06-05 生效的最新版友盟隐私政策，以及官方《移动统计 SDK 合规配置指引（iOS）》。草案已补入友盟同欣（北京）科技有限公司、注册地址、官方字段范围、存储/期限确定方式、退出入口和隐私联系邮箱。
- B2 中“友盟运营主体缺失”的子项已修正，但友盟在具体集成关系中的法律角色、统一固定保存天数未由官方材料明确，仍需以开发者协议/工单答复或最终法律审查关闭。
- B4 不因采用友盟官方参考文案而关闭：当前 UMCommon 7.6.4 的 Apple 隐私清单仍声明广告数据、第三方广告目的和跟踪。草案已显著标为发布阻断；不得用概括性的官方模板覆盖本地归档证据。
- 本次更新没有发布或推送法律文档，也没有将整体审查状态从 `blocked` 改为通过。

## Official and Industry Sources

- [《中华人民共和国个人信息保护法》](https://www.cac.gov.cn/2021-08/20/c_1631050028355286.htm)，国家互联网信息办公室，访问于 2026-07-22。
- [《网络数据安全管理条例》](https://www.cac.gov.cn/2024-09/30/c_1729384452307680.htm)，国家互联网信息办公室，访问于 2026-07-22。
- [《常见类型移动互联网应用程序必要个人信息范围规定》](https://www.miit.gov.cn/jgsj/xgj/gzdt/art/2021/art_4e535277ab4343ee9010dbbaf90aab64.html)，工业和信息化部，访问于 2026-07-22。
- [《App违法违规收集使用个人信息行为认定方法》](https://www.cac.gov.cn/2019-12/27/c_1578986455686625.htm)，国家互联网信息办公室，访问于 2026-07-22。
- [2025 年 App 与 SDK 个人信息保护执法通报](https://www.cac.gov.cn/2025-05/06/c_1748239411359045.htm)，国家互联网信息办公室，访问于 2026-07-22。
- [《个人信息保护合规审计管理办法》](https://www.cac.gov.cn/2025-02/14/c_1741233507681519.htm)，国家互联网信息办公室，访问于 2026-07-22。
- [《互联网应用程序个人信息收集使用规定（征求意见稿）》](https://www.cac.gov.cn/2026-01/10/c_1769603446094128.htm)，国家互联网信息办公室，访问于 2026-07-22；仅作趋势参考。
- [App Review Guidelines §5.1](https://developer.apple.com/app-store/review/guidelines/)，Apple，访问于 2026-07-22。
- [App Privacy Details](https://developer.apple.com/app-store/app-privacy-details/)，Apple，访问于 2026-07-22。
- [Upcoming third-party SDK requirements](https://developer.apple.com/support/third-party-SDK-requirements/)，Apple，访问于 2026-07-22。
- [Adding a privacy manifest to your app or third-party SDK](https://developer.apple.com/documentation/bundleresources/adding-a-privacy-manifest-to-your-app-or-third-party-sdk)，Apple，访问于 2026-07-22。
- [友盟隐私政策](https://www.umeng.com/page/policy/)，友盟，访问于 2026-07-22。
- [友盟开发者中心](https://devs.umeng.com/)，友盟，访问于 2026-07-22。
- [支付宝 SDK 说明文档](https://render.alipay.com/p/c/17mdvjx9ata8)与[向第三方共享个人信息的情况说明](https://render.alipay.com/p/c/18qd2eli72kg)，访问于 2026-07-22；仅作为行业分层披露示例。
