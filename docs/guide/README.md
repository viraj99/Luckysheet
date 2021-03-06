# Get started

## Introduction
Luckysheet is an online spreadsheet like excel that is powerful, simple to configure, and completely open source.

### Features
1. Support table settings including freezing columns, merging cells, filtering, sorting, querying, conditional formatting, and annotations
2. Support data analysis functions including pivottables, charts, columns, matrix operations, built-in 385 calculation functions
3. Support one-click screenshots, data copying as json,shared editing, and free data copying and pasting between excel and luckysheet
4. Support mobile viewing
5. Support sparkLine
6. Drop down copy
7. keyboard shortcuts

![Demo](https://minio.cnbabylon.com/public/luckysheet/LuckysheetDemo.gif)


### Demo
[Online demo](https://mengshukeji.github.io/LuckysheetDemo/)

## Development model

### Requirements
[Node.js](https://nodejs.org/en/) Version >= 6 

### Installation
```shell
npm install
npm install gulp -g
```

### Development
```shell
npm run dev
```

### Package
```shell
npm run build
```

## Steps for usage

### First step
After `npm run build`, all files in the `dist` folder are copied to the project directory

### Second step
Introduce dependencies
```html
<link rel='stylesheet' href='./plugins/css/pluginsCss.css' />
<link rel='stylesheet' href='./plugins/plugins.css' />
<link rel='stylesheet' href='./css/luckysheet.css' />
<script src="./plugins/js/plugin.js"></script>
<script src="./luckysheet.umd.js"></script>
```
### Third step
Specify a table container
```html
<div id="luckysheet" style="margin:0px;padding:0px;position:absolute;width:100%;height:100%;left: 0px;top: 0px;"></div>
```
### Fourth step
Create a table
```javascript
<script>
    $(function () {
        //Configuration item
        var options = {
            container: 'luckysheet' //luckysheet is the container id
        }
        luckysheet.create(options)
    })
</script>
```

## Structure

### Format

The data format of a complete Luckysheet table file is: luckysheetfile, a table file contains several sheet files, corresponding to excel sheet0, sheet1, etc.

An example of a Luckysheet file is as follows, the table contains 3 sheets:`
luckysheetfile = [{sheet1 settings}, {sheet2 settings}, {sheet3 settings}]`
Equivalent to 3 sheets of excel

![excel sheet](https://minio.cnbabylon.com/public/luckysheet/excel.png)

An example of a sheet in the file is as follows:
```javascript
luckysheetfile[0] = 
{
	"name": "Cell", //Worksheet name
	"color": "", //Worksheet color
	"config": {}, //Table row height, column width, merged cells, borders, hidden rows and other settings
	"index": "0", //Worksheet index
	"chart": [], //Chart configuration
	"status": "1", //Activation status
	"order": "0", //The order of the worksheet
	"hide": 0,//whether to hide
	"column": 18, //Number of columns
	"row": 36, //number of rows
	"celldata": [], //Original cell data set
	"visibledatarow": [], //The position of all rows
	"visibledatacolumn": [], //The position of all columns
	"ch_width": 2322, //The width of the worksheet area
	"rh_height": 949, //The height of the worksheet area
	"scrollLeft": 0, //Left and right scroll bar position
	"scrollTop": 315, //Up and down scroll bar position
	"luckysheet_select_save": [], //selected area
	"luckysheet_conditionformat_save": {},//Conditional format
	"calcChain": [],//Formula chain
	"isPivotTable":false,//Whether to pivot table
	"pivotTable":{},//Pivot table settings
	"filter_select": null,//Filter range
	"filter": null,//Filter configuration
	"luckysheet_alternateformat_save": [], //Alternate colors
	"luckysheet_alternateformat_save_modelCustom": []//Customize alternate colors
}
```
### View method
View in chrome's console
`luckysheet.getluckysheetfile()`
You can see the complete settings
`[{shee1}, {sheet2}, {sheet3}]`

## Keyboard shortcuts

| Keyboard shortcuts | Features |
| ------------ | ------------ |
|  CTRL + C | Copy cell |
|  CTRL + V | Paste cell |
|  CTRL + X | Cut cell |
|  CTRL + Z | Undo |
|  CTRL + Y | Redo |
|  CTRL + A | Select all |
|  CTRL + B | Bold |
|  CTRL + F | Find |
|  CTRL + H | Replace |
|  CTRL + I | Italic |
|  CTRL + UP/DOWN/LEFT/RIGHT | Quickly adjust cell marquee |
|  SHIFT + UP/DOWN/LEFT/RIGHT | Adjust selection area |
|  CTRL + Left mouse click | Multiple selection cell |
|  SHIFT + Left mouse click | Adjust selection area |
|  UP/DOWN/LEFT/RIGHT | Single move adjustment cell selection box |
|  ENTER | Edit cell |
|  DELETE | Clear cell data |