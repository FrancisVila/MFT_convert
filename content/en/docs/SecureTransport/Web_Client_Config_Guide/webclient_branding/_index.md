{
    "title": "Brand the interface",
    "linkTitle": "Brand the interface",
    "weight": "90"
}Changing the branding means modifying the following aspects of the Secure Transport Web Client:

-   Color theme and style
-   Logo on the login page and on the pages a logged in user can access
-   Text header next to the logo
-   Disclaimer on the login page
-   Favicon
-   adding custom content via Layout Injector plugin

## Prerequisites

On a separate machine than the ST Server, install NodeJS from the official website https://nodejs.org/ or through the package manager if you’re working on a Linux machine.

Then install the less compiler (version 3.9.0), postcss-cli (version 5.0.1), autoprefixer (version 9.4.5), clean-css (version 4.2.1), and postcss-clean (version 1.1.0):

    npm install -g less@3.9.0 postcss-cli@5.0.1 autoprefixer@9.4.5 clean-css@4.2.1 postcss-clean@1.1.0

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Do not install NodeJS on the production server where <span>SecureTransport</span> is installed. Use a separate machine for building the branding assets.         </td>
      </tr>
</table>

## Procedure

The application is styled and branded by the following files and folders found in the ST Web Client installation folder:

-   `C/assets/wap.css` - Controls the color theme and the style. It is generated from several .less files delivered in the branding assets archive.
-   `custom/stwebclient.config.json` - Controls the logos, the text header displayed next to the logo and the disclaimer on the login page.

## Change the logos, header, and disclaimer

This is done by editing the custom configuration file as described in section [Configuration files](../config_files).

Copy the “branding” section from `C/config/default.config.json` into `custom/stwebclient.config.json`, and do the modifications as desired.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The logo paths are relative to <code>[SecureTransport_installDir]/share/ftdocs</code>. If you modify them, make sure to create them on the server.         </td>
      </tr>
</table>

## <span id="Change2"></span>Change the favicon

This is done by adding an ICO file in `[SecureTransport_installDir]/share/ftdocs`. The ICO file must respect these conditions:

-   Must be named `favicon.ico`
-   Must be 64x64 pixels in size

This customization is not preserved between installations or after applying a patch or service pack.

The `favicon.ico` file must be added again after these operations.

## <span id="Change"></span>Change the color theme and/or the style

1.  Copy the branding assets archive` C/assets/branding/branding_assets.zip` on the system where you installed NodeJS and unzip it. After unzipping, it should have the following directory structure:  
    
        assets_508.less_a5.less_book.less_branding.less_download.less_fonts.less_header.less_icons.less_media-queries.less_mixins.less_reset.less_spinner.lessprogress.lesswap.less
2.  To change the color theme, follow the steps bellow. If you want to change an existing style or create a new one, go to step 3.  
    2.1 Open `_branding.less` in a text editor. The color theme is defined by a set of variables:  
    -   `toolbarBgImage` - \[null | path\]
        -   background image for the toolbar component. Paths are relative to `[SecureTransport_installDir]/share/ftdocs`.
    -   `baseColor` - \[color\]
        -   main color of the file explorer
    -   `headerColor` - \[color\]
        -   header background color.
    -   `sidebarColor` - \[color\]
        -   sidebar background color.
    -   `highlightColor`- \[color\]
        -   active element color.
    -   `secondaryColor` - \[color\]
    -   `headerHighlightColor` - \[color\]
        -   custom highlight color for active elements in the header.
    -   `headerUsesFlatColor` - \[auto|true|false\]
        -   header background style. Set to true for flat color, false for gradient or leave auto.

      
    2.2 You can either modify the default theme or use one of the predefined alternative themes.  
    In order to use one of the predefined themes, comment the default theme and uncomment the desired predefined theme. A theme is commented by adding /\* before the first variable in the group and \*/ after the last one. It is uncommented by removing the lines containing /\* and \*/ at the beginning and the end of its variable group.
3.  To override an existing style or create a new one, follow the steps:  
    3.1 Create a file called "custom.less".  
    3.2 Define all the new style definitions and overrides in this file. You can reuse definitions and variables from the other LESS files, the compiler imports them automatically.  
    Example: removing the background image  
      
    
        /* the original style definition in wap.less at line 3104 */

        body.Login {

          color: contrast(@baseColor);

          background-color: @baseColor;

          background-image: url(textures/login_background_1920x1080.jpg);

          background-position: center center;

          background-size: cover;

          background-attachment: fixed;

        }

         

        /the modified style definition in * custom.less */

        body.Login {

          /* Set background-image to 'none' */

          background-image: none;

        }

      
    3.3 Copy `custom.less` next to the other branding artifacts (`wap.less, progress.less`, etc. ) to the unzipped folder.

4\. After modifying `branding.less`, you need to generate the CSS files containing the new theme. This is done using the LESS compiler which should be installed beforehand.

<!-- -->

<!-- -->

<!-- -->

5\. Copy both CSS files to the server in `C/assets` by overwriting the old `wap.css` and `progress.css`.  
Make sure to put the image used for `@toolbarBgImage` on the server .
