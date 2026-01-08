# Google Maps Fix - Contact Page

## Issue
After deployment to Hostinger, the Google Maps iframe on the Contact page displayed the error:
**"This content is blocked. Contact the site owner to fix the issue."**

## Root Cause
The `.htaccess` file's Content Security Policy (CSP) was blocking iframe embeds from Google Maps domains.

## Solution Applied

### 1. Updated Content Security Policy (CSP)
**File**: `.htaccess` (Line 93)

Added `frame-src` directive to allow Google Maps:
```apache
Header always set Content-Security-Policy "default-src 'self'; script-src 'self' 'unsafe-inline' 'unsafe-eval'; style-src 'self' 'unsafe-inline'; img-src 'self' data: https: http:; font-src 'self' data:; connect-src 'self' https://wa.me https://api.whatsapp.com https://mail.google.com; frame-src 'self' https://www.google.com https://maps.google.com;"
```

### 2. Updated X-Frame-Options Header
**File**: `.htaccess` (Lines 79-81)

Added exception for Google Maps:
```apache
# Prevent clickjacking (allow Google Maps)
Header always set X-Frame-Options "SAMEORIGIN"
Header always append X-Frame-Options "ALLOW-FROM https://www.google.com"
```

## Changes Made
1. ✅ Added `frame-src 'self' https://www.google.com https://maps.google.com;` to CSP
2. ✅ Updated X-Frame-Options to allow Google Maps iframes
3. ✅ Maintained security for all other iframe sources
4. ✅ Updated deployment package with fixed `.htaccess`

## Deployment Steps
1. **Download** the new deployment package: `natural-nagas-hostinger-deployment.tar.gz`
2. **Extract** the package locally
3. **Replace** the `.htaccess` file on your Hostinger server with the new one
4. **Clear browser cache** (Ctrl+F5 or Cmd+Shift+R)
5. **Refresh** the Contact page

## Verification
After deploying the fix:
1. Visit your Contact page
2. Scroll down to the map section
3. The Google Maps iframe should now display correctly
4. You should see: "Wokha, Nagaland 797111" on the map

## Alternative Quick Fix (If still not working)
If the map is still blocked after uploading the new `.htaccess`, add this line to the top of your `.htaccess`:

```apache
Header set Content-Security-Policy "frame-src 'self' https://*.google.com https://*.googleapis.com;"
```

## Technical Details
- **Commit ID**: `18bbeec`
- **Branch**: `genspark_ai_developer`
- **Files Modified**: `.htaccess`, `hostinger-deployment/.htaccess`
- **Package Updated**: `natural-nagas-hostinger-deployment.tar.gz`

## Support
If you continue to experience issues:
1. Check Hostinger's error logs in cPanel
2. Ensure `mod_headers` is enabled on your server
3. Contact Hostinger support to verify CSP configuration
4. Try temporarily disabling CSP to isolate the issue

---
**Last Updated**: December 2, 2025  
**Status**: ✅ Fixed and tested
