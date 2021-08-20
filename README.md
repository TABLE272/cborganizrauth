These templates will add Organizr Auth to a Cloudbox setup, offering Basic Auth login and excluding required API paths.

Created a file in /opt/nginx-proxy/vhost.d titled appname.domain.tld_location and fill the contents of the relevant application.

For any applications not listed, the generic templates should provide a good basis.
If the application does not support Basic Auth, use Generic_No_Exlusions
If it does, use Generic_Basic_Auth to pass through your login details (You can change *arrs to "Basic" login method instead of "Form" to automatically log in.

If the app does not need to communicate with other apps these will be sufficient.
If the app needs to communicate with other apps, write exclusion blocks based upon existing templates such as Sonarr
