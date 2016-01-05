# grunt-resize-crop [![Build Status](https://travis-ci.org/traviswimer/grunt-resize-crop.png?branch=master)](https://travis-ci.org/traviswimer/grunt-resize-crop)

> Make images a specific size without distorting the aspect ratio. Resizes as close as possible and crops the rest.

_This plugin is a wrapper for [resize-crop](https://github.com/traviswimer/resize-crop.js)_

## Getting Started
This plugin requires [Grunt](http://gruntjs.com/) `~0.4.4` -- [Learn to use Grunt](http://gruntjs.com/getting-started)

Install the plugin with this command:

```shell
brew install imagemagick
npm install @aftership/grunt-resize-crop --save-dev
```

Enable in your Gruntfile with:

```js
grunt.loadNpmTasks('grunt-resize-crop');
```


## The "resize_crop" task

In your project's Gruntfile, add a section named `resize_crop` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig({
  resize_crop: {
    image_group: {
      options: {
        gravity: "center",
        height: 200,
        width: 200
      },
      files: [{
        expand: true, // Enable dynamic expansion.
        cwd: 'img/src', // Src matches are relative to this path.
        src: ['**/*_[0-9].jpg'], // Actual pattern(s) to match.
        dest: 'img/dist' // Destination path prefix.
      }]
    }
  }
});
```

## Options

### options.height

* REQUIRED OPTION
* Type: `integer`
* Description: Sets the height in pixels to be used for the output image.

### options.width

* REQUIRED OPTION
* Type: `integer`
* Description: Sets the width in pixels to be used for the output image.

### options.gravity

* Type: `string`
* Description: Determines the part of the image that will be removed during cropping. For example, `"center"` will try to keep the centermost part of the image and only remove the furthest edges.

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [Grunt](http://gruntjs.com/).
