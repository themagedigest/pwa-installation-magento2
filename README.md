# pwa-installation-magento2

Pre-requisites

Install NODE + NPM - 
https://askubuntu.com/questions/426750/how-can-i-update-my-nodejs-to-the-latest-version
https://linuxize.com/post/how-to-install-node-js-on-ubuntu-20-04/

Install YARN - https://classic.yarnpkg.com/lang/en/docs/install/#windows-stable

Check your versions -
NodeJS >=16 LTS
Yarn >=1.13.0 ===> Recommended
NPM > 8.19

Setup a storefront project

Go to html directory
yarn create @magento/pwa

cd pwa => before running the below commands.
yarn run buildpack create-custom-origin ./  => to generate a unique, secure custom domain for your new project. Highly recommended.
yarn run watch => to start the dev server and do real-time development.

Link for solution or follow below commands 1 to 6 = https://developer.adobe.com/commerce/pwa-studio/metapackages/open-source/

Go to magento root directory and run below commands.
1. git clone git@github.com:magento/magento2-pwa.git /var/www/html/magento243/vendor/ext/magento/magento2-pwa
2. composer config minimum-stability dev
3. composer config repositories.ext path "./vendor/ext/*/*/*"
4. composer require magento/pwa
5. php bin/magento module:enable --clear-static-content Magento_ContactGraphQlPwa
6. php bin/magento module:enable --clear-static-content Magento_NewsletterGraphQlPwa

Come back to PWA directory and execute => yarn run watch

yarn run storybook => to start Storybook dev server and view available components in your app.
yarn run build => to build the project into optimized assets in the '/dist' directory.
yarn start => after build to preview the app on a local staging server.


Note - edit .env file to change the Magento Backend Url
