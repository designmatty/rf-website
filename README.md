# About

The marketing site for Raster Foundry. The site is built using Jekyll, Gulp, NetlifyCMS and Netlify. This site is based on [https://github.com/NickStees/jekyll-cms](NickStees/jekyll-cms).

# Features at a Glance

- Jekyll static site generation
- [Gulp.js](https://gulpjs.com/) build allows for SASS/SCSS, JS/Babel and image processing.
- Live reloading local development with Browser Sync
- [Netlify CMS integration](https://www.netlifycms.org/) allows editing copy for all pages via a CMS workflow.
- Uses [Jekyll](https://jekyllrb.com/docs/datafiles/) `\_data` to output content like variables across multiple pages, making content easy to maintain.

# Getting started

This project requires first that [Jekyll be installed](https://jekyllrb.com/docs/installation/) along with the [Node.js](https://nodejs.org/en/download/). If its your first time run `gem install jekyll bundler` to install both Jekyll and Bundler locally.

After cloning the project

- run `nvm use && rvm use`
- run `bundle install` to install gem dependencies
- run `npm install` to install npm modules
- run `npm run start` to start live development

## SCSS and JS

The theme and JS files are located in the `/assets/_scss` and `/assets/js` folder. Gulp will process these files and build the sites final CSS and JS files.

## Netlify CMS Integration

The Netlify CMS edits the YAML files in `_data/*`. By allowing the Netlify CMS to edit mainly the `_data` files, you are free to use complex markup on the rest of the site pages (more than markdown provides), and to pull in Netlify CMS managed content you simply tell Jekyll to output {{ site.data.home.title }} which coresponds to the `_data/home.yml` to access the Netlify CMS managed YAMl data.

Each `_pages/*.html` page will need a corresponding \_.yml file that the Netlify CMS will edit. So you can control exactly what the client can edit.

This site also uses some 'Global' yaml files `_data/footer.yml` and `_data/social_media.yml` that can be edited which are like site wide settings that multiple pages use.

## Directories Explained

This is a quick overview of this projects directories, and how they are used.

- **\_data** Jekyll [Data Files](https://jekyllrb.com/docs/datafiles/) which is also what Netlify CMS will mainly edit to update site pages.
- **\_includes** [Reuseable components/partials](https://jekyllrb.com/docs/includes/) that are used across multiple pages
- **\_layouts** Default [Jekyll layouts](https://jekyllrb.com/docs/step-by-step/04-layouts/)
- **\_pages** The site pages are mainly created from these .html files which pull data from the `_data` directory that can be maintained from the Netlify CMS
- **admin** [Netlify CMS configuration](https://www.netlifycms.org/docs/add-to-your-site/)
- **assets** SCSS/JS/img files mainly related to the Theme, processed by Gulp.js
- **uploads** The location Netlify CMS editor [uploads files](https://www.netlifycms.org/docs/configuration-options/#media-library). _Note: these are not optimized by gulp_

## Scripts

<!-- prettier-ignore -->
| Script | Description |
|-|-|
| **`npm run start`** | runs `gulp` default script, which starts browser-sync and watches for changes. Used for local development |
| **`npm run build`** | runs `jekyll clean && gulp build`. Used during the deployment process |
| **`npm run clean`** | runs `jekyll clean` which clears out the jekyll dist |
