Frango - A FRontend and backend djANGO project template
=======================================================

Now frontend and backend will not live togheter anymore. Frango use by
default Gulp to automate your frontend tasks, creating a familiar enviroment 
for frontend developers who works with Django as backend framework.

System dependences
------------------

First of all, dependences. This is what Frango need from your system:

- NodeJS
- NPM
- Bower
- Gulp 

### Ubuntu setup

Install dependences:

```
curl -sL https://deb.nodesource.com/setup_4.x | sudo -E bash -
sudo apt-get install nodejs
sudo npm install -g npm 
sudo npm install -g gulp-cli bower
```

Start new Frango project
------------------------

To start a new Django project using Frango:

```
pip install django
django-admin startproject --template=https://github.com/hersonls/frango/archive/master.zip myproject
cd myproject
make config
```

Backend
-------

### Development server

Frango come with a django frontend app witch will suport you
with several features, like management command to run developement server
wich will manage a BrowserSync process for you and some helpfull 
templatetags.

To run development server with BrowserSync proxy:

```
cd myproject/backend
python manage.py server
```

Frontend
--------

All the frontend files now live in ```frontend``` directory. The files here are
famliliar to all frontend developers. The main directores is:

- ***static*** - All static files for project like: images, styles, scripts and fonts.
- ***templates*** - All project templates
- ***dist*** - All build files for production. This directory will be generated by ```gulp build``` command.
- ***.tmp*** - All runtime files generated by development server. Like output from sass and javascript from babel.

### Frontend features

By default, frontend is automated by [Gulp](http://gulpjs.com/). This is which tasks Frango has by default:

- [BrowserSync]() - Here's pleasure, now all your test browser will be automatically updated when any changes happen.
- [sass](https://www.npmjs.com/package/gulp-sass) - Compile automaticaly all sass files.
- [babel](https://www.npmjs.com/package/gulp-babel) - Now you can write ES6 without worry about browser support.
- [autoprefixer](https://www.npmjs.com/package/gulp-autoprefixer) - You don't need to remember all browser support tags, this task will add for you.
- [cssnano](https://www.npmjs.com/package/cssnano) - This task will make your css small as possible.
- [eslit](https://www.npmjs.com/package/gulp-eslint) - If you make something wrong in your Javascript, this task will make you know about it.
- [imagemin](https://www.npmjs.com/package/gulp-imagemin) - If your image has pixel wich you don't need, this will remove for you.
- [sourcemaps](https://www.npmjs.com/package/gulp-sourcemaps) - You need to be remembered where your source code live, this task will create a map for you.
- [wiredep](https://www.npmjs.com/package/gulp-wiredep) - Dude, you don't need to put your dependences by yourself, this will put for in your html or sass files after execute bower install. 
- [uglify](https://www.npmjs.com/package/gulp-uglify) - This task is what you need to minify your javascript. 
- [useref](https://www.npmjs.com/package/gulp-useref) - This task will help you concatenate your files easily. 

All this stuff is run automatically by default in your development server.

### Create a distribution build

To create a distribute build you need to execute the gulp build task:

```
cd myproject/frontend
gulp build
```

This task will create a ```dist``` folder with all minified and compressed files.

TO-DO
-----

- Test, test and more test.
- Feedback from frontend nation.
- Improve npm speed and a better strategy for first install of dependency in deployment proccess.
- Improve django management command for manage gulp process. Gulp process is restart always django
  server is restarted.
- Documentation.
