# Chaise Blog

A simple CouchApp for blogging privately, built on [Angular.js](http://angularjs.org/) and [CouchDB](http://couchdb.apache.org/).

![Chaise Blog](http://eggchair.maxthayer.org/api/couch-therapy.jpg/img)

For those thoughts you want to reflect on alone, lay back on the chaise and relax. Or check out the [demo](http://chaisedemo.maxthayer.org/)!

## Install

Chaise depends on...

* [node.js][nodejs]
* [grunt][grunt]

You'll need those two on your computer. Once you do, run this:
	
	# get the repo
	git clone git@github.com:garbados/chaiseblog.git
	cd chaiseblog
	# install dependencies
	npm install
	# compile JavaScript, CSS, and Jade to our couchapp
	# make sure your couchdb target is running!
	# if your couchdb target requires credentials, enter them in `config.json`
	grunt

Your chaise blog should now live at `http://localhost:5984/chaise-admin/_design/chaiseblog/_rewrite`. You can use [virtual hosts](http://couchdb.readthedocs.org/en/latest/configuring.html?highlight=virtual#virtual-hosts) to make that a prettier URL.

## Configuration

Chaise uses `config.json` to store settings, such as...

* `jade`: Template variables, like the blog's title.
* `couchapp`: URL for the remote CouchDB, and path to a node.couchapp settings file. To push somewhere remote, like [Cloudant][cloudant], set `db`.

[nodejs]: http://nodejs.org/
[grunt]: http://gruntjs.com/
[cloudant]: https://cloudant.com/

## Taking it Public!

Diaries are cool, but what if you want to share your ramblings with the world? Chaise has you covered.

In `config.json` there's a `public` field which tells Chaise where to push a public version of the site. By default, it pushes to `http://localhost:5984/chaise-public`. The interface doesn't expose any means of altering your data, thus eliminating random clicking as an attack vector. Take that, black hats!

If you're hosting your public site on a Cloudant database, remember to make the database publicly readable through the Permissions tab!

## License

The MIT License (MIT)

Copyright (c) 2013 Maximilian Alexander Dunn Thayer

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
