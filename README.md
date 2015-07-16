# JSBuilder2
JavaScript project builder from ExtJS (Sencha)

This project was created by ExtJS development team to build their project like ExtJS and ext_core.
Later it is evolved to [Sencha Cmd][1] project.

At this moment Sencha assumed that project is obsolete and removed it from site.
But some old project still require it for build - for example, ext_core (is obsolete too :))

# Usage
For example, I build ext_core project with JSBuilder2

At first, check out project files [from SVN][2]:
    $ svn checkout http://svn.extjs.com/svn/ext-core/trunk ext_core
    $ cd ext_core

Then build it:
    $ java -jar /path/to/JSBuilder2.jar -p ext-core.jsb2 -d .

After execution will be created ext-core-3.3.0 directory with compiled library files and resources

Used in this example config file is in JSON format and very simple and self-describing:

    {
	    "projectName": "Ext Core",
	    "deployDir": "ext-core-3.3.0",
	    "licenseText": "Ext Core Library $version&#xD;&#xA;http://extjs.com/&#xD;&#xA;Copyright(c) 2006-2009, $author.&#xD;&#xA;&#xD;&#xA;The MIT License&#xD;&#xA;&#xD;&#xA;Permission is hereby granted, free of charge, to any person obtaining a copy&#xD;&#xA;of this software and associated documentation files (the &quot;Software&quot;), to deal&#xD;&#xA;in the Software without restriction, including without limitation the rights&#xD;&#xA;to use, copy, modify, merge, publish, distribute, sublicense, and/or sell&#xD;&#xA;copies of the Software, and to permit persons to whom the Software is&#xD;&#xA;furnished to do so, subject to the following conditions:&#xD;&#xA;&#xD;&#xA;The above copyright notice and this permission notice shall be included in&#xD;&#xA;all copies or substantial portions of the Software.&#xD;&#xA;&#xD;&#xA;THE SOFTWARE IS PROVIDED &quot;AS IS&quot;, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR&#xD;&#xA;IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,&#xD;&#xA;FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE&#xD;&#xA;AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER&#xD;&#xA;LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,&#xD;&#xA;OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN&#xD;&#xA;THE SOFTWARE.&#xD;&#xA;",
	    "pkgs": [{
	        "name": "Ext Base",
	        "file": "ext-base.js",
	        "isDebug": true,
	        "fileIncludes": [{
	            "text": "Ext.js",
	            "path": "src/core/"
	        },{
	            "text": "TaskMgr.js",
	            "path": "src/util/"
	        },{
	            "text": "ext-base-begin.js",
	            "path": "src/adapter/"
	        },{
	            "text": "ext-base-dom.js",
	            "path": "src/adapter/"
	        },{
	            "text": "ext-base-event.js",
	            "path": "src/adapter/"
	        },{
	            "text": "ext-base-ajax.js",
	            "path": "src/adapter/"
	        },{
	            "text": "ext-base-anim.js",
	            "path": "src/adapter/"
	        },{
	            "text": "ext-base-anim-extra.js",
	            "path": "src/adapter/"
	        },{
	            "text": "ext-base-end.js",
	            "path": "src/adapter/"
	        }]
	    },{
	        "name": "Ext Core",
	        "file": "ext-core.js",
	        "isDebug": true,
	        "pkgDeps": ["ext-base.js"],
	        "includeDependencies": true,
	        "fileIncludes": [{
	            "text": "Observable.js",
	            "path": "src/util/"
	        },{
	            "text": "DomHelper.js",
	            "path": "src/core/"
	        },{
	            "text": "Template.js",
	            "path": "src/core/"
	        },{
	            "text": "DomQuery.js",
	            "path": "src/core/"
	        },{
	            "text": "DelayedTask.js",
	            "path": "src/util/"
	        },{
	            "text": "EventManager.js",
	            "path": "src/core/"
	        },{
	            "text": "Element.js",
	            "path": "src/core/"
	        },{
	            "text": "Element.traversal.js",
	            "path": "src/core/"
	        },{
	            "text": "Element.insertion.js",
	            "path": "src/core/"
	        },{
	            "text": "Element.style.js",
	            "path": "src/core/"
	        },{
	            "text": "Element.position.js",
	            "path": "src/core/"
	        },{
	            "text": "Element.scroll.js",
	            "path": "src/core/"
	        },{
	            "text": "Element.fx.js",
	            "path": "src/core/"
	        },{
	            "text": "Fx.js",
	            "path": "src/core/"
	        },{
	            "text": "CompositeElementLite.js",
	            "path": "src/core/"
	        },{
	            "text": "Connection.js",
	            "path": "src/data/"
	        },{
	            "text": "JSON.js",
	            "path": "src/util/"
	        },{
	            "text": "Loader.js",
	            "path": "src/core/"
	        }]
	    }],
	    "resources": [{
	        "src": "src/",
	        "dest": "src/",
	        "filters": ".*\\.js"
	    },{
	        "src": "examples/",
	        "dest": "examples/",
	        "filters": ".*[\\.html|\\.jpg|\\.png|\\.gif|\\.css|\\.js|\\.php]"
	    },{
	        "src": "ext-core.jsb2",
	        "dest": "ext-core.jsb2",
	        "filters": ".*"
	    }]
	}

# How to build

To build this project You need to install [Maven tool][3]. After that build is simple and easy:
    $ cd /path/to/JSBuilder2
    $ mvn package

After build finished will be created ``target`` directory containing ``jsbuilder2-1.0-jar-with-dependencies.jar`` file.
You can rename it or copy in any place and use it.

[1]: https://www.sencha.com/products/extjs/cmd-download/
[2]: https://www.sencha.com/forum/showthread.php?122963-Ext-core-download-location-missing-on-new-site
[3]: https://maven.apache.org/
