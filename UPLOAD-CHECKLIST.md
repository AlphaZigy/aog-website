# cPanel Upload Checklist

## Before Upload
- [ ] Backup any existing website files
- [ ] Test website locally to ensure everything works
- [ ] Verify all image paths and links are working

## Files to Upload
- [ ] index.html (main homepage)
- [ ] about.html
- [ ] contact.html
- [ ] donate.html
- [ ] testimonial.html
- [ ] ministries.html
- [ ] executive.html
- [ ] 404.html
- [ ] .htaccess (server configuration)

## Folders to Upload
- [ ] css/ (all stylesheets)
- [ ] js/ (JavaScript files)
- [ ] img/ (all images and logos)
- [ ] lib/ (third-party libraries)
- [ ] scss/ (SCSS source files - optional for live site)

## After Upload
- [ ] Check file permissions (644 for files, 755 for folders)
- [ ] Test homepage loads correctly
- [ ] Test all navigation links
- [ ] Verify images display properly
- [ ] Test contact form (if applicable)
- [ ] Check mobile responsiveness
- [ ] Test on different browsers
- [ ] Set up SSL certificate if available
- [ ] Enable HTTPS redirect if SSL is configured

## Domain Setup (if new domain)
- [ ] Configure DNS settings
- [ ] Wait for DNS propagation
- [ ] Test from multiple locations

## Optional Optimizations
- [ ] Enable Gzip compression (configured in .htaccess)
- [ ] Set up caching headers (configured in .htaccess)
- [ ] Configure security headers (configured in .htaccess)
- [ ] Set up website analytics (Google Analytics, etc.)
- [ ] Configure backup schedule in cPanel