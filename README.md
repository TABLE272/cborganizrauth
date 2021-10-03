These templates will add Organizr Auth to a Cloudbox setup, offering Basic Auth login and excluding required API paths.

Create a file in /opt/nginx-proxy/vhost.d titled appname.domain.tld_location (where you would access this app in your browser) and fill the contents from the relevant template.

For any applications not listed, the generic templates should provide a good basis.
If the application does not support Basic Auth, use Generic_No_Exclusions
If it does, use Generic_Basic_Auth to pass through your login details (You can change *arrs to "Basic" login method instead of "Form" to automatically log in.

If the app does not need to communicate with other apps these will be sufficient.
If the app needs to communicate with other apps, write exclusion blocks based upon existing templates such as Sonarr

After applying a template, you will need to restart both nginx-proxy and the app in question.
If you screw up, particularly making your own file, edit the file to be blank but leave it in place. Do not delete the file. This is because nginx-proxy will continue to try to reference this file and fail to start, causing you to need to re-run the nginx-proxy role.
