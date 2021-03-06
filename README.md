## Setting up a e-commerce site using WordPress & WooCommerce!

Sample site https://www.iwantaverycheapdomainname.xyz/

#### Getting Ready

1. Visit https://www.dreamhost.com/wordpress/shared-wp-hosting/
2. Select a plan
   - We recommend selecting the one month plan for now from **Shared Hosting**

![hosting](images/hosting.png)

3. You will then be asked to choose a domain. You can choose to "link" an existing domain that you have or register one with them.
   - You can also register a domain on sites like **GoDaddy** or **Namecheap**.
     - For example, on [GoDaddy](https://my.godaddy.com/domains/domain-name-search). You just have to type in the domain name that you're looking for in the search bar provided, then it will show a list of domains that you might be interested in.
       ![domain-purchase](images/domain-purchase.png)
       ![domain-result](images/domain-result.png)
     - After adding a domain into your cart, it will bring you to a page where it asks you if you want to include some other features, all of these options are optional. Becareful of what you've sign up for!
   - Once you've registered a domain with one of the registrar, configure your **Nameservers** to point to
     ```
     ns1.dreamhost.com
     ns2.dreamhost.com
     ns3.dreamhost.com
     ```
   - In the case of **GoDaddy**, it will be under your **GoDaddy** dashboard
     ![dns-config](images/dns-config.png)
     ![nameservers](images/nameservers.png)

![domain-plan](images/domain-plan.png)

4. You will then be asked to pay for the hosting plan and other things.
   - If you scroll down to the **Additional Options** section, you can further customize what you're paying for.
     - DreamShield
       - Sort of like a anti-virus + cleaner. I would recommend keeping this unless you're just creating a test site rather than an actual public website that you're expecting traffic.
     - Professional Email
       - This is to give you another mailbox under your domain. e.g. no-reply@mydomain.com
       - Like DreamShield, I would'nt recommend this unless you're deploying an actual website.

![payment](images/payment.png)

5. After paying for the service, you should have access to DreamHost's dashboard. From there, you should be able to access your WordPress Dashboard
   - If you visit the domain name that you've keyed in during step **3**, then you should see a dummy site that you can build on top! Congratulations on getting your first WordPress site!

![dh-dashboard](images/dh-dashboard.png)

6. Next is to setup SSL for your WordPress site. SSL is used to protect users that are browsing your site. On DreamHost's Dashboard, on the sidebar, under **Domains**, there should be a **SSL/TLS Certificates** section, click on it.

![ssl](images/ssl.png)

7. Your domain should be listed, make sure that there is a certificate associated to it.
   - If there is no certificate, click on **Settings** that is beside your domain.
   - Click on **Add New Certificate**.
   - Choose which certificate to use. Either is fine.

![ssl-set](images/ssl-set.png)

8. After setting up the certificate, you should enforce it by forcing all users to visit your HTTPS site instead of HTTP. Do this by going to your DreamHost Dashboard, at the FileManager section, click on **Manage Files**, this will open up a file browser on another tab.

![file-manager](images/file-manager.png)

9. You should see your domain name as a folder, that folder contains all the files for your WordPress site, inside the folder, there should be two files named **.htaccess** and **wp-config.php** respectively.
10. Open **wp-config.php** and add these at the end of the file.
    ```
    define('FORCE_SSL', true);
    define('FORCE_SSL_ADMIN',true);
    ```
11. Open **.htaccess** and add these at the end of the file.
    ```
    RewriteEngine On
    RewriteCond %{HTTPS} !=on
    RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301,NE]
    ```
    - After both step **10** and **11**, you should be redirected back to HTTPS whenever you try to visit the site in HTTP.
12. Access your WordPress Dashboard through DreamHost Dashboard.

![wp-dashboard](images/wp-dashboard.png)

13. Once you've access your WordPress Dashboard, click on **Users** at the sidebar, it should show you a pre-generated user. Click on the user and scroll to the **Account Management** section. From there, click on **Generate Password**, you can use the random password that is generated, or you can change it to another password, once you're done, scroll down and click on **Update Profile**.

![wp-user](images/wp-user.png)

#### Themes

1. You can change your site's theme by accessing **Customize** on the left bar of your WordPress Dashboard, and then clicking on **Change Themes**

![wp-theme](images/wp-theme.png)

2. There, you can either choose from existing installed themes, or click on **Add New** to install new themes.

![theme](images/theme.png)

3. Under customize is where you can also further customize how your site looks!

#### Pages

1. We will start by adding a new page for our site! On the WordPress Dashboard, there should be a **Pages** section on the left bar, under that there should be an **Add Blank** section, click on it.

![add-page](images/add-page.png)

2. The page will then show you an editor where you can customize your page however you like.
   - The + sign on the top-left corner allows you to add more elements to the page!

![demo-page](images/demo-page.png)

3. After customizing your page, you can preview it by clicking on the **Preview** button at the top right corner of the page.
4. When you're ready, just click on **Publish...** to publish your page!

#### Plugins

1. On your WordPress Dashboard, go to the **Plugins** section, then click on **Add New**.

![new-plugin](images/new-plugin.png)

2. Install **WooCommerce** and **WooCommerce Services**

![install](images/install.png)

3. Activate **Jetpack**, **WooCommerce** and **WooCommerce Services** from **Plugins** page.

![activate](images/activate.png)

4. Clicking on **Pages** section will reveal that **WooCommerce** has added a few more pages on your WordPress site!
5. Whenever you need to add any functionality to your WordPress site, just go to **Add New** section and search for it.

#### WooCommerce

1. We will first start by creating our first product for our store! There should be a **Products** section at the sidebar, there should be an **Add New** section under it, click on it.

![new-product](images/new-product.png)

2. The important options on this page are:
   - Product name
   - Product categories
   - Product tags
   - Product image
   - Product gallery
   - Product data
   - Product short description
3. Fill the informations in, once you're done, click on the **Publish** button!
4. Remember that **WooCommerce** actually added a few extra pages for us? Visit the **Shop** page that is added. If you don't know where to access the page, just click on the **Pages** section on the left bar, and click **View** on the **Shop** page!

![view-shop](images/view-shop.png)

5. You should now be able to see the product that you just posted!

#### WooCommerce Extra

1. There are a few options that you can enable/disable for **WooCommerce**, under **WooCommerce**, there should be a **Settings** section, click on it.

![shop-settings](images/shop-settings.png)

2. The options that you're most likely interested are:

   - Under **Shipping** tab, there should be an option named **WooCommerce Services**. There you can add shipping labels and packaging.

   ![label](images/label.png)

   - There is also the **Payments** tab where you can add more payment methods into your e-commerce site. Remember if its not listed here, you can still add more payment methods through **Plugins**
   - Under **Accounts & Privacy**, you can configure how your customer can create their account for your site.
