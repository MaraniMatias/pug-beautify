# Pug(former jade) beautify
This tiny program format a pug(former jade) template file.
For reusability, it's made as a module suggested by [@Glavin001](https://github.com/Glavin001), [@MaraniMatias](https://github.com/MaraniMatias) added some functions.

## Installation
```shell
npm install pug_formatter
```

__Global__

```shell
npm install -g pug_formatter
```

## Test
```shell
npm run test
```
### Options
* fill_tab - boolean, fill whether tab or space, default true.
* omit_div - boolean, whether omit 'div' tag, default false.
* tab_size - number, when 'fill_tab' is false, fill 'tab_size' spaces, default 4.
* separator_space - boolean, When 'separator_space' is true, the attribute separator is comma, default true.
* omit_empty_lines - When 'separator_space' is false, delete line blank, default true.

## How to use
__NodeJS__
```javascript
var output = pugBeautify(code);
```
```javascript
var output = pugBeautify(code,{fill_tab:true,omit_div:false,tab_size:4,separator_space:true});
```
__Shell__
```shell
pugformat -h
pugformat -o '{"tab_size":4}' ./index.pug
```

## Example code
```javascript
var fs = require('fs');
var pugBeautify = require('pug_formatter');
var code = fs.readFileSync('sample.jade','utf8');
var option = {
    fill_tab: true,
    omit_div: false,
    tab_size: 4,
    separator_space: true,
    omit_empty_lines : false
};
try {
    var output = pugBeautify(code,option);
}catch(error){
    // Error occurred
}
```
