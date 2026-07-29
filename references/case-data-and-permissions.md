# Case Data and Permission Reference

Use this reference when reading a case repository, normalizing a case document, or deciding whether a visual may identify the customer.

## Source Model

Treat the repository as three linked layers:

1. **Customer profile**: stable customer identity, industry, market, account owner, official website, relationship status, and high-level permissions.
2. **Use case**: one business problem, workflow, solution, adoption pattern, and outcome. A customer may have multiple use cases.
3. **Usage record**: a specific reuse of a case in a pitch deck, website, event, speaker program, customer visit, or other channel.

Do not collapse multiple use cases into a single record merely because they belong to the same customer.

## Field Aliases

Field names vary by Base. Match semantically rather than requiring exact spelling.

### Identity

- Case ID / 案例ID
- Case title / 案例标题
- Linked customer / 关联客户
- Customer name / 客户名称 / 客户名称（提交）
- Market / 市场
- Industry / 一级行业 / 二级行业
- Official website / 官网

### Case facts

- Case summary / 案例简介
- Customer challenge / 客户挑战
- Lark solution / Lark解决方案
- Products / 产品能力
- Content theme / 内容主题
- Adoption / 使用范围 / Adoption
- Quantitative result / 量化结果
- Qualitative value / 业务价值
- Case link / 案例链接 / Source document

### AI facts

- Is AI use case / 是否AI应用
- AI workflow / AI工作流
- AI maturity / AI落地阶段
- AI result / AI成效

An AI tag alone is not proof of an AI workflow or result. Include AI in the visual only when the workflow and supporting fact are explicit.

### Reuse and fit

- Recommended use / 推荐用途
- Presales fit / 售前适配度
- Website fit / 官网适配度
- Speaker fit / Speaker适配度
- Customer-visit fit / 走进活动适配度
- Quality rating / 质量评级
- Review status / 审核状态

### Permissions

- Content usage scope / 内容使用范围
- Customer name and logo permission / 客户名称/Logo授权
- Business data permission / 业务数据授权
- Authorization status / 授权状态
- Authorization evidence / 授权凭证
- Expiry date / 授权有效期

## Permission Decision Table

| Content scope | Identity treatment | Metrics treatment | Required label | Allowed default output |
|---|---|---|---|---|
| Prohibited / 禁止使用 | Do not generate | Do not generate | N/A | Stop |
| Internal anonymous / 内部匿名 | Remove name, logo, location, and distinctive brand identifiers | Use only internally approved figures; generalize if required | `INTERNAL ONLY · ANONYMIZED` | Neutral internal visual |
| Internal named / 内部实名 | Name allowed internally; logo requires separate approval | Use only approved internal figures | `INTERNAL ONLY` | Brand-inspired internal visual |
| Public / 可公开 | Name allowed only when covered; logo still requires explicit approval | Include only figures covered by authorization or already public | `DRAFT` until publication review | Public-style draft |

Apply the most restrictive relevant field. For example, public content scope plus unapproved business data means the visual may identify the customer but must omit those metrics.

## Review Gate

Use only records that are sufficiently reviewed for their intended channel.

- Draft or pending review: internal draft only.
- Approved for internal reuse: internal channels only.
- Approved for external reuse: external draft is possible if permissions also pass.
- Rejected, expired, or revoked: stop or remove the affected identity/data.

## Fact Snapshot Template

Create this snapshot before writing an image prompt:

```text
Customer:
Industry / market:
Use case title:
Business context:
Challenge:
Lark solution:
Products used:
Adoption scope:
Verified metrics:
Verified qualitative outcomes:
Verified AI workflow:
Approved quote:
Content scope:
Name permission:
Logo permission:
Business-data permission:
Review status:
Intended channel:
Evidence links:
Excluded or uncertain claims:
```

Every metric should have an evidence link or a named source field. If no evidence is available, omit the metric from the image.
