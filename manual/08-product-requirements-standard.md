# 08. Product Requirements Standard

**Part II** · Owns: product vision, problem, users, goals, non-goals, product requirements, constraints, success measures, avoiding technical leakage, relationship to specifications.

## 8.1 Artifacts

| Artifact | Path | Template |
|---|---|---|
| Product vision | `docs/product/vision.md` | `docs/product/vision-template.md` |
| Product requirements | `docs/product/requirements.md` | `docs/product/requirements-template.md` |

Create the actual artifacts from the templates; never leave project requirements only in a template.

## 8.2 Vision content

Problem statement · target users and their context · value proposition · goals · non-goals · guiding principles · constraints · success measures · time horizon. The vision changes rarely and by owner approval.

## 8.3 Product requirements content

- Product-level requirements stated as outcomes and capabilities (`PR-NNN` local labels are permitted inside the document for reference; they are not governed identifiers).
- User groups and key journeys.
- Constraints (regulatory, budget, platform, hosting, privacy).
- Explicit non-goals.
- Success measures that can be observed.
- Open questions and their owner.

## 8.4 Avoiding technical leakage

Product documents do not prescribe frameworks, databases, APIs, or internal architecture unless the technology is itself a product constraint (for example, "must run on the existing self-hosted platform"). Technical choices belong in plans and ADRs.

## 8.5 Relationship to specifications

Specifications cite the product requirement they serve. Product requirements do not contain acceptance criteria for features; those belong in the specification. A specification that conflicts with product requirements is escalated to the owner before approval.

## 8.6 Review

Use prompt [05](../prompts/05-product-requirements-review.md). Product intent approval is the second gate in [chapter 26](26-validation-and-quality-gates.md).
