# boilerplate-v2.0

## Installed webpack
- Installed webpack and webpack-cli
- Added a start script in package.json which calls webpack
- Made an index.js file, which is the file webpack looks for by default
- Webpack spits out our code in dist/main.js by default
- Currently our main app code has nothing to do with webpack, but it will soon

## Webpack now bundling all our app code
- We use import/export to indicate dependencies
- Webpack makes sure everything loads in the correct order
- We can remove all our additional script tags in index.html

## Add webpack config file
- Created webpack.config.js
- Added some basic configuration
- Modified package.json, so that webpack uses our config file

## Add first loaders to handle css
- Installed style-loader and css-loader
- Configured webpack.config to use both loaders on css files
- Remember the order we use them in webpack.config matters

## Add Sass loader, override bootstrap colors
- Changed our main.css to main.scss
- Installed bootstrap locally so we can tweak it
- Installed sass-loader and node-sass
- Updated webpack.config file to include a .scss rule

## Cache busting and HtmlWebpackPlugin
- Configured webpack to use contentHash in bundle file name
- This caused a problem with out script tag in index.html
- We installed HtmlWebpackPlugin to help us generate a new index.html
- It automatically includes the correct script tag at the bottom
- We created a template file that we passed in called template.html
- We deleted the original index.html because we don't need it anymore
- Make sure you are opening dist/index.html now to view the app

## Add prod and dev configs, dev-server
- Broke our webpack.config file into 3 files
- webpack.common.js, webpack.dev.js, and webpack.prod.js
- installed webpack-merge to share the common functionality
- updated our package.json to use the new config files
- installed webpack-dev-server and added it to start script in package.json

## Add html-loader, file-loader, and clean-webpack-plugin
- Added html-loader to automatically require the files we reference in img tags
- Added file-loader to handle the svg,png,jpg,gif files from our images
- Configured file-loader to add our images to an imgs directory in dist
- Also configured it to add a hash to their filenames
- Lastly, added clean-webpack-plugin to our production config to clean out the dist directory each time we build

## Add entrypoint for vendor js file, add bootstrap js
- Now we have 2 entry files and 2 bundles
- The vendor file houses code that is less likely to change, 3rd party libraries
- The main file has all of our app code

## Add babel to transpile js code into compatible code
- installed babel using @babel/preset-env
- add babel config to the production config file

## Minify JS, CSS, and HTML in production
- Extracted CSS into own file in production
- Minified CSS in production
- Added TerserJS back in to minify JS in production
- Minified HTML in production as well
