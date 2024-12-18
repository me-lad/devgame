# Getting Started

If you just want to see the project demo use the link below<br />
[**Demo**](https://me-lad.github.io/devgame/)

## Installation

To get started with this project, you'll need to have
**Node.js** and **Npm** installed on your system. if you already have them do the fallowing steps.<br />

1. Clone the repo<br />

   ```
   git clone https://github.com/me-lad/devgame
   ```

2. Run npm install to install the required packages

   ```
    npm install
   ```

3. If you see any problom with **sass** commands you need to use dart-sass instead of node-sass that is no longer supported and also change all **@import** commands with **@use** and change the scripts we`ve been using. 👇

   - Removing the node-sass

   ```
    npm uninstall node-sass
   ```

   - Installing dart-sass

   ```
    npm i sass -D
   ```

   - Changing the scripts in **package.json**<br />
     change 👇

   ```
    scripts: {
        "watch:sass": "node-sass sass/main.scss public/css/style.css -w"
        "compress:css": "node-sass public/css/style.prefix.css public/css/style.min.css --output-style compressed",
    }
   ```

   to 👇

   ```
    scripts: {
       "watch:sass": "sass sass/main.scss public/css/style.css -w"
       "compress:css": "sass public/css/style.prefix.css public/css/style.min.css --style=compressed",
    }
   ```

   - Changing **@import** commands in **main.scss**, like this 👇

   ```
    change

    @import "base/reset";

    with

    @use "base/reset"; or @use "base/reset" as *;
   ```
