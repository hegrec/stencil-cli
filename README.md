# Stencil CLI - Stencil Server emulator for local theme development

### Install

`$ npm install -g bigcommerce/stencil-cli`

### Usage

`$ stencil init` - Run this at the top level of your Stencil Theme.  It will ask you a few questions to get your started.  
`$ stencil start` - Run this to start developing your theme.
 - Run with `-o` or `--open` to automatically open up a browser.
 - While stencil is running, you can type `rs` and then hit enter to auto-reload all browsers. This is similar to Nodemon's `rs` option.

### BrowserSync

Stencil CLI comes packaged with BrowserSync so you can take advantage of all of those amazing goodies!  Have a look at their website for more information: http://www.browsersync.io/

### SASS/LESS Compiling

You are able to compile your CSS using either SASS (`node-sass`), LESS, or plain ol' css.  The theme developer can pick which compiler they want to use by editing the theme's `config.json` file and updating the `css_compiler` option to either `scss`, `less`, or `css`.  
There is only one convention you need to follow when choosing the compiler: Place your files in a folder under `./assets` with the same name as your extension.  For example, if you are using `scss`, you would place your `.scss` files in `./assets/scss`.  Stencil CLI will grab each **top level** file that is **not** prefixed and an underscore, compile it to CSS with an inline SourceMap, and then places it in a directory called `./assets/css-artifacts` (this directory should be ignored by Git).  There is a route in the server which serves these CSS Artifacts via `/assets/css/*`.

### Autoprefixer ###

Stencil CLI comes packaged with [Autoprefixer](https://github.com/postcss/autoprefixer).  You can set which browsers that should be targeted as well as if it should cascade the generated rules in the theme's `config.json` file with these options:
 - `autoprefixer_cascade` - Defaults to `true`
 - `autoprefixer_browsers` - Defaults to `["> 5% in US"]`

### How To Get Help or Report A Bug

If you need any help or experience any bugs, please create a GitHub issue in this repo.

### License

Copyright (c) 2015-2016, Bigcommerce Inc.
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:
1. Redistributions of source code must retain the above copyright
   notice, this list of conditions and the following disclaimer.
2. Redistributions in binary form must reproduce the above copyright
   notice, this list of conditions and the following disclaimer in the
   documentation and/or other materials provided with the distribution.
3. All advertising materials mentioning features or use of this software
   must display the following acknowledgement:
   This product includes software developed by Bigcommerce Inc.
4. Neither the name of Bigcommerce Inc. nor the
   names of its contributors may be used to endorse or promote products
   derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY BIGCOMMERCE INC ''AS IS'' AND ANY
EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL BIGCOMMERCE INC BE LIABLE FOR ANY
DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND
ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
