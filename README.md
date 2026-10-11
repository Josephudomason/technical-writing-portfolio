| Field | Details |
| --- | --- |
| Title | Technical Writing Portfolio Documentation Library |
| Description | A professional Markdown documentation library covering beginner programming, React, mobile development, tools, APIs, troubleshooting, product docs, and technical concepts. |
| Category | Documentation Library |
| Audience | Beginner and junior developers |
| Difficulty | Beginner |

# Technical Writing Portfolio Documentation Library

This library collects practical developer documentation for people learning modern web and mobile development. It includes tutorials, concept explainers, troubleshooting guides, a fictional REST API reference, and fictional product documentation.

## Target Audience

- Beginner developers
- Junior developers
- Developers transitioning into a new technology
- Technical users who need clear product instructions

## Folder Structure

```text
docs/
+-- 01-beginner-programming/
+-- 02-react-nextjs/
+-- 03-react-native-mobile/
+-- 04-developer-tools/
+-- 05-api-documentation/
+-- 06-troubleshooting/
+-- 07-product-documentation/
+-- 08-technical-concepts/
```

## How Articles Are Organized

Each article is an individual Markdown file with front matter, a clear title, practical examples, common mistakes, and further reading where useful. The structure is consistent enough to scan, but each page should still be edited for the needs of its topic.

## Major Sections

- [Beginner Programming](01-beginner-programming/what-is-javascript-and-how-does-it-work.md)
- [React / Next.js](02-react-nextjs/how-react-components-work.md)
- [React Native / Mobile](03-react-native-mobile/getting-started-with-react-native.md)
- [Developer Tools](04-developer-tools/git-and-github-beginners-guide.md)
- [Fictional User API](05-api-documentation/fictional-user-api/README.md)
- [Troubleshooting](06-troubleshooting/react-app-wont-start.md)
- [Fictional Banking App Documentation](07-product-documentation/banking-app/README.md)
- [Technical Concepts](08-technical-concepts/what-is-an-api.md)
- [Master Content Index](content-index.md)

## How to Contribute

1. Create one Markdown file per topic.
2. Use lowercase kebab-case filenames.
3. Include front matter with title, description, category, audience, and difficulty.
4. Prefer official documentation for technical references.
5. Add internal links only to files that exist.
6. Check links, code fences, headings, and examples before publishing changes.

## Writing Standards

- Write directly and avoid filler.
- Define unfamiliar terms before using them heavily.
- Use realistic examples.
- Keep headings descriptive.
- Prefer practical guidance over abstract explanation.

## Technical Standards

- Use current framework conventions.
- Do not present deprecated APIs as current.
- Check commands, imports, filenames, and environment variables.
- Label fictional APIs and products clearly.
- Use official references in Further Reading sections.

