# Deploy Sonic Reader to Vercel with Custom Domain

## Quick Deploy (5 minutes)

### Option 1: Vercel CLI (Fastest)

1. **Install Vercel CLI**
```bash
npm install -g vercel
```

2. **Deploy from the speedr-deploy folder**
```bash
cd speedr-deploy
vercel
```

3. **Follow prompts:**
   - Set up and deploy? **Y**
   - Which scope? Select your account
   - Link to existing project? **N**
   - What's your project's name? **sonic-reader**
   - In which directory is your code located? **./**
   - Want to modify settings? **N**

4. **Deploy to production**
```bash
vercel --prod
```

You'll get a URL like: `https://sonic-reader.vercel.app`

---

### Option 2: Vercel Dashboard (Easiest)

1. **Push to GitHub first:**
```bash
cd speedr-deploy
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/YOUR-USERNAME/sonic-reader.git
git push -u origin main
```

2. **Import to Vercel:**
   - Go to [vercel.com](https://vercel.com)
   - Click **"Add New Project"**
   - Import your GitHub repo
   - Configure:
     - Framework Preset: **Other**
     - Root Directory: **./speedr-deploy** (or leave as root if you pushed just the deploy folder)
     - Build Command: Leave empty
     - Output Directory: Leave empty
   - Click **Deploy**

---

## Add Custom Domain: sonic-reader.com

### Step 1: In Vercel Dashboard

1. Go to your project in Vercel
2. Click **Settings** → **Domains**
3. Add these domains:
   - `sonic-reader.com`
   - `www.sonic-reader.com`
4. Click **Add**

### Step 2: Configure DNS (Where you bought the domain)

Vercel will show you DNS records to add. You'll need to add these at your domain registrar (GoDaddy, Namecheap, Google Domains, etc.):

**For sonic-reader.com (root domain):**
- Type: **A**
- Name: **@**
- Value: **76.76.21.21**

**For www.sonic-reader.com:**
- Type: **CNAME**
- Name: **www**
- Value: **cname.vercel-dns.com**

### Step 3: Wait for DNS propagation (10-60 minutes)

Vercel will automatically verify and issue SSL certificate once DNS propagates.

---

## Update PayPal Return URL

After deployment, update your PayPal button:

1. Go to [PayPal](https://www.paypal.com) → Profile → My Selling Tools → Website Preferences
2. Update **Return URL** to:
   - `https://sonic-reader.com/success.html`
3. Save

---

## Deploy Updates

### Via CLI:
```bash
cd speedr-deploy
vercel --prod
```

### Via GitHub:
Just push to your repo and Vercel auto-deploys:
```bash
git add .
git commit -m "Update"
git push
```

---

## Environment Variables (Optional)

If you want to add any secrets later:

1. Go to Vercel Dashboard → Settings → Environment Variables
2. Add variables
3. Redeploy

---

## Vercel vs Netlify

| Feature | Vercel | Netlify |
|---------|--------|---------|
| Speed | ⚡ Faster | ⚡ Fast |
| Deploy | Instant | Instant |
| Free SSL | ✅ Yes | ✅ Yes |
| Custom Domain | ✅ Yes | ✅ Yes |
| CLI | ✅ Yes | ✅ Yes |
| Analytics | ✅ Built-in (paid) | ✅ Built-in (paid) |

Both work great! Vercel is slightly faster for static sites.

---

## Common Issues

**DNS not propagating?**
- Wait 1 hour
- Check DNS with: [dnschecker.org](https://dnschecker.org)
- Make sure you're adding records at the RIGHT registrar

**Vercel shows "Invalid Configuration"?**
- Make sure vercel.json is in the root
- Try removing vercel.json if issues persist (it's optional)

**www not working?**
- Add both `sonic-reader.com` AND `www.sonic-reader.com` in Vercel domains
- Add CNAME record for www

---

## Your Site Structure

```
speedr-deploy/
├── index.html          # Main app
├── success.html        # Payment success page
├── logo.png           # Sonic Reader logo
├── vercel.json        # Vercel config (optional)
├── netlify.toml       # Ignore this (for Netlify)
├── _headers           # Ignore this (for Netlify)
├── SETUP.md           # Setup guides
├── PAYPAL-SETUP.md    # PayPal integration
└── README.md          # Documentation
```

---

## Next Steps

1. ✅ Deploy to Vercel
2. ✅ Add custom domain (sonic-reader.com)
3. ✅ Update PayPal return URL
4. ✅ Test the full flow
5. ✅ Share and launch! 🚀

**Total time: ~15 minutes** (10 min for DNS)

---

## Quick Commands Cheat Sheet

```bash
# Install Vercel CLI
npm install -g vercel

# Deploy to preview
vercel

# Deploy to production
vercel --prod

# Check deployment logs
vercel logs

# Remove deployment
vercel remove sonic-reader
```

---

You're all set! Your site will be live at **sonic-reader.com** 🎉
