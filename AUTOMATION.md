# 🤖 YIP Automation & AI Agents Guide

This document explains how to use the AI agents and automation workflows in your YIP project.

## Table of Contents
1. [Overview](#overview)
2. [GitHub Actions Workflows](#github-actions-workflows)
3. [Project Management](#project-management)
4. [Discord Integration](#discord-integration)
5. [Content Generation](#content-generation)
6. [Troubleshooting](#troubleshooting)

---

## Overview

Your YIP project now includes **4 major automation workflows**:

| Workflow | Trigger | Purpose |
|----------|---------|---------|
| **Auto Deploy** | Push to main | Auto-deploy site to GitHub Pages |
| **Content Generator** | Manual trigger | AI-powered content creation |
| **Issue Management** | New issues/PRs | Smart labeling & responses |
| **Discord Notifications** | Any event | Real-time Discord updates |

---

## GitHub Actions Workflows

### 1. 🚀 Auto Deploy Workflow
**File:** `.github/workflows/auto-deploy.yml`

**What it does:**
- Validates HTML on every push
- Deploys to GitHub Pages automatically
- Sends Discord notification on success
- Runs on every push to `main` branch

**Trigger:** Automatic (push to main)

**Output:** Website live at https://theyoungindiaparty.github.io

```bash
# To trigger:
git push origin main
# Check Actions tab to see deployment progress
```

---

### 2. ✨ AI Content Generator Workflow
**File:** `.github/workflows/content-generator.yml`

**What it does:**
- Generates social media content
- Creates newsletter templates
- Writes blog post outlines
- Generates announcements
- Creates PRs with generated content

**How to use:**

#### Option A: GitHub UI
1. Go to **Actions** tab
2. Click **AI-Powered Content Generator**
3. Click **Run workflow**
4. Select content type:
   - `social-media` - Instagram, Twitter, LinkedIn
   - `newsletter` - Email newsletter
   - `blog-post` - Blog article template
   - `announcement` - Press releases
5. Click **Run workflow** again
6. Review generated content in new PR

#### Option B: Using `gh` CLI
```bash
gh workflow run content-generator.yml \
  -f content_type=social-media
```

**Generated Content:**
- Social media captions with hashtags
- Newsletter templates
- Blog post outlines
- Announcement templates

**Next Step:**
- Review PR with generated content
- Customize and make it yours
- Merge when ready

---

### 3. 🐛 Smart Issue Management Workflow
**File:** `.github/workflows/issue-management.yml`

**What it does:**
- Auto-labels new issues (bug, enhancement, documentation)
- Welcomes new contributors
- Sizes PRs automatically
- Requests reviews on PRs
- Adds helpful checklist comments

**Automatic triggers:**
- New issue opened → Auto-labels & welcomes
- PR opened → Labels by size, adds checklist
- Labels applied → Categorizes automatically

**Label System:**
- `bug` - Issues with bugs
- `enhancement` - Feature requests
- `documentation` - Doc updates
- `community` - Community-related
- `size/small` - < 100 additions
- `size/medium` - 100-500 additions
- `size/large` - > 500 additions

**Example:**
```
Issue Title: "Bug: Footer Discord link not working"
↓
Auto-labeled as: bug, community
↓
Automatic welcome comment posted
```

---

### 4. 💬 Discord Notifications Workflow
**File:** `.github/workflows/discord-notifications.yml`

**What it does:**
- Notifies Discord on new commits
- Alerts on new PRs
- Announces merged PRs
- Reports new issues
- Announces releases

**Events monitored:**
- ✅ Push to main
- 🔄 New PR opened
- ✅ PR merged/closed
- 🐛 New issue
- 🎉 New release

**Setup required:**
1. Create Discord webhook:
   - Go to Discord server
   - Server Settings → Webhooks
   - New Webhook → Copy URL
2. Add to GitHub secrets:
   - Repo Settings → Secrets → New secret
   - Name: `DISCORD_WEBHOOK_URL`
   - Value: Paste webhook URL

**Discord Message Example:**
```
🚀 New Commit to Main
Commit: feat: Add AI content generator
Author: Your Name
View: [GitHub Link]
```

---

## Project Management

### Issue Management System

**When you open an issue:**
1. Title gets analyzed
2. Appropriate labels auto-applied
3. Welcome message posted
4. Team gets notified

**Best practices:**
```
✅ Good title: "Bug: Homepage image not loading on mobile"
❌ Poor title: "Something broken"

✅ Good issue: Includes steps to reproduce
❌ Poor issue: "It doesn't work"
```

### PR Management System

**When you create a PR:**
1. Size automatically calculated
2. Review checklist posted
3. Contributors welcomed
4. Auto-labeled by changes

**PR labels:**
- `size/small` - Quick changes
- `size/medium` - Standard changes
- `size/large` - Major changes

---

## Discord Integration

### Setting up Discord Notifications

**Step 1: Create Webhook**
```
Discord Server → Right-click channel → Edit → Integrations → Webhooks
→ New Webhook → Copy URL
```

**Step 2: Add to GitHub**
```
GitHub Repo → Settings → Secrets & variables → Actions
→ New repository secret
→ Name: DISCORD_WEBHOOK_URL
→ Paste webhook URL
```

**Step 3: Test**
```bash
git push origin main
# Check Discord for notification
```

### Discord Message Types

| Event | Message | Color |
|-------|---------|-------|
| Push to main | 📝 New Commit | Green |
| PR opened | 🔄 New PR | Blue |
| PR merged | ✅ PR Merged | Green |
| PR closed | ❌ PR Closed | Red |
| New issue | 🐛 New Issue | Orange |
| Release | 🎉 New Release | Purple |

---

## Content Generation

### Social Media Content

**Generate with:**
1. Go to Actions → AI-Powered Content Generator
2. Select `social-media`
3. Run workflow

**Generated for:**
- 📷 Instagram (caption + hashtags)
- 🐦 Twitter/X (short, engaging)
- 💼 LinkedIn (professional)

**Customization:**
- Edit in PR before merging
- Add images/videos
- Schedule on social platforms
- Track engagement

### Newsletter Content

**Generated sections:**
- Weekly movement updates
- Member spotlights
- Upcoming events
- Call to action

**Use with:**
- Mailchimp
- ConvertKit
- Substack
- Custom email service

### Blog Posts

**Generated:**
- Title ideas
- Outline structure
- Hook starters
- CTA templates

**Topics covered:**
- Youth movements
- Political change
- Education reform
- Justice & equality

### Announcements

**Generated:**
- Major announcements
- Key points
- Link to 5 demands
- Call to action

---

## Workflow Triggers Reference

### Manual Triggers (in GitHub Actions UI)

```
Repository → Actions tab → Select workflow → Run workflow
```

### Automatic Triggers

```
Push to main → Auto-deploy
New issue → Auto-label & respond
New PR → Auto-label & request review
Merge PR → Discord notification
Push tag → Release notification
```

### CLI Triggers

```bash
# List all workflows
gh workflow list

# Run specific workflow
gh workflow run auto-deploy.yml
gh workflow run content-generator.yml -f content_type=social-media
gh workflow run issue-management.yml

# View workflow run
gh run view [run-id]

# View workflow logs
gh run view [run-id] --log
```

---

## Troubleshooting

### Discord Webhook Not Working

**Problem:** No Discord notifications appearing

**Solution:**
1. Check webhook URL is correct
2. Verify secret is added as `DISCORD_WEBHOOK_URL`
3. Test webhook manually:
   ```bash
   curl -X POST https://discord.com/api/webhooks/YOUR/WEBHOOK \
     -H "Content-Type: application/json" \
     -d '{"content":"Test message"}'
   ```
4. Check Discord channel permissions

### Content Not Generating

**Problem:** Workflow runs but no PR created

**Solution:**
1. Check workflow logs in Actions tab
2. Verify `peter-evans/create-pull-request` action
3. Check GitHub token permissions
4. Ensure branch name is valid

### Issues Not Auto-Labeling

**Problem:** New issues don't get labeled

**Solution:**
1. Check issue management workflow enabled
2. Verify issue title includes keywords (bug, feature, docs)
3. Check GitHub Actions permissions
4. Review workflow logs

### Deployment Failing

**Problem:** Site not deploying to GitHub Pages

**Solution:**
1. Check HTML validation passes
2. Verify `index.html` exists
3. Check GitHub Pages settings:
   - Settings → Pages → Source: Deploy from branch
   - Branch: main, folder: / (root)
4. Review auto-deploy workflow logs

---

## Advanced Configuration

### Adding More Workflows

Create new workflow in `.github/workflows/custom.yml`:

```yaml
name: Custom Workflow
on:
  push:
    branches: [main]

jobs:
  custom-job:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Your custom step
        run: echo "Hello YIP!"
```

### Environment Variables

Add in GitHub Actions:
```
Repo → Settings → Environments
→ Create production environment
→ Add environment variables
```

### Secrets Management

```bash
# Add secret via CLI
gh secret set DISCORD_WEBHOOK_URL --body "[your-webhook-url]"

# List secrets
gh secret list

# Delete secret
gh secret delete DISCORD_WEBHOOK_URL
```

---

## Best Practices

✅ **DO:**
- Review auto-generated content before merging
- Test workflows on feature branches first
- Keep Discord webhooks secure
- Document custom workflows
- Monitor workflow logs regularly

❌ **DON'T:**
- Commit secrets to repository
- Disable workflows without reason
- Ignore workflow failures
- Create duplicate workflows
- Share webhook URLs publicly

---

## Support

**Need help?**
- 💬 Discord: https://discord.gg/U9wXW249t
- 📝 GitHub Issues: [Create issue](https://github.com/theyoungindiaparty/theyoungindiaparty.github.io/issues)
- 📖 GitHub Docs: [Actions documentation](https://docs.github.com/en/actions)

---

**Made by Indian youth. Trying to fix what adults normalized.** 🇮🇳
