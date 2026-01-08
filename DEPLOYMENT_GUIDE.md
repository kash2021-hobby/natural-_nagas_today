# Natural Nagas - Hostinger Deployment Guide

## 📦 Deployment Package Contents

This package contains the **production-ready** build of Natural Nagas website with all optimizations applied.

### Files Structure:
```
hostinger-deployment/
├── index.html              # Main entry point (2.87 KB)
├── .htaccess              # Apache configuration for routing & caching
├── assets/                # JavaScript and CSS files
│   ├── index-*.css       # Styles (41.22 KB)
│   ├── index-*.js        # Main bundle (26.42 KB)
│   ├── react-core-*.js   # React library (157.88 KB)
│   ├── react-router-*.js # React Router (31.73 KB)
│   ├── About-*.js        # About page (29.21 KB)
│   ├── Programs-*.js     # Programs page (55.28 KB)
│   ├── Gallery-*.js      # Gallery page (35.60 KB)
│   ├── Events-*.js       # Events page (30.54 KB)
│   └── ... (other page chunks)
└── images/               # All website images (WebP optimized)
    ├── 1.webp
    ├── amur-falcon/
    ├── dhandeli-karnataka-trip/
    ├── environmental-events/
    ├── gdp-activities/
    ├── hec-workshops/
    ├── plantation-drives/
    ├── programs/
    └── team/
```

---

## 🚀 Deployment Steps for Hostinger

### Option 1: Using Hostinger File Manager (Recommended)

1. **Login to Hostinger**
   - Go to https://hpanel.hostinger.com
   - Login with your credentials

2. **Access File Manager**
   - Navigate to your hosting account
   - Click on "File Manager"
   - Go to `public_html` directory (or your domain directory)

3. **Clear Existing Files (if any)**
   - Select all old files in `public_html`
   - Delete them (backup first if needed)

4. **Upload New Files**
   - Click "Upload" button
   - Select ALL files from this `hostinger-deployment` folder
   - Upload everything (index.html, .htaccess, assets/, images/)
   - Wait for upload to complete

5. **Verify Permissions**
   - Ensure `.htaccess` is readable (644 permissions)
   - Ensure directories are executable (755 permissions)

6. **Test the Website**
   - Visit your domain: https://yourdomain.com
   - Test all pages (About, Programs, Events, Gallery, Contact, etc.)
   - Check mobile responsiveness
   - Test all forms and WhatsApp integrations

### Option 2: Using FTP/SFTP

1. **Connect via FTP**
   - Use FileZilla or any FTP client
   - Host: ftp.yourdomain.com (or Hostinger FTP hostname)
   - Username: Your Hostinger FTP username
   - Password: Your Hostinger FTP password
   - Port: 21 (FTP) or 22 (SFTP)

2. **Navigate to public_html**
   - Open the `public_html` folder (or your domain folder)

3. **Upload Files**
   - Drag and drop ALL files from `hostinger-deployment` folder
   - Ensure binary mode for images
   - Keep directory structure intact

4. **Set Permissions**
   - Right-click `.htaccess` → File Permissions → Set to 644
   - Directories should be 755
   - Files should be 644

---

## ⚙️ Post-Deployment Configuration

### 1. SSL Certificate (HTTPS)
- Go to Hostinger control panel
- Navigate to "SSL" section
- Enable "Force HTTPS"
- Wait 5-10 minutes for SSL to activate

### 2. Domain Configuration
- Ensure your domain points to Hostinger nameservers
- Clear DNS cache if needed
- Wait for DNS propagation (up to 24 hours)

### 3. Performance Optimization
- Enable Hostinger's CDN (if available)
- Enable caching in Hostinger control panel
- The `.htaccess` file already includes:
  - Gzip compression
  - Browser caching
  - Security headers

---

## ✅ Verification Checklist

After deployment, verify the following:

- [ ] Homepage loads correctly (https://yourdomain.com)
- [ ] All navigation links work
- [ ] About page displays Steve Odyuo's image
- [ ] Programs page shows all projects
- [ ] Events page displays Clean Doyang Mission article
- [ ] Gallery page works with lightbox
- [ ] Contact form redirects to WhatsApp
- [ ] Get Involved donation form works
- [ ] All images load properly (WebP format)
- [ ] Mobile responsive design works
- [ ] Page transitions are smooth
- [ ] No 404 errors in browser console
- [ ] SSL certificate shows padlock icon
- [ ] Website loads in < 2 seconds

---

## 🐛 Troubleshooting

### Issue: Blank page or "Cannot GET /about" errors
**Solution:** Ensure `.htaccess` file is uploaded and readable
```bash
# Check file exists in File Manager
# Permissions should be 644
```

### Issue: Images not loading
**Solution:** Verify `images` folder is uploaded completely
- Check all subdirectories exist
- Verify file paths are correct (case-sensitive)

### Issue: CSS not applying
**Solution:** Clear browser cache or use Ctrl+Shift+R (hard refresh)

### Issue: 404 errors on page refresh
**Solution:** 
1. Check if `.htaccess` is present
2. Verify Apache mod_rewrite is enabled (contact Hostinger support)
3. Check RewriteBase in .htaccess matches your setup

### Issue: WhatsApp links not working
**Solution:** 
- Links use `wa.me` format: https://wa.me/917005092944
- Should work on all devices
- Test on mobile for best experience

---

## 📊 Performance Metrics

**Expected Performance:**
- First Contentful Paint: < 0.5s
- Time to Interactive: < 1s
- Total Page Size: ~220 KB (with lazy loading)
- Lighthouse Score: 95+

**Optimization Features:**
- ✅ Code splitting (React Router)
- ✅ Lazy loading (all pages except Home)
- ✅ WebP image format
- ✅ Gzip compression
- ✅ Browser caching (1 year for images)
- ✅ Minified JavaScript & CSS
- ✅ Tree-shaken dependencies
- ✅ Hash-based cache busting

---

## 🔄 Future Updates

### To Update the Website:

1. **Make changes in development**
   ```bash
   cd /home/user/webapp
   # Make your changes
   npm run build
   ```

2. **Upload only changed files**
   - Only upload files that changed
   - Check `dist` folder for new builds
   - Hash in filenames changes automatically

3. **Clear cache if needed**
   - Hostinger control panel → Clear Cache
   - Or wait for cache expiration

---

## 📞 Support

**Hostinger Support:**
- Live Chat: Available 24/7
- Email: support@hostinger.com
- Knowledge Base: https://support.hostinger.com

**Website Issues:**
- Check browser console for errors (F12)
- Verify `.htaccess` configuration
- Contact Hostinger if Apache modules needed

---

## 🎉 Deployment Complete!

Your Natural Nagas website is now:
- ⚡ Super fast loading (< 1 second)
- 📱 Mobile responsive
- 🔒 Secure with HTTPS
- 🚀 Optimized for performance
- 💚 Ready for visitors!

**Live URL:** https://yourdomain.com

Remember to test all features and enjoy your new optimized website! 🌿
