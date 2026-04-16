# 🦦 OwO Reseller Bot — GitHub + Render Deployment Guide

---

## 📁 Files to upload to GitHub
```
bot.py            ← main bot
requirements.txt  ← python dependencies
render.yaml       ← render.com config
.gitignore        ← keeps db & secrets off GitHub
```

---

## 🐙 Step 1 — Upload to GitHub

1. Go to https://github.com → Sign in → Click "New repository"
2. Name it `owo-bot` → Set to **Private** ⚠️ (important!)
3. Click "Create repository"
4. Click "uploading an existing file"
5. Drag and drop all 4 files → Click "Commit changes"

---

## 🚀 Step 2 — Deploy on Render.com

1. Go to https://render.com → Sign in with GitHub
2. Click "New +" → Select "Blueprint"
3. Connect your GitHub repo (owo-bot)
4. Render detects render.yaml automatically

### Set Environment Variables (Render Dashboard → Environment tab):

| Key             | Value                          |
|-----------------|--------------------------------|
| BOT_TOKEN       | Your Discord bot token         |
| OWNER_ID        | Your Discord user ID (numbers) |
| OWO_CHANNEL_ID  | Channel ID for owo commands    |

5. Click "Save Changes" → Render auto-deploys ✅

---

## ⚠️ Important Notes

- ALWAYS keep your GitHub repo PRIVATE — never expose tokens
- .gitignore excludes accounts.db and .env automatically
- Render free tier may reset the DB on restart — use Render Persistent Disk or Supabase for permanent storage
