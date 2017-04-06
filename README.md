# api documentation for  [edit-google-spreadsheet (v0.2.21)](https://github.com/jpillora/node-edit-google-spreadsheet#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-edit-google-spreadsheet.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-edit-google-spreadsheet) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-edit-google-spreadsheet.svg)](https://travis-ci.org/npmdoc/node-npmdoc-edit-google-spreadsheet)
#### > A simple API for reading and writing Google Spreadsheets in Node.js

[![NPM](https://nodei.co/npm/edit-google-spreadsheet.png?downloads=true)](https://www.npmjs.com/package/edit-google-spreadsheet)

[![apidoc](https://npmdoc.github.io/node-npmdoc-edit-google-spreadsheet/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-edit-google-spreadsheet_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-edit-google-spreadsheet/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-edit-google-spreadsheet/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-edit-google-spreadsheet/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "bugs": {
        "url": "https://github.com/jpillora/node-edit-google-spreadsheet/issues"
    },
    "dependencies": {
        "async": "^1.5.0",
        "colors": "^1.0.3",
        "google-auth-library": "^0.9.6",
        "google-oauth-jwt": "~0.1.4",
        "googleclientlogin": "~0.2.8",
        "lodash": "^3.10.1",
        "request": "^2.51.0",
        "xml2js": "^0.4.15"
    },
    "description": "> A simple API for reading and writing Google Spreadsheets in Node.js",
    "devDependencies": {
        "chai": "^3.3.0",
        "mocha": "^2.3.3",
        "mockery": "^1.4.0",
        "sinon": "^1.17.1",
        "sinon-chai": "^2.8.0"
    },
    "directories": {},
    "dist": {
        "shasum": "36a249bb2773c5642b8cba70c31bfb19b421eadc",
        "tarball": "https://registry.npmjs.org/edit-google-spreadsheet/-/edit-google-spreadsheet-0.2.21.tgz"
    },
    "gitHead": "0340ece46ded64d0ed55cdc213dd1257754a7444",
    "homepage": "https://github.com/jpillora/node-edit-google-spreadsheet#readme",
    "maintainers": [
        {
            "name": "jpillora",
            "email": "jpillora@gmail.com"
        }
    ],
    "name": "edit-google-spreadsheet",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/jpillora/node-edit-google-spreadsheet.git"
    },
    "scripts": {
        "test": "mocha test --recursive"
    },
    "version": "0.2.21"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module edit-google-spreadsheet](#apidoc.module.edit-google-spreadsheet)
1.  [function <span class="apidocSignatureSpan">edit-google-spreadsheet.</span>create (opts, callback)](#apidoc.element.edit-google-spreadsheet.create)
1.  [function <span class="apidocSignatureSpan">edit-google-spreadsheet.</span>load (opts, callback)](#apidoc.element.edit-google-spreadsheet.load)
1.  [function <span class="apidocSignatureSpan">edit-google-spreadsheet.</span>metadata (spreadsheet)](#apidoc.element.edit-google-spreadsheet.metadata)
1.  object <span class="apidocSignatureSpan">edit-google-spreadsheet.</span>metadata.prototype
1.  object <span class="apidocSignatureSpan">edit-google-spreadsheet.</span>util

#### [module edit-google-spreadsheet.metadata](#apidoc.module.edit-google-spreadsheet.metadata)
1.  [function <span class="apidocSignatureSpan">edit-google-spreadsheet.</span>metadata (spreadsheet)](#apidoc.element.edit-google-spreadsheet.metadata.metadata)

#### [module edit-google-spreadsheet.metadata.prototype](#apidoc.module.edit-google-spreadsheet.metadata.prototype)
1.  [function <span class="apidocSignatureSpan">edit-google-spreadsheet.metadata.prototype.</span>_set (data, callback)](#apidoc.element.edit-google-spreadsheet.metadata.prototype._set)
1.  [function <span class="apidocSignatureSpan">edit-google-spreadsheet.metadata.prototype.</span>extract (result)](#apidoc.element.edit-google-spreadsheet.metadata.prototype.extract)
1.  [function <span class="apidocSignatureSpan">edit-google-spreadsheet.metadata.prototype.</span>get (callback)](#apidoc.element.edit-google-spreadsheet.metadata.prototype.get)
1.  [function <span class="apidocSignatureSpan">edit-google-spreadsheet.metadata.prototype.</span>set (data, callback)](#apidoc.element.edit-google-spreadsheet.metadata.prototype.set)
1.  [function <span class="apidocSignatureSpan">edit-google-spreadsheet.metadata.prototype.</span>url (isId)](#apidoc.element.edit-google-spreadsheet.metadata.prototype.url)

#### [module edit-google-spreadsheet.util](#apidoc.module.edit-google-spreadsheet.util)
1.  [function <span class="apidocSignatureSpan">edit-google-spreadsheet.util.</span>gcell2cell (cell, getValue, useTextValues)](#apidoc.element.edit-google-spreadsheet.util.gcell2cell)
1.  [function <span class="apidocSignatureSpan">edit-google-spreadsheet.util.</span>int2cell (r, c)](#apidoc.element.edit-google-spreadsheet.util.int2cell)
1.  [function <span class="apidocSignatureSpan">edit-google-spreadsheet.util.</span>num (obj)](#apidoc.element.edit-google-spreadsheet.util.num)



# <a name="apidoc.module.edit-google-spreadsheet"></a>[module edit-google-spreadsheet](#apidoc.module.edit-google-spreadsheet)

#### <a name="apidoc.element.edit-google-spreadsheet.create"></a>[function <span class="apidocSignatureSpan">edit-google-spreadsheet.</span>create (opts, callback)](#apidoc.element.edit-google-spreadsheet.create)
- description and source-code
```javascript
create = function (opts, callback) {
  if (!callback)
    callback = opts.callback;
  if (!callback)
    throw "Missing callback";
  if (!(opts.username && opts.password) && !opts.oauth && !opts.oauth2 && !opts.accessToken)
    return callback("Missing authentication information");
  if (!opts.spreadsheetId && !opts.spreadsheetName)
    return callback("Missing 'spreadsheetId' or 'spreadsheetName'");
  if (!opts.worksheetId && !opts.worksheetName)
    return callback("Missing 'worksheetId' or 'worksheetName'");

  //default to true if useCellTextValues is not set or defined.
  opts.useCellTextValues = (_.has(opts, 'useCellTextValues')) ? opts.useCellTextValues : true;

  var spreadsheet = new Spreadsheet(opts);

  //default to http's' when undefined
  opts.useHTTPS = opts.useHTTPS === false ? '' : 's';
  spreadsheet.protocol += opts.useHTTPS;

  //add to spreadsheet
  _.extend(spreadsheet, _.pick(opts,
    'spreadsheetId', 'spreadsheetName',
    'worksheetId', 'worksheetName', 'debug'
  ));

  spreadsheet.log('Logging into Google...'.grey);
  auth(opts, function(err, token) {
    if (err) return callback(err);
    spreadsheet.log('Logged into Google'.green);
    spreadsheet.setToken(token);
    spreadsheet.init(callback);
  });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.edit-google-spreadsheet.load"></a>[function <span class="apidocSignatureSpan">edit-google-spreadsheet.</span>load (opts, callback)](#apidoc.element.edit-google-spreadsheet.load)
- description and source-code
```javascript
load = function (opts, callback) {
  if (!callback)
    callback = opts.callback;
  if (!callback)
    throw "Missing callback";
  if (!(opts.username && opts.password) && !opts.oauth && !opts.oauth2 && !opts.accessToken)
    return callback("Missing authentication information");
  if (!opts.spreadsheetId && !opts.spreadsheetName)
    return callback("Missing 'spreadsheetId' or 'spreadsheetName'");
  if (!opts.worksheetId && !opts.worksheetName)
    return callback("Missing 'worksheetId' or 'worksheetName'");

  //default to true if useCellTextValues is not set or defined.
  opts.useCellTextValues = (_.has(opts, 'useCellTextValues')) ? opts.useCellTextValues : true;

  var spreadsheet = new Spreadsheet(opts);

  //default to http's' when undefined
  opts.useHTTPS = opts.useHTTPS === false ? '' : 's';
  spreadsheet.protocol += opts.useHTTPS;

  //add to spreadsheet
  _.extend(spreadsheet, _.pick(opts,
    'spreadsheetId', 'spreadsheetName',
    'worksheetId', 'worksheetName', 'debug'
  ));

  spreadsheet.log('Logging into Google...'.grey);
  auth(opts, function(err, token) {
    if (err) return callback(err);
    spreadsheet.log('Logged into Google'.green);
    spreadsheet.setToken(token);
    spreadsheet.init(callback);
  });
}
```
- example usage
```shell
...
#### Basic Usage

Load a spreadsheet:

''' js
  var Spreadsheet = require('edit-google-spreadsheet');

  Spreadsheet.load({
debug: true,
spreadsheetName: 'node-edit-spreadsheet',
worksheetName: 'Sheet1',

// Choose from 1 of the 5 authentication methods:

//    1. Username and Password has been deprecated. OAuth2 is recommended.
...
```

#### <a name="apidoc.element.edit-google-spreadsheet.metadata"></a>[function <span class="apidocSignatureSpan">edit-google-spreadsheet.</span>metadata (spreadsheet)](#apidoc.element.edit-google-spreadsheet.metadata)
- description and source-code
```javascript
metadata = function (spreadsheet){
  this.spreadsheet = spreadsheet;
}
```
- example usage
```shell
...

Get metadata

''' js
  function sheetReady(err, spreadsheet) {
    if(err) throw err;

    spreadsheet.metadata(function(err, metadata){
      if(err) throw err;
      console.log(metadata);
      // { title: 'Sheet3', rowCount: '100', colCount: '20', updated: [Date] }
    });
  }
'''
...
```



# <a name="apidoc.module.edit-google-spreadsheet.metadata"></a>[module edit-google-spreadsheet.metadata](#apidoc.module.edit-google-spreadsheet.metadata)

#### <a name="apidoc.element.edit-google-spreadsheet.metadata.metadata"></a>[function <span class="apidocSignatureSpan">edit-google-spreadsheet.</span>metadata (spreadsheet)](#apidoc.element.edit-google-spreadsheet.metadata.metadata)
- description and source-code
```javascript
metadata = function (spreadsheet){
  this.spreadsheet = spreadsheet;
}
```
- example usage
```shell
...

Get metadata

''' js
  function sheetReady(err, spreadsheet) {
    if(err) throw err;

    spreadsheet.metadata(function(err, metadata){
      if(err) throw err;
      console.log(metadata);
      // { title: 'Sheet3', rowCount: '100', colCount: '20', updated: [Date] }
    });
  }
'''
...
```



# <a name="apidoc.module.edit-google-spreadsheet.metadata.prototype"></a>[module edit-google-spreadsheet.metadata.prototype](#apidoc.module.edit-google-spreadsheet.metadata.prototype)

#### <a name="apidoc.element.edit-google-spreadsheet.metadata.prototype._set"></a>[function <span class="apidocSignatureSpan">edit-google-spreadsheet.metadata.prototype.</span>_set (data, callback)](#apidoc.element.edit-google-spreadsheet.metadata.prototype._set)
- description and source-code
```javascript
_set = function (data, callback) {
  var _this = this;
  var entry = '<entry xmlns="http://www.w3.org/2005/Atom" '+
               'xmlns:gs="http://schemas.google.com/spreadsheets/2006">'+
    '<id>'+this.url(true)+'</id>' +
    '<title>'+data.title+'</title>' +
    '<gs:colCount>'+data.colCount+'</gs:colCount>' +
    '<gs:rowCount>'+data.rowCount+'</gs:rowCount>' +
    '</entry>';

  this.spreadsheet.request({
    method: 'PUT',
    url: this.url(),
    body: entry
  }, function(err, result) {
    if(err) return callback(err);
    callback(null, _this.extract(result));
  });
}
```
- example usage
```shell
...

Metadata.prototype.set = function(data, callback) {
var _this = this;
//must retrieve current col/row counts if missing
if(data.colCount === undefined || data.rowCount === undefined)
  this.get(function(err, metadata) {
    if(err) return callback(err);
    _this._set(_.extend(metadata, data), callback);
  });
else
  _this._set(data, callback);
};

Metadata.prototype._set = function(data, callback) {
var _this = this;
...
```

#### <a name="apidoc.element.edit-google-spreadsheet.metadata.prototype.extract"></a>[function <span class="apidocSignatureSpan">edit-google-spreadsheet.metadata.prototype.</span>extract (result)](#apidoc.element.edit-google-spreadsheet.metadata.prototype.extract)
- description and source-code
```javascript
extract = function (result) {
  return {
    updated: new Date(result.entry.updated),
    title: result.entry.title,
    rowCount: result.entry['gs:rowCount'],
    colCount: result.entry['gs:colCount']
  };
}
```
- example usage
```shell
...

Metadata.prototype.get = function(callback) {
var _this = this;
this.spreadsheet.request({
  url: this.url()
}, function(err, result) {
  if(err) return callback(err);
  callback(null, _this.extract(result));
});
};

Metadata.prototype.set = function(data, callback) {
var _this = this;
//must retrieve current col/row counts if missing
if(data.colCount === undefined || data.rowCount === undefined)
...
```

#### <a name="apidoc.element.edit-google-spreadsheet.metadata.prototype.get"></a>[function <span class="apidocSignatureSpan">edit-google-spreadsheet.metadata.prototype.</span>get (callback)](#apidoc.element.edit-google-spreadsheet.metadata.prototype.get)
- description and source-code
```javascript
get = function (callback) {
  var _this = this;
  this.spreadsheet.request({
    url: this.url()
  }, function(err, result) {
    if(err) return callback(err);
    callback(null, _this.extract(result));
  });
}
```
- example usage
```shell
...
  });
};

Metadata.prototype.set = function(data, callback) {
  var _this = this;
  //must retrieve current col/row counts if missing
  if(data.colCount === undefined || data.rowCount === undefined)
    this.get(function(err, metadata) {
      if(err) return callback(err);
      _this._set(_.extend(metadata, data), callback);
    });
  else
    _this._set(data, callback);
};
...
```

#### <a name="apidoc.element.edit-google-spreadsheet.metadata.prototype.set"></a>[function <span class="apidocSignatureSpan">edit-google-spreadsheet.metadata.prototype.</span>set (data, callback)](#apidoc.element.edit-google-spreadsheet.metadata.prototype.set)
- description and source-code
```javascript
set = function (data, callback) {
  var _this = this;
  //must retrieve current col/row counts if missing
  if(data.colCount === undefined || data.rowCount === undefined)
    this.get(function(err, metadata) {
      if(err) return callback(err);
      _this._set(_.extend(metadata, data), callback);
    });
  else
    _this._set(data, callback);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.edit-google-spreadsheet.metadata.prototype.url"></a>[function <span class="apidocSignatureSpan">edit-google-spreadsheet.metadata.prototype.</span>url (isId)](#apidoc.element.edit-google-spreadsheet.metadata.prototype.url)
- description and source-code
```javascript
url = function (isId) {
  return this.spreadsheet.protocol+'://spreadsheets.google.com/feeds/worksheets/' +
         this.spreadsheet.spreadsheetId + '/' + (isId?'':'private/full/') + this.spreadsheet.worksheetId;
}
```
- example usage
```shell
...
    colCount: result.entry['gs:colCount']
  };
};

Metadata.prototype.get = function(callback) {
  var _this = this;
  this.spreadsheet.request({
    url: this.url()
  }, function(err, result) {
    if(err) return callback(err);
    callback(null, _this.extract(result));
  });
};

Metadata.prototype.set = function(data, callback) {
...
```



# <a name="apidoc.module.edit-google-spreadsheet.util"></a>[module edit-google-spreadsheet.util](#apidoc.module.edit-google-spreadsheet.util)

#### <a name="apidoc.element.edit-google-spreadsheet.util.gcell2cell"></a>[function <span class="apidocSignatureSpan">edit-google-spreadsheet.util.</span>gcell2cell (cell, getValue, useTextValues)](#apidoc.element.edit-google-spreadsheet.util.gcell2cell)
- description and source-code
```javascript
gcell2cell = function (cell, getValue, useTextValues) {
  //get formula AND has a formula?
  if(!getValue && /^=/.test(cell.inputValue)) {
    //must convert '=RC[-2]+R[3]C[-1]' to '=B5+C8'
    return cell.inputValue.replace(/(R(\[(-?\d+)\])?)(C(\[(-?\d+)\])?)/g, function() {
      return exports.int2cell(
          exports.num(cell.row) + exports.num(arguments[3] || 0),
          exports.num(cell.col) + exports.num(arguments[6] || 0)
        );
    });
  }
  //get value
  return (useTextValues) ? exports.num(cell.$t) : exports.num(cell.inputValue);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.edit-google-spreadsheet.util.int2cell"></a>[function <span class="apidocSignatureSpan">edit-google-spreadsheet.util.</span>int2cell (r, c)](#apidoc.element.edit-google-spreadsheet.util.int2cell)
- description and source-code
```javascript
int2cell = function (r, c) {
  return String.fromCharCode(64+c)+r;
}
```
- example usage
```shell
...
};

exports.gcell2cell = function(cell, getValue, useTextValues) {
//get formula AND has a formula?
if(!getValue && /^=/.test(cell.inputValue)) {
  //must convert '=RC[-2]+R[3]C[-1]' to '=B5+C8'
  return cell.inputValue.replace(/(R(\[(-?\d+)\])?)(C(\[(-?\d+)\])?)/g, function() {
    return exports.int2cell(
        exports.num(cell.row) + exports.num(arguments[3] || 0),
        exports.num(cell.col) + exports.num(arguments[6] || 0)
      );
  });
}
//get value
return (useTextValues) ? exports.num(cell.$t) : exports.num(cell.inputValue);
...
```

#### <a name="apidoc.element.edit-google-spreadsheet.util.num"></a>[function <span class="apidocSignatureSpan">edit-google-spreadsheet.util.</span>num (obj)](#apidoc.element.edit-google-spreadsheet.util.num)
- description and source-code
```javascript
num = function (obj) {
  if(obj === undefined) return 0;
  if(typeof obj === 'number' || typeof obj === 'boolean') return obj;
  if(typeof obj === 'string') {
    //ensure that the string is *only* a number
    if(!/^\-?\d+(\.\d+)?$/.test(obj)) return obj;
    var res = parseFloat(obj, 10);
    if(isNaN(res)) return obj;
    return res;
  }
  throw "Invalid number: " + JSON.stringify(obj);
}
```
- example usage
```shell
...

exports.gcell2cell = function(cell, getValue, useTextValues) {
  //get formula AND has a formula?
  if(!getValue && /^=/.test(cell.inputValue)) {
    //must convert '=RC[-2]+R[3]C[-1]' to '=B5+C8'
    return cell.inputValue.replace(/(R(\[(-?\d+)\])?)(C(\[(-?\d+)\])?)/g, function() {
      return exports.int2cell(
          exports.num(cell.row) + exports.num(arguments[3] || 0),
          exports.num(cell.col) + exports.num(arguments[6] || 0)
        );
    });
  }
  //get value
  return (useTextValues) ? exports.num(cell.$t) : exports.num(cell.inputValue);
};
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
