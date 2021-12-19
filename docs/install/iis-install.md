# Install OpenCAD on IIS

## Installing On Internet Information Services

### Prerequisites

- Windows server running Windows 2016 or above (earlier versions will work, but not supported by Microsoft.)
- IIS 8.0 or above
- Recommended but not required: PHP Manager for IIS (helps with configuring PHP on Windows to avoid having to manually enter values into php.ini)
- database server: either MySQL 5 or MariaDB 10

### Installtaion Steps

1. Extract the archive containing the OpanCAD files into the dorectory that you have chosen for your site content (knowledge of creating web sites in IIS is beyond scope.)
2. Ensure that the permissions for the directory (via Explorer>properties>security tab) and the site (via sites>website) have full control set for the application pool identity. Each site created in IIS from version 7.0 onwards will be created in its own isolated application pool, with its own virtual identity. Note that these identities are not actual accounts in Windows, so they will not show up as users on the server. 
3. Navigate to the site settings via right-clicking the site, then choosing basic settings from the menu that pops up.
4. Under application pool, ensure the pool is either set to your site's name, or is set to the default application pool (though please note that running two or more sites under a single identity can cause issues down the road if one of the sites stops working, others could crash with it)
5. Under site bindings, set all of your ports to the correct IP addresses and port number values (normally port 80 for http and 443 for https) 
6. Either set a single IP per port if you have the IP addresses to spare, or set it to all unassigned if only a single IP is available.
7. Give the host a name matching the domain on which your site runs.
8. Assuming everything is set up correctly, browse to your site and go to the autoinstaller located at https://sitename.domainname/install/start.php.
9. Walk through the installer, providing values for your community's name, name of the database, along with user name and password (assuming that you set up the database beforehand; otherwise, go ahead and set those up now.)

***
## Additional Microsoft Documentation
- [Microsoft's documentation on the application pool identity concept](https://docs.microsoft.com/en-us/iis/manage/configuring-security/application-pool-identities#:~:text=Here%20is%20how%3A%201%20Open%20the%20IIS%20Management,5%20The%20following%20dialog%20appears%3A%20More%20items...%20)
- [documentation for the PHP Manager IIS extension](https://www.iis.net/downloads/community/2018/05/php-manager-150-for-iis-10)