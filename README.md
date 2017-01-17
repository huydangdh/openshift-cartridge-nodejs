# Custom Node.js cartridge for OpenShift

![nodejs-openshift](https://cloud.githubusercontent.com/assets/581999/13374525/d25b0a28-dd8f-11e5-86cd-a49b3e698aa5.png)

This is a custom Node.js cartridge that **takes care of auto-updating the Node.js and NPM versions** on each build.

## Why

Because the standard OpenShift cartridge never gets updated to the latest Node.js version.

## When to use

When you need a quick and unsophisticated solution to run your application on the latest Node.js version.

## How to

### The lazy way

Just click here:

[![Create Node.js app on OpenShift](https://launch-shifter.rhcloud.com/launch/Create app on.svg)](https://openshift.redhat.com/app/console/application_type/custom?&cartridges[]https://raw.githubusercontent.com/huydangdh/openshift-cartridge-nodejs/master/metadata/manifest.yml&name=appname)

…or deploy from the [OpenShift Hub Quickstart](https://hub.openshift.com/quickstarts/243-node-js-latest).

### Using [web console](https://openshift.redhat.com/app/console/applications)

Go to [Choose a type of application](https://openshift.redhat.com/app/console/application_types) in your OpenShift Online account, paste the URL below into "Code Anything" textbox at the bottom of the page, click "Next", then set your public URL and click "Create Application".

    https://raw.githubusercontent.com/huydangdh/openshift-cartridge-nodejs/master/metadata/manifest.yml

### Using command line

Assuming you have `rhc` installed (see [here](https://developers.openshift.com/en/managing-client-tools.html)), run:

    rhc app create appname https://raw.githubusercontent.com/huydangdh/openshift-cartridge-nodejs/master/metadata/manifest.yml

…where `appname` is the name of your application.

If you want to create the app with **your own source code** instead of the provided application template, run:

    rhc app create appname \
      https://raw.githubusercontent.com/huydangdh/openshift-cartridge-nodejs/master/metadata/manifest.yml \
      --from-code=https://github.com/you/your-repo.git

…where `https://github.com/you/your-repo.git` is your application repository URL.

Make sure your app has the appropriate `start` entry in `package.json` (see note below).

You can also create an app based on multiple cartridges. For instance, assuming you'd want to include this [custom MongoDB cartridge](https://github.com/icflorescu/openshift-cartridge-mongodb) as well, run:

    rhc app create appname \
      https://raw.githubusercontent.com/huydangdh/openshift-cartridge-nodejs/master/metadata/manifest.yml \
      https://raw.githubusercontent.com/huydangdh/openshift-cartridge-nodejs/master/metadata/manifest.yml

See output of `rhc app create --help` for information on additional options.

## Credits

See contributors [here](https://github.com/icflorescu/openshift-cartridge-nodejs/graphs/contributors).

If you find this repo useful, don't hesitate to give it a star and [spread the word](http://twitter.com/share?text=Checkout%20this%20custom%20Node.js%20cartridge%20for%20OpenShift!&amp;url=http%3A%2F%2Fgithub.com/icflorescu/openshift-cartridge-nodejs&amp;hashtags=javascript,nodejs,openshift&amp;via=icflorescu).

## License

The [ISC License](https://github.com/icflorescu/openshift-cartridge-nodejs/blob/master/LICENSE).
