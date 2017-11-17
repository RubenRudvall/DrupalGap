To manually install DrupalGap 8, you can copy/paste these terminal commands once you `cd` into your Drupal root folder (or wherever you want to create the app, just replace `app` with your desired folder name):

```
cd drupal
wget https://github.com/signalpoint/DrupalGap/archive/8.x-1.x.zip || curl -O https://github.com/signalpoint/DrupalGap/archive/8.x-1.x.zip
unzip 8.x-1.x.zip
mv DrupalGap-8.x-1.x/ app
rm 8.x-1.x.zip
cd app
wget https://raw.githubusercontent.com/easystreet3/jDrupal/8.x-1.x/jdrupal.min.js --no-check-certificate || curl -O https://raw.githubusercontent.com/easystreet3/jDrupal/8.x-1.x/jdrupal.min.js
cp default.settings.js settings.js
```

When you're done, the sdk should live here:

```
http://example.com/app/drupalgap.min.js
http://example.com/app/...
...
```

For those not comfortable in a terminal, here's a verbal overview of what needs to be done:

1. Go to your Drupal site's root folder
2. [Download the DrupalGap SDK zip file](https://github.com/signalpoint/DrupalGap/archive/8.x-1.x.zip): 
3. Unzip it to your Drupal site's root folder
4. Rename the folder from `DrupalGap-8.x-1.x` to `app`
5. Go into the `app` folder
6. [Download](https://raw.githubusercontent.com/easystreet3/jDrupal/8.x-1.x/jdrupal.min.js) and save the `jdrupal.min.js` file to the `app` folder

That's it, the DrupalGap SDK should now be installed. Go back to the install page to continue with the instructions.
