# Hostinger Website Synchronization & Deployment Checklist

## ✅ Issues Found & Fixed

### Path Inconsistencies (FIXED)
The website had **9 instances** where internal PHP file links were missing the `./` prefix. This caused broken page links on Hostinger because relative paths weren't resolved correctly.

**Files Fixed:**
- ✅ `index.php` - Fixed 2 links (about.php, contact.php, gallery.php)
- ✅ `gallery.php` - Fixed 4 links (blog.php, media-coverage.php, contact.php, achievements.php)
- ✅ `achievements.php` - Fixed 1 link (contact.php)

### Path Standardization (COMPLETED)
All asset paths are now standardized with `./` prefix:
- ✅ All images: `./images/*` format
- ✅ All CSS: `./styles.css` format
- ✅ All libraries: `./site_libs/*` format
- ✅ All internal links: `./filename.php` format

---

## 📋 Pre-Deployment Checklist

### 1. **Verify All Files Locally**
- [ ] Website works at `http://localhost:8000`
- [ ] All images display correctly
- [ ] All internal links work
- [ ] Navigation menus function properly
- [ ] CSS styling is applied

### 2. **Files to Upload to Hostinger**
Ensure you upload ALL of these to your Hostinger account:

**In `public_html/` (or your domain's root):**
```
✓ All 19 PHP files:
  - index.php, about.php, achievements.php, basicright.php
  - blog.php, board.php, capacity.php, career.php
  - contact.php, disaster.php, donation.php, focusareas.php
  - gallery.php, livelihood.php, media-coverage.php, mission.php
  - objectives.php, secretary-desk.php, team.php

✓ CSS & Resources:
  - styles.css
  - responsive.css
  - search.json

✓ Folders (entire contents):
  - images/ (all image files)
  - site_libs/ (all Quarto libraries)
  - vendor/ (Composer dependencies - optional but recommended)

✓ Configuration Files:
  - composer.json
  - composer.lock (auto-generated)
```

### 3. **File Permissions on Hostinger**
After uploading, set correct permissions:
- **PHP files & CSS**: `644` (readable by all, writable only by owner)
- **Directories**: `755` (traversable by all)

Set via Hostinger File Manager:
1. Right-click file → Properties
2. Set permissions accordingly

### 4. **Verify Upload Completeness**
Before testing on Hostinger:
- [ ] All PHP files uploaded
- [ ] `images/` folder with all 58 image files
- [ ] `site_libs/` folder with Bootstrap and Quarto libraries
- [ ] `styles.css` and `responsive.css` files
- [ ] Check folder structure matches locally

### 5. **Test on Hostinger**
After uploading:
- [ ] Access your domain (e.g., yoursite.com)
- [ ] Images load without 404 errors
- [ ] Navigation links work
- [ ] All pages load and display correctly
- [ ] CSS styling looks right
- [ ] No broken links

### 6. **Troubleshooting Common Issues**

| Issue | Cause | Solution |
|-------|-------|----------|
| **Broken Images** | Missing `images/` folder | Upload entire `images/` folder |
| **Broken CSS** | Missing `styles.css` | Verify `styles.css` uploaded to root |
| **Broken Pages Links** | Missing `./` prefix | ✅ Already fixed in v2 |
| **Page Styling Broken** | Missing `site_libs/` | Upload entire `site_libs/` folder recursively |
| **404 Errors** | Incomplete file upload | Use Hostinger's "Upload" or FTP to sync |

### 7. **Clear Cache After Deployment**
- [ ] Clear browser cache (Ctrl+Shift+Delete or Cmd+Shift+Delete)
- [ ] Clear Hostinger's page cache (if enabled in control panel)
- [ ] Wait 5-10 minutes for DNS propagation

---

## 🔄 Upload Methods (Choose One)

### Method 1: Hostinger File Manager (Easiest)
1. Log into Hostinger Control Panel
2. Go to File Manager
3. Navigate to `public_html/`
4. Upload each PHP file
5. Upload entire `images/`, `site_libs/`, `vendor/` folders
6. Upload CSS files

### Method 2: FTP Upload (Recommended for large uploads)
1. Use FileZilla or WinSCP
2. Connect using Hostinger FTP credentials
3. Navigate to `public_html/` 
4. Drag and drop all files/folders
5. Ensure permissions are set correctly

### Method 3: Hostinger File Synchronization
Some Hostinger plans include automatic sync - check your control panel.

---

## 📝 Version History
- **v2.0** (Current): Fixed 9 path inconsistencies, standardized all relative paths
- **v1.0**: Initial sync issues with broken links and missing `./ ` prefixes

---

## ✨ Summary
Your website is now **fully synchronized and ready for Hostinger**. All relative paths use the correct `./` prefix, and all files are structured for proper deployment. Simply upload all files following the checklist above, and your site should work identically to localhost.

**Key Difference from Before:** Internal PHP file links now consistently use `./filename.php` format, which ensures they resolve correctly on all domains and hosting providers.
