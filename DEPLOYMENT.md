# 🚀 Deployment Guide

Complete step-by-step guide to deploy your Europe Tension Tracker with synthetic data.

## 📋 Prerequisites

- GitHub account
- Git installed locally
- Python 3.8+ installed

## 🔧 Step 1: Repository Setup

### 1.1 Create GitHub Repository
```bash
# Create new repository on GitHub: europe-tension-tracker
# Clone locally
git clone https://github.com/YOUR_USERNAME/europe-tension-tracker.git
cd europe-tension-tracker

# Copy all files from this project
# Commit initial version
git add .
git commit -m "🎉 Initial Europe Tension Tracker setup"
git push origin main
```

### 1.2 Test Locally
```bash
# Test frontend
python -m http.server 8000
# Open http://localhost:8000 in browser
```

## 🔧 Step 2: GitHub Pages Setup

### 2.1 Enable GitHub Pages
1. Go to `https://github.com/YOUR_USERNAME/europe-tension-tracker`
2. Click **Settings** tab
3. Scroll to **Pages** section
4. **Source:** Select "GitHub Actions"
5. Save settings

### 2.2 Configure Frontend URL
Edit `index.html` around line 150:

```javascript
const CONFIG = {
    // Replace with your actual GitHub Pages URL
    DATA_URL: 'https://YOUR_USERNAME.github.io/europe-tension-tracker/data/europe-tension.json',
    // ... rest of config
};
```

### 2.3 Commit URL Changes
```bash
git add index.html
git commit -m "🔧 Configure production DATA_URL"
git push origin main
```

## 🔧 Step 3: Verification

### 3.1 Check URLs
After deployment completes, verify these URLs work:

```bash
# Main application
curl -I https://YOUR_USERNAME.github.io/europe-tension-tracker/

# JSON data endpoint
curl https://YOUR_USERNAME.github.io/europe-tension-tracker/data/europe-tension.json

# Should return valid JSON with scores array
```

### 3.2 Test Frontend
1. Open `https://YOUR_USERNAME.github.io/europe-tension-tracker/`
2. Map should load within 5 seconds
3. Hover over countries to see tooltips
4. Check browser console for errors

## 🔧 Step 4: Custom Domain (Optional)

### 4.1 Setup Custom Domain
If you want to use your own domain (e.g., `tension.yoursite.com`):

1. **GitHub Settings:**
   - Go to Settings > Pages
   - Enter your custom domain
   - Enable "Enforce HTTPS"

2. **DNS Configuration:**
   ```
   # Add CNAME record in your DNS provider
   CNAME   tension   YOUR_USERNAME.github.io
   ```

3. **Update Frontend Config:**
   ```javascript
   DATA_URL: 'https://tension.yoursite.com/data/europe-tension.json'
   ```

## 🔧 Step 5: Customization Options

### 5.1 Update Tension Scores
Edit `data/europe-tension.json` to modify country tension scores:
```json
{
  "iso3": "HUN",
  "country": "Hungary",
  "score": 25,
  "level": "low",
  "events": 12
}
```

### 5.2 Add More Countries
Add new entries to the `scores` array in the JSON file with ISO3 country codes.

## 🎯 Success Checklist

- ✅ Repository created and code pushed
- ✅ GitHub Pages enabled and configured
- ✅ DATA_URL updated in frontend
- ✅ Main URL loads the map
- ✅ JSON endpoint returns valid data
- ✅ Countries show correct colors/tooltips
- ✅ No console errors
- ✅ Mobile-friendly responsive design

## 🚨 Troubleshooting

### Frontend Not Loading
```bash
# Check browser console
# Common issues:
# - Wrong DATA_URL
# - CORS errors
# - JSON parse errors
```

### Data Not Showing
```bash
# Verify JSON file exists at correct path
# Check JSON syntax is valid
# Verify file is accessible via URL
```

---

**🎉 Your Europe Tension Tracker is now live!**

Main URL: `https://YOUR_USERNAME.github.io/europe-tension-tracker/`
JSON API: `https://YOUR_USERNAME.github.io/europe-tension-tracker/data/europe-tension.json`

*Update the URLs above with your actual GitHub username.*