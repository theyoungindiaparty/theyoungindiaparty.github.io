# 🤝 Contributing to The Young India Party

Thank you for your interest in contributing to YIP! We welcome contributions from everyone.

## Table of Contents
- [Getting Started](#getting-started)
- [How to Contribute](#how-to-contribute)
- [Development Guidelines](#development-guidelines)
- [Submitting Changes](#submitting-changes)
- [Code of Conduct](#code-of-conduct)

---

## Getting Started

### 1. Fork & Clone
```bash
# Fork the repository on GitHub
# Clone your fork
git clone https://github.com/YOUR_USERNAME/theyoungindiaparty.github.io.git
cd theyoungindiaparty.github.io

# Add upstream remote
git remote add upstream https://github.com/theyoungindiaparty/theyoungindiaparty.github.io.git
```

### 2. Create a Branch
```bash
# Update your local repository
git fetch upstream
git checkout main
git merge upstream/main

# Create a feature branch
git checkout -b feature/your-feature-name
# or
git checkout -b fix/issue-description
# or
git checkout -b docs/what-you-documented
```

### 3. Set Up
No special setup needed! Just edit files directly.

---

## How to Contribute

### Types of Contributions

#### 🐛 Bug Reports
- Open an issue with "Bug:" in the title
- Describe the issue clearly
- Include steps to reproduce
- System/browser information

#### ✨ Feature Requests
- Open an issue with "Feature:" in the title
- Explain the feature and why it's needed
- Provide examples if possible
- Link related issues

#### 📝 Documentation
- Update README, guides, or docs
- Fix typos and improve clarity
- Add examples and tutorials
- Create guides for new features

#### 💻 Code Changes
- Website improvements
- Performance optimizations
- Accessibility enhancements
- Bug fixes

#### 📢 Content
- Social media posts
- Newsletter content
- Blog articles
- Announcements

---

## Development Guidelines

### HTML/CSS Standards
- Use semantic HTML
- Follow existing code style
- Mobile-first responsive design
- Accessibility first (WCAG 2.1 AA)
- Comment complex code

### Best Practices
- ✅ Keep changes focused
- ✅ One feature per branch
- ✅ Test in browser
- ✅ No console errors/warnings
- ✅ Meaningful commit messages

### Commit Message Format
```
type(scope): subject

body

footer
```

**Types:**
- `feat` - New feature
- `fix` - Bug fix
- `docs` - Documentation
- `style` - Formatting (no logic change)
- `refactor` - Code restructuring
- `perf` - Performance improvement
- `test` - Tests
- `chore` - Build/tooling changes

**Examples:**
```
feat(hero): add animated background
fix(footer): correct discord link
docs(automation): add workflow guide
```

### Naming Conventions
- Branches: `feature/add-newsletter` or `fix/broken-link`
- PRs: Clear, descriptive titles
- Issues: Specific and actionable

---

## Submitting Changes

### 1. Make Your Changes
```bash
# Edit files
nano index.html
# or use your editor
```

### 2. Commit & Push
```bash
# Stage changes
git add .

# Commit with message
git commit -m "feat(section): add amazing feature"

# Push to your fork
git push origin feature/your-feature-name
```

### 3. Create Pull Request
- Go to GitHub
- Click "Compare & pull request"
- Fill in PR title and description
- Reference related issues: "Closes #123"
- Submit!

### 4. PR Description Template
```markdown
## Description
What does this PR do?

## Related Issues
Closes #(issue number)

## Changes Made
- Change 1
- Change 2
- Change 3

## Testing
How to test these changes:
1. Step 1
2. Step 2
3. Step 3

## Screenshots (if applicable)
[Add screenshots]

## Checklist
- [ ] My code follows the style guidelines
- [ ] I have updated documentation
- [ ] My changes generate no new warnings
- [ ] I have tested locally
```

### 5. Review Process
- Automated checks run
- Team reviews your code
- Respond to feedback
- Make requested changes
- Celebrate when merged! 🎉

---

## Our Automated Workflow

### Auto-Labeling
Issues & PRs automatically get labeled:
- `bug` - Bug reports
- `feature` - Feature requests
- `documentation` - Doc updates
- `size/small` - < 100 changes
- `size/medium` - 100-500 changes
- `size/large` - > 500 changes

### Auto-Deployment
- Push to `main` → Auto-deployed to GitHub Pages
- Updates live at https://theyoungindiaparty.github.io
- Discord notification sent

### Auto-Checks
- HTML validation
- Broken link detection
- Format checking

---

## Code of Conduct

### Our Values
✅ Respectful & inclusive
✅ Youth-focused
✅ Merit-based
✅ Transparent
✅ Accountability

### Be Respectful
- Treat everyone with respect
- Assume good intentions
- Provide constructive feedback
- Welcome diverse perspectives

### No Tolerance For
❌ Harassment or discrimination
❌ Spam or trolling
❌ Personal attacks
❌ Copyright violations
❌ Malicious code

### Reporting Issues
Email: [contact email] or report via Discord

---

## Resources

### Documentation
- [AUTOMATION.md](AUTOMATION.md) - Automation workflows
- [index.html](index.html) - Main website
- [GitHub Docs](https://docs.github.com)

### Tools
- [GitHub Desktop](https://desktop.github.com) - Git GUI
- [VSCode](https://code.visualstudio.com) - Editor
- [Discord](https://discord.gg/U9wXW249t) - Community

### Community
- 💬 [Discord](https://discord.gg/U9wXW249t) - Live chat
- 📝 [Issues](https://github.com/theyoungindiaparty/theyoungindiaparty.github.io/issues) - Discussions
- 📧 Email for questions

---

## Questions?

### Ask On:
- 💬 [Discord Community](https://discord.gg/U9wXW249t)
- 📝 [GitHub Discussions](https://github.com/theyoungindiaparty/theyoungindiaparty.github.io/discussions)
- 📧 Contact us via issues

---

## Thank You! 🇮🇳

We appreciate every contribution. Together, we're building the future India deserves.

**Made by Indian youth. Trying to fix what adults normalized.**
