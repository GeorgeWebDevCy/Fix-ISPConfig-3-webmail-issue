# Fix ISPConfig 3 webmail issue
-------------------------------
When installing ISPConfig 3 using the guide here:https://www.howtoforge.com/tutorial/ispconfig-automated-install-script/

After initial installation and configuration 

When trying to access the webmail at https://YOURIP:8080/webmail/ you get a 404 error. If we select roundcube as our default webmail client

To solve this issue run these commands in sequence 

1. cat >> /etc/apache2/conf-available/local.conf <<EOF
   Alias /webmail /var/lib/roundcube
   EOF

2. a2enconf local
3. service apache2 restart
This should solve the issue for you

Related blog post here:https://www.georgenicolaou.me/how-to-fix-ispconfig-3-webmail-issue/
