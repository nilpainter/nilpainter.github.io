# Integrating Cusdis Comments

## Steps to Enable Cusdis

### 1. Get your Cusdis App ID

1. Go to https://cusdis.com and sign up
2. Create a new site/app in your dashboard
3. Copy your **App ID**

### 2. Configure Hugo

I've already added the Cusdis configuration to your `config/_default/params.toml`.

**You need to replace `YOUR_CUSDIS_APP_ID` with your actual App ID:**

```toml
[comments.cusdis]
  host = "https://cusdis.com"
  appId = "YOUR_ACTUAL_APP_ID_HERE"
```

### 3. Enable Comments on Specific Posts

You can control comments per post by adding to the front matter:

```markdown
---
title: "My Post"
date: 2026-01-17
showComments: true  # Enable for this post
---
```

Or disable for specific posts:

```markdown
---
title: "My Post"
showComments: false  # Disable for this post
---
```

### 4. Deploy

```bash
git add config/_default/params.toml
git commit -m "Add Cusdis comments integration"
git push
```

Comments will appear at the bottom of blog posts after deployment!

## Self-Hosted Cusdis (Optional)

If you're self-hosting Cusdis, change the host URL:

```toml
[comments.cusdis]
  host = "https://your-cusdis-instance.com"
  appId = "your-app-id"
```

## Styling Comments

The comments will automatically match your site's cream background and elegant typography through the Blowfish theme integration.

## Moderating Comments

Log into your Cusdis dashboard at https://cusdis.com to:
- Approve/delete comments
- Get email notifications
- See comment statistics
- Manage spam

