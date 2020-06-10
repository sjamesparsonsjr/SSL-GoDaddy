






![SSL-GoDaddy Logo](/SSL-GoDaddy.png)

# SSL-GoDaddy

*TL;DR* Free SSL (HTTPS) for GoDaddy.

**Description**
GoDaddy charges for SSL (HTMLS).  They offer [four packages](https://www.godaddy.com/web-security/ssl-certificate)  as of 2020/06/10.
|1 site| Multiple sites |Subdomains|Managed SSL|
|--|--|--|--|
|$80/year|$200/year|$370/year|$150/year|


this document will show you how to do it for free.   This needs to be done every 2 months (60 days).  6 times a year thats **$13**  Every two months!

![SSL-GoDaddy ScreenShot](/SSL-GoDaddy_screenShot.png)


## Support Websites
[Youtube Guide ](https://www.youtube.com/watch?v=GPcznB74GPs)  tipswithpunch walks us through the steps.

[ZeroSSL](https://zerossl.com/) Site that provides the SSL certificates

## Steps
1. Log into [ZeroSSL](https://zerossl.com/) an create a free account
2. Click on <kbd>New Certificate</kbd> Button
3. Send verfication email to admin@[you-domain].com <br> **note** I had to create an admin email.
4. Download certificates
5. Go to  cPanel -> SSL/TLS -> URL Link Manage SSL sites
6. Scroll to the section ``Install an SSL Website``
7. Select the domain you want to add SSL
8. Using text editor open the three downloaded fles<br>ca_bundle.crt<br>certificate.crt<br>private.key<br>
9. Copy ``certificate.crt `` text into ``Certificate: (CRT)`` field.
10. Copy ``private.key `` text into ``Certificate: (CRT)``  field.
11. Copy ``ca_bundle.crt`` text into ``Certificate Authority Bundle: (CABUNDLE)``  field.
12. On the [zerossl](https://zerossl.com/) website click the <kbd>Verify Certificate</kbd> Button
13. Make Calander event to remind you to update in 60 days.
14. Go to cPanel -> File Manager -> /public_html
15. Click ``Settings`` button, and make sure Show Hidden Files (dot files) is checked
16. Open file ``.htaccess``
17.  Paste this to the end of the file <br> ``RewriteEngine On``<br>``RewriteCond %{HTTPS} off`` <br>``RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]``

## Authors

* **[S James Parsons Jr](https://www.linkedin.com/in/sjamesparsonsjr/)** 


> Written with [StackEdit](https://stackedit.io/).
