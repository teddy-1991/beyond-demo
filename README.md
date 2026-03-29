# Beyond Group AI Assistant — Deployment Guide

## Vercel Environment Variables

Go to Vercel Dashboard → Your Project → Settings → Environment Variables
Add these:

| Variable Name          | Value                        |
|------------------------|------------------------------|
| ANTHROPIC_API_KEY      | sk-ant-...                   |
| EMAILJS_SERVICE_ID     | service_udemcgu              |
| EMAILJS_TEMPLATE_ID    | template_xxxxxxx             |
| EMAILJS_PUBLIC_KEY     | your emailjs public key      |
| EMAILJS_PRIVATE_KEY    | your emailjs private key     |
| RECIPIENT_EMAIL        | yongin016@gmail.com          |

## File Structure

```
beyond-group-demo/
├── api/
│   ├── chat.js          ← Claude API (reads ANTHROPIC_API_KEY)
│   └── send-email.js    ← EmailJS API (reads EMAILJS_* keys)
├── index.html           ← Frontend (no keys, calls /api/*)
└── README.md
```

## Deploy Steps

1. Push this folder to GitHub (public repo is fine — no keys in code)
2. Go to vercel.com → Add New Project → Import GitHub repo
3. Add all environment variables above
4. Deploy → get your live URL
5. Send URL to Curt at curt@beyondfoam.ca with subject: "I did my homework"

## EmailJS Private Key

Find it at: emailjs.com → Account → General → API Keys → Private Key
This is needed for server-side sending (different from the public key).
