# Contributing to Awesome Security Tools

Thank you for your interest in contributing to this curated list of security tools! This project thrives on community contributions and we welcome your input.

## Table of Contents

- [How to Contribute](#how-to-contribute)
- [Contribution Guidelines](#contribution-guidelines)
- [Quality Standards](#quality-standards)
- [Formatting Guidelines](#formatting-guidelines)
- [Pull Request Process](#pull-request-process)
- [What to Contribute](#what-to-contribute)
- [Code of Conduct](#code-of-conduct)

---

## How to Contribute

There are several ways to contribute:

1. **Add new security tools** - Submit tools that fit our quality criteria
2. **Update existing entries** - Fix outdated information, broken links, or improve descriptions
3. **Report issues** - Found a broken link or outdated info? Open an issue
4. **Improve descriptions** - Make tool descriptions more accurate or helpful
5. **Suggest new categories** - Propose new sections for emerging security domains
6. **Fix typos and formatting** - Even small improvements matter

---

## Contribution Guidelines

### Before Submitting

- **Search first**: Check if the tool is already listed
- **One tool per PR**: Submit separate pull requests for each tool
- **Test the tool**: Ensure you've actually used or thoroughly researched the tool
- **Check the link**: Verify all URLs work correctly
- **Read existing entries**: Follow the established format and style

### What Makes a Good Contribution

✅ **Good:**
- Well-established tools with active development
- Tools with clear documentation and real-world usage
- Open-source tools with significant community adoption
- Commercial tools that are industry standards
- Emerging tools solving real security problems

❌ **Not Suitable:**
- Your own tool without significant traction (wait for community adoption)
- Abandoned projects (no updates in 2+ years without good reason)
- Tools with no documentation or unclear purpose
- Duplicate functionality without clear differentiation
- Tools with known security issues or malicious intent

---

## Quality Standards

All tools must meet these criteria:

### Minimum Requirements

1. **Actively Maintained**: Updated within the last 12 months OR widely used stable tool
2. **Clear Purpose**: Solves a specific security problem
3. **Documentation**: Has README, documentation, or clear usage instructions
4. **Legitimate**: Not malware, not a scam, has verifiable reputation
5. **Accessible**: Publicly available (open-source or commercial with trial)

### Additional Criteria (Preferred)

- GitHub stars (for open-source): 500+ preferred, 100+ minimum
- Community adoption: Used by known organizations or has case studies
- Quality indicators: Regular releases, issue resolution, active community
- Professional presentation: Website, logo, clear branding

---

## Formatting Guidelines

### Tool Entry Format

Each tool entry should follow this structure:

```markdown
- **[Tool Name](https://tool-url.com/)** - Brief description (1-3 sentences). Key features in concise format. Use case or target audience. Notable users or adoption statistics if available. Pricing model if relevant (open-source, free tier, commercial).
```

### Writing Style

**Description Guidelines:**
- **First sentence**: What the tool does and its primary purpose
- **Second sentence**: Key features, capabilities, or differentiators  
- **Third sentence**: Target audience, use case, or adoption info
- **Length**: 50-150 words (aim for ~100 words like existing entries)
- **Tone**: Professional, factual, informative
- **Avoid**: Marketing hype, excessive adjectives, sales language

**Good Example:**
```markdown
- **[Semgrep](https://semgrep.dev/)** - Fast, lightweight static analysis tool that finds bugs and enforces code standards. Supports 20+ languages with 2,000+ pre-built rules. YAML-based rules are easy to write and customize. Runs locally, in CI/CD, or as GitHub App. Open-source with commercial features. Used by Dropbox, Snowflake, and thousands of companies. Detects OWASP Top 10, CWE Top 25, and custom patterns. 10x faster than traditional SAST tools.
```

**Bad Example:**
```markdown
- **[SuperScannerPro](https://example.com/)** - The most amazing, revolutionary, and groundbreaking security scanner ever created! It's absolutely incredible and will change your life! Industry-leading performance! Best tool ever!
```

### Formatting Rules

- Use **bold** for tool names: `**[Tool Name](url)**`
- Include direct link to main website or GitHub repo
- Use sentence case for descriptions, not title case
- End descriptions with period
- Use proper spacing (see existing entries)
- Maintain alphabetical order within categories (unless there's a logical grouping)

### Link Guidelines

- **Primary link**: Main website or official GitHub repository
- **Prefer HTTPS**: Always use secure links
- **No affiliate links**: Direct links only
- **No URL shorteners**: Use full URLs
- **Verify links**: Ensure they work before submitting

---

## Pull Request Process

### Step-by-Step Guide

1. **Fork the repository**
   ```bash
   # Click "Fork" button on GitHub
   ```

2. **Clone your fork**
   ```bash
   git clone https://github.com/YOUR-USERNAME/awesome-security.git
   cd awesome-security
   ```

3. **Create a branch**
   ```bash
   git checkout -b add-tool-name
   ```

4. **Make your changes**
   - Add/update tool entries following the format above
   - Maintain consistent formatting with existing entries
   - Test all links

5. **Commit your changes**
   ```bash
   git add README.md
   git commit -m "Add [Tool Name] to [Category] section"
   ```

6. **Push to your fork**
   ```bash
   git push origin add-tool-name
   ```

7. **Submit a Pull Request**
   - Go to the original repository
   - Click "New Pull Request"
   - Select your branch
   - Fill out the PR template (see below)

### Pull Request Template

When submitting a PR, please include:

```markdown
## Tool Information

**Tool Name**: [Name]
**URL**: [Link]
**Category**: [Section name]

## Description

[Explain why this tool should be added]

## Checklist

- [ ] I have used or thoroughly researched this tool
- [ ] The tool is actively maintained or widely adopted
- [ ] I have verified all links work correctly
- [ ] I followed the formatting guidelines
- [ ] The tool fits the quality standards
- [ ] This is not a duplicate entry
- [ ] I am not the tool author (or disclosed if I am)

## Additional Context

[Any other relevant information]
```

### Review Process

- Maintainers will review your PR within 7 days
- We may request changes or ask questions
- Once approved, your contribution will be merged
- You'll be credited as a contributor

---

## What to Contribute

### High-Priority Contributions

We especially welcome:

- **New tools in emerging areas**: Zero Trust, Supply Chain Security, Cloud-Native Security
- **Updates to outdated entries**: Version changes, new features, broken links
- **Missing industry-standard tools**: Widely-used tools we've overlooked
- **Better descriptions**: More accurate or informative tool descriptions
- **New categories**: Propose sections for important security domains we're missing

### Types of Updates

**Adding New Tools:**
- Find the appropriate category or suggest a new one
- Follow formatting guidelines exactly
- Provide comprehensive but concise description

**Updating Existing Entries:**
- Fix broken or redirected links
- Update descriptions with new features
- Correct inaccurate information
- Add missing important details

**Improving Organization:**
- Suggest better categorization
- Propose new subcategories
- Improve section descriptions

---

## Code of Conduct

### Our Standards

- **Be respectful**: Treat all contributors with respect
- **Be constructive**: Provide helpful feedback, not just criticism
- **Be collaborative**: Work together to improve the list
- **Be honest**: Disclose conflicts of interest (e.g., if you created the tool)
- **Be patient**: Maintainers are volunteers

### Unacceptable Behavior

- Harassment, discrimination, or offensive comments
- Spam or repeated self-promotion
- Intentionally misleading or false information
- Plagiarism or copyright violation

### Conflict of Interest

If you are:
- The author/maintainer of the tool being submitted
- Employed by the company behind the tool
- Financially benefiting from the tool

Please disclose this in your PR. This doesn't automatically disqualify the submission, but transparency is important.

---

## Questions?

- **General questions**: Open a GitHub issue with the `question` label
- **Major changes**: Discuss in an issue before submitting PR
- **Security concerns**: Report security issues responsibly (see SECURITY.md)

---

## Recognition

Contributors are recognized in the following ways:

- Your GitHub profile appears in the repository's contributors list
- Significant contributions may be highlighted in release notes
- Regular contributors may be invited to become maintainers

---

## License

By contributing, you agree that your contributions will be licensed under the same license as the project (see LICENSE file).

---

## Getting Help

Need help contributing? Here are some resources:

- [GitHub Pull Request Tutorial](https://docs.github.com/en/pull-requests)
- [Markdown Guide](https://www.markdownguide.org/)
- [Awesome List Guidelines](https://github.com/sindresorhus/awesome/blob/main/contributing.md)

---

**Thank you for contributing to Awesome Security Tools!** 🔒

Your contributions help the security community discover and adopt better tools, making the internet safer for everyone.
