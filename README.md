# Xuyutech Legal Documents

Welcome to the Xuyutech Legal Documents repository. This centralized hub stores all legal documents for our products, including Privacy Policies, Terms of Service, and FAQs, organized by product, platform, region, and language.

[简体中文](README.zh-cn.md)

## Quick Navigation

- [Privacy Policies](#privacy-policies)
- [Terms of Service](#terms-of-service)
- [Frequently Asked Questions](#frequently-asked-questions)
- [Documentation](#additional-documentation)
- [How to Contribute](#how-to-contribute)

## Repository Structure

```
xuyutech-legal-docs/
├── README.md                    # English documentation
├── README.zh-cn.md              # Simplified Chinese documentation
├── LICENSE                      # Open source license (if applicable)
├── .gitignore                   # Git ignore rules
│
├── products/                    # Product-specific legal documents
│   ├── Subs Manager iOS/
│   │   ├── privacy-policy/      # Privacy policies by region
│   │   ├── terms-of-service/    # Terms of service by region
│   │   └── qa/                  # FAQs by region
│   │
│   └── Subs Manager Android/
│       ├── privacy-policy/
│       ├── terms-of-service/
│       └── qa/
│
└── docs/                        # Supplementary documentation
    ├── compliance.md            # Compliance guidelines
    ├── faq.md                   # General FAQs
    └── legal-notices.md         # Legal notices
```

## Document Categories

### Privacy Policies

Privacy policies are stored under `products/[Product]/privacy-policy/[Region]/` and available in multiple languages:

| Region | Folder | Languages |
|--------|--------|-----------|
| United States | `us/` | English (`en.md`), Spanish (`es.md`) |
| China | `cn/` | Chinese (`zh-cn.md`), English (`en.md`) |
| Spain | `es/` | Spanish (`es.md`), English (`en.md`) |

Example path: `products/Subs Manager iOS/privacy-policy/us/en.md`

### Terms of Service

Terms of Service documents are organized in `products/[Product]/terms-of-service/[Region]/` following the same language structure as privacy policies.

### Frequently Asked Questions

FAQs are available in `products/[Product]/qa/[Region]/` to help users understand our policies and legal terms.

## Language Support

Each region supports multiple language versions. Legal documents use the following naming convention:

- **English (US)**: `en.md`
- **Chinese (Simplified)**: `zh-cn.md`
- **Spanish**: `es.md`
- **Other languages**: ISO 639-1 language codes

## Additional Documentation

The `docs/` directory contains supplementary materials:

| File | Description |
|------|-------------|
| [docs/compliance.md](docs/compliance.md) | Data protection compliance information (GDPR, CCPA, PIPL) |
| [docs/faq.md](docs/faq.md) | General questions about our legal documents |
| [docs/legal-notices.md](docs/legal-notices.md) | Important legal notices and disclaimers |

## How to Use This Repository

### Finding a Document

1. Navigate to the `products/` directory
2. Select your product and platform
3. Choose the document type (privacy policy, terms of service, or QA)
4. Select your region and preferred language

### Example: Finding Subs Manager iOS Privacy Policy (US English)

```
products/ → Subs Manager iOS/ → privacy-policy/ → us/ → en.md
```

## How to Contribute

We welcome contributions from the community. Please follow these guidelines:

1. **Fork this repository** and create a feature branch
2. **Make your changes** following our [document structure](#repository-structure)
3. **Submit a Pull Request** with a clear description of your updates
4. **Ensure compliance**: All changes must be reviewed by at least one team member

### Contribution Requirements

- Follow the [document naming conventions](#language-support)
- Include both English and local language versions when adding new regions
- Update the relevant documentation in `docs/` if needed
- Provide detailed commit messages explaining your changes

## Legal Compliance

This repository maintains legal documents compliant with:

- **GDPR** - General Data Protection Regulation (EU)
- **CCPA** - California Consumer Privacy Act (US)
- **PIPL** - Personal Information Protection Law (China)
- **Other applicable data protection regulations**

For detailed compliance information, see [docs/compliance.md](docs/compliance.md).

## Contact

For questions about our legal documents or to report issues, please contact:

- **Email**: [legal@xuyutech.com](mailto:legal@xuyutech.com)
- **Issues**: Submit via GitHub Issues

## License

This repository is proprietary to Xuyutech. Please contact us for licensing inquiries.
