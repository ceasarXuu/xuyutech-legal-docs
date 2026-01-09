# Xuyutech 法律文档

欢迎访问 Xuyutech 法律文档仓库。本仓库集中存储了所有产品的法律文件，包括隐私政策、服务条款和常见问题，按照产品、平台、地区和语言进行组织。

[English](README.md)

## 快速导航

- [隐私政策](#隐私政策)
- [服务条款](#服务条款)
- [常见问题](#常见问题)
- [附加文档](#附加文档)

## 仓库结构

```
xuyutech-legal-docs/
├── README.md                    # 英文文档
├── README.zh-cn.md              # 简体中文文档
├── LICENSE                      # 开源许可证（如适用）
├── .gitignore                   # Git 忽略规则
│
├── products/                    # 产品法律文档
│   ├── Subs Manager iOS/
│   │   ├── privacy-policy/      # 按地区分类的隐私政策
│   │   ├── terms-of-service/    # 按地区分类的服务条款
│   │   └── qa/                  # 按地区分类的常见问题
│   │
│   └── Subs Manager Android/
│       ├── privacy-policy/
│       ├── terms-of-service/
│       └── qa/
│
└── docs/                        # 附加文档
    ├── compliance.md            # 合规指南
    ├── faq.md                   # 常见问题解答
    └── legal-notices.md         # 法律声明
```

## 文档分类

### 隐私政策

隐私政策存储在 `products/[产品]/privacy-policy/[地区]/` 目录下，支持多种语言：

| 地区 | 文件夹 | 支持语言 |
|------|--------|----------|
| 美国 | `us/` | 英语 (`en.md`)、西班牙语 (`es.md`) |
| 中国 | `cn/` | 简体中文 (`zh-cn.md`)、英语 (`en.md`) |
| 西班牙 | `es/` | 西班牙语 (`es.md`)、英语 (`en.md`) |

示例路径：`products/Subs Manager iOS/privacy-policy/us/en.md`

### 服务条款

服务条款文档组织在 `products/[产品]/terms-of-service/[地区]/` 目录下，与隐私政策采用相同的语言结构。

### 常见问题

常见问题可在 `products/[产品]/qa/[地区]/` 中找到，帮助用户了解我们的政策和使用条款。

## 语言支持

每个地区支持多种语言版本。法律文档使用以下命名规范：

- **英语（美国）**: `en.md`
- **简体中文**: `zh-cn.md`
- **西班牙语**: `es.md`
- **其他语言**: ISO 639-1 语言代码

## 附加文档

`docs/` 目录包含补充材料：

| 文件 | 说明 |
|------|------|
| [docs/compliance.md](docs/compliance.md) | 数据保护合规信息（GDPR、CCPA、PIPL） |
| [docs/faq.md](docs/faq.md) | 关于法律文档的常见问题 |
| [docs/legal-notices.md](docs/legal-notices.md) | 重要法律声明和免责声明 |

## 如何使用本仓库

### 查找文档

1. 进入 `products/` 目录
2. 选择产品和平台
3. 选择文档类型（隐私政策、服务条款或常见问题）
4. 选择所在地区和首选语言

### 示例：查找 Subs Manager iOS 隐私政策（美国英语）

```
products/ → Subs Manager iOS/ → privacy-policy/ → us/ → en.md
```

## 法律合规

本仓库维护的法律文件符合以下法规：

- **GDPR** - 通用数据保护条例（欧盟）
- **CCPA** - 加州消费者隐私法案（美国）
- **PIPL** -个人信息保护法（中国）
- **其他适用的数据保护法规**

详细合规信息请参阅 [docs/compliance.md](docs/compliance.md)。

## 联系我们

如有关于法律文档的问题或需报告问题，请联系：

- **邮箱**: [datachewer@gmail.com](mailto:datachewer@gmail.com)

## 许可证

本仓库归 Xuyutech 所有。如需许可证咨询，请联系我们。
