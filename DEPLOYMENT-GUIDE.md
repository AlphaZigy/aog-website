# AOG Website Deployment Guide - cPanel

## Prerequisites
- cPanel hosting account with file manager access
- FTP/SFTP client (optional, but recommended)
- Your website files (already prepared in this repository)

## Deployment Methods

### Method 1: Direct File Upload via cPanel File Manager

1. **Log into cPanel**
   - Access your hosting provider's cPanel login page
   - Enter your credentials

2. **Navigate to File Manager**
   - Find and click "File Manager" in the Files section
   - Navigate to the `public_html` directory (or your domain's document root)

3. **Clear existing files (if any)**
   - Select all existing files in public_html
   - Delete them to make room for your new website

4. **Upload website files**
   - Upload all files from your local `aog` folder to `public_html`
   - Make sure to upload:
     - All HTML files (`index.html`, `about.html`, etc.)
     - `css/` folder with all stylesheets
     - `js/` folder with JavaScript files
     - `img/` folder with all images
     - `lib/` folder with libraries
     - `.htaccess` file (for Apache configuration)

### Method 2: FTP Upload

1. **Get FTP credentials from cPanel**
   - In cPanel, look for "FTP Accounts" or "FTP Settings"
   - Note down: hostname, username, password, port (usually 21)

2. **Use FTP client**
   - Use FileZilla, WinSCP, or similar FTP client
   - Connect to your server using the credentials
   - Navigate to `public_html` directory
   - Upload all website files

### Method 3: Git Deployment (if supported)

1. **Check if Git is available**
   - Look for "Git™ Version Control" in cPanel
   - If available, you can clone directly from GitHub

2. **Clone repository**
   ```bash
   git clone https://github.com/AlphaZigy/aog-website.git
   ```

3. **Move files to public_html**
   - Copy all files from the cloned directory to `public_html`

## Post-Deployment Steps

1. **Set file permissions**
   - HTML files: 644
   - Directories: 755
   - .htaccess file: 644

2. **Test the website**
   - Visit your domain to ensure the site loads correctly
   - Test all navigation links
   - Check that images and CSS are loading properly

3. **Enable SSL (recommended)**
   - In cPanel, look for "SSL/TLS" or "Let's Encrypt"
   - Enable SSL certificate for your domain
   - Uncomment the HTTPS redirect lines in .htaccess if needed

4. **Set up custom error pages**
   - Your 404.html page is already configured in .htaccess
   - Test by visiting a non-existent page

## File Structure for Upload

Ensure the following structure is maintained in `public_html`:

```
public_html/
├── index.html
├── about.html
├── contact.html
├── donate.html
├── testimonial.html
├── ministries.html
├── executive.html
├── 404.html
├── .htaccess
├── css/
│   ├── bootstrap.min.css
│   └── style.css
├── js/
│   └── main.js
├── img/
│   ├── logo.png
│   ├── carousel-1.jpg
│   └── [all other images]
└── lib/
    ├── animate/
    ├── easing/
    ├── owlcarousel/
    └── [other libraries]
```

## Troubleshooting

### Common Issues:

1. **Website shows directory listing instead of homepage**
   - Ensure `index.html` is in the root of `public_html`
   - Check that the filename is exactly `index.html` (case-sensitive on Linux)

2. **CSS/Images not loading**
   - Check file permissions (should be 644 for files, 755 for directories)
   - Verify file paths in HTML are correct (case-sensitive)

3. **404 errors for existing pages**
   - Check .htaccess syntax
   - Ensure mod_rewrite is enabled on the server

4. **Mixed content warnings (HTTP/HTTPS)**
   - Update any hardcoded HTTP links to HTTPS
   - Enable the HTTPS redirect in .htaccess

### Getting Help:
- Contact your hosting provider's support if you encounter server-specific issues
- Check cPanel documentation for your specific hosting provider
- Verify that your hosting package supports the features you're trying to use

## Domain Configuration

If this is a new domain or subdomain:
1. Ensure DNS is properly configured
2. Wait for DNS propagation (can take up to 48 hours)
3. Test from different locations/devices

## Maintenance

To update the website:
1. Make changes to your local files
2. Commit changes to Git repository
3. Re-upload changed files via cPanel or FTP
4. Test the updates on the live site

---

**Note**: Always backup your website files before making major changes!