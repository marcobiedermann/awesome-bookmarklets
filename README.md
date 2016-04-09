# Bookmarklets

## Table of contents
* [Accessibility](#accessibility--validation)
* [Debug](#debug)
* [Fonts](#fonts)
* [Performance](#performance)
* [Search Engine Optimization](#search-engine-optimization)
* [Miscellaneous](#miscellaneous)

## Accessibility & Validation
**[a11y.css](https://github.com/ffoodd/a11y.css):** This CSS file intends to warn developers about possible risks and mistakes that exist in HTML code. It can also be used to roughly evaluate a site's quality by simply including it as an external stylesheet.

```javascript
javascript:(function(d){'use strict';var a11ycss=d.createElement('link');a11ycss.href='https://rawgit.com/ffoodd/a11y.css/master/css/a11y-en.css';a11ycss.rel='stylesheet';a11ycss.media='all';(d.body||d.getElementsByTagName('body')[0]).appendChild(a11ycss);})(document);
```

**[HTML_CodeSniffer](https://github.com/squizlabs/HTML_CodeSniffer):** HTML_CodeSniffer is a client-side JavaScript that checks a HTML document or source code, and detects violations of a defined coding standard.

```javascript
javascript:(function(d){'use strict';var _p='https://squizlabs.github.io/HTML_CodeSniffer/build/',options={path:_p};function _i(s,cb){var sc=d.createElement('script');sc.onload=function(){sc.onload=null;sc.onreadystatechange=null;cb.call(this);};sc.onreadystatechange=function(){if(/^(complete|loaded)$/.test(this.readyState)===true){sc.onreadystatechange=null;sc.onload();}};sc.src=s;(d.head||d.getElementsByTagName('head')[0]).appendChild(sc);}_i(_p+'HTMLCS.js',function(){HTMLCSAuditor.run('WCAG2AA',null,options);});})(document);
```

**[Readability Bookmarklet](http://accessibility.oit.ncsu.edu/tools/readability/):** This tool will show you how readable selected text is on a page. The readability guidelines are based on WCAG 2 Level AAA Conformance. Note, there is no readability requirement for WCAG 2, Level AA Conformance. The results are based on six tests.

```javascript
javascript:(function(d){'use strict';var yourURL='https://webapps.ncsu.edu/accessibility-readability/readability.php';function getScript(url,success){var script=d.createElement('script'),head=d.head||d.getElementsByTagName('head')[0],done=false;script.src=url;script.onload=script.onreadystatechange=function(){if(!done&&(!this.readyState||this.readyState==='loaded'||this.readyState==='complete')){done=true;success();script.onload=script.onreadystatechange=null;head.removeChild(script);}}head.appendChild(script);}getScript(yourURL,function(){});})(document);
```

**[REVENGE.CSS](https://github.com/Heydon/REVENGE.CSS):** The premise of revenge.css is simple: A CSS bookmarklet that uses selectors to find bad markup, displaying ugly pink error messages in comic sans serif wherever you write bad HTML.

```javascript
javascript:(function(d){'use strict';var revenge=d.createElement('link');revenge.href='https://rawgit.com/Heydon/REVENGE.CSS/master/revenge.css';revenge.rel='stylesheet';revenge.media='all';(d.body||d.getElementsByTagName('body')[0]).appendChild(revenge);})(document);
```

**[Web Evaluation Tools Bookmarklet](http://accessibility.oit.ncsu.edu/tools/web-evaluation-tools):** This set of tools allows you to check for several aspects of Web accessibility that other tools do not. It is not designed to replace any other tools, but rather to supplement them.

```javascript
javascript:(function(d){'use strict';var yourURL='https://webapps.ncsu.edu/web-evaluation-tools/web-evaluation-tools.php';function getScript(url,success){var script=d.createElement('script'),head=d.head||d.getElementsByTagName('head')[0],done=false;script.src=url;script.onload=script.onreadystatechange=function(){if(!done&&(!this.readyState||this.readyState==='loaded'||this.readyState==='complete')){done=true;success();script.onload=script.onreadystatechange=null;head.removeChild(script);}};head.appendChild(script);}getScript(yourURL,function(){});})(document);
```

## Debug

**[45-75](https://css-tricks.com/bookmarklet-colorize-text-45-75-characters-line-length-testing/):** Check whether lines are between 45 and 75 characers, for optimal readability; this especially helps with font sizing for responsive web design.

```javascript
javascript:(function(d){'use strict';var loadScript;function init(){var redOutline={outline:'2px solid red'},text,textyElements='p,li,dt,dd,h1,h2,h3,h4,h5,h6';$(textyElements).on('mouseover.red',function(){$(this).css(redOutline);}).on('mouseleave.red',function(){$(this).removeAttr('style');}).on('click.red',function(){text=$(this).text();var e=text.substring(0,45),t=text.substring(45,75),n=text.substring(75,text.length),r=e+'<span style="color:red;">'+t+'</span>'+n;$(this).html(r);$(textyElements).off('mouseover.red mouseleave.red click.red');$(this).removeAttr('style');});}if(typeof jQuery==='undefined'){loadScript=function loadScript(a,b){var c=d.createElement('script'),head=d.head||d.getElementsByTagName('head')[0],done=false;c.type='text/javascript';c.src=a;c.onload=c.onreadystatechange=function(){if(!done&&(!this.readyState||this.readyState==='loaded'||this.readyState==='complete')){done=true;b();}};head.appendChild(c)};loadScript('https://cdn.jsdelivr.net/jquery/1.12.3/jquery.min.js',init);}else init();})(document);
```

**[CSS Debugger](https://github.com/roykolak/css-debugger):** CSS styles to highlight problematic and malformed html

```javascript
javascript:(function(d){'use strict';(d.body||d.getElementsByTagName('body')[0]).appendChild(d.createElement('script')).src='https://roykolak.github.io/css-debugger/bookmarklet.js';})(document);
```

**[CSS Layout Debugger](https://gist.github.com/addyosmani/fd3999ea7fce242756b1):** A tweet-sized debugger for visualizing your CSS layouts. Outlines every DOM element on your page a random (valid) CSS hex color.
```javascript
javascript:(function(d){'use strict';var elts=(d.body||d.getElementsByTagName('body')[0]).getElementsByTagName('*'),i=elts.length;while(i--)elts[i].style.outline='1px solid #'+(~~(Math.random()*(1<<24))).toString(16);})(document);
```

**[Debug CSS](https://gist.github.com/ozgrozer/91e8b759a1aaff39d9d5#file-debugcss-js)**

```javascript
javascript:(function(d){'use strict';var s=d.createElement('style'),e=d.getElementById('debugCss');;s.id='debugCss';s.innerHTML='*{background-color: rgba(0, 0, 0, .05) !important;outline: 1px solid #fff !important;}';if(null==e)(d.head||d.getElementsByTagName('head')[0]).appendChild(s);else e.parentNode.removeChild(e);})(document);
```

**[Yahoo! debugCSS](https://github.com/yahoo/debugCSS):** debugCSS is meant to be loaded on an existing page to highlight potentially broken, malformed or legacy (X)HTML.

```javascript
javascript:(function(d,i){'use strict';var l=d.getElementById(i);if(l){l.parentNode.removeChild(l);return;}l=d.createElement('link');l.id=i;l.rel='stylesheet';l.type='text/css';l.href='https://yahoo.github.io/debugCSS/debugCSS.css';(d.head||d.getElementsByTagName('head')[0]).appendChild(l);})(document,'debugCSS');
```

## Fonts
**[FFFFALLBACK](http://ffffallback.com/):** Web fonts are here, sparking an exciting new era in web design. FFFFALLBACK makes it easy to find the perfect fallback fonts, so that your designs degrade gracefully.

```javascript
javascript:(function(d){'use strict';var body=d.body||d.getElementsByTagName('body')[0],scriptTag=d.createElement('script'),linkTag=d.createElement('link');scriptTag.setAttribute('src','https://rawgit.com/jbrewer/ffffallback/master/bookmarklet/ffffallback.js');linkTag.setAttribute('href','https://rawgit.com/jbrewer/ffffallback/master/bookmarklet/ffffallback.css');linkTag.setAttribute('rel','stylesheet');body.appendChild(scriptTag);body.appendChild(linkTag);})(document);
```

**[FontFriend](http://somadesign.ca/projects/fontfriend/):** Font­Friend is a book­marklet for typo­graph­i­cally obsessed web design­ers. It enables rapid check­ing of fonts and font styles directly in the browser with­out edit­ing code and refresh­ing pages, mak­ing it the ideal com­pan­ion for cre­at­ing CSS font stacks.

```javascript
javascript:(function(d){'use strict';var head=d.head||d.getElementsByTagName('head')[0],_my_script=d.createElement('script'),jqit;if(typeof jQuery==='undefined'){jqit=d.createElement('script');jqit.type='text/javascript';jqit.src='https://cdn.jsdelivr.net/jquery/1.12.3/jquery.min.js';head.appendChild(jqit);}_my_script.type='text/javascript';_my_script.src='https://rawgit.com/lewisje/font-friend/master/font-friend.js';head.appendChild(_my_script);})(document);
```

**[Fount](http://fount.artequalswork.com/):** Identify webfonts on any site.

```javascript
javascript:(function(d){'use strict';if(!d.getElementById('fountscripton')&&!d.getElementById('fountscript')){var founts=d.createElement('script');founts.src='http://fount.artequalswork.com/fount.js';founts.id='fountscript';(d.body||d.getElementsByTagName('body')[0]).appendChild(founts);}else fountReset(false);})(document);
```

**[Flippant](http://flippant.artequalswork.com/):** View any site from all angles.

```javascript
javascript:(function(d){'use strict';if(!d.getElementById('flippantscript')){var flipscript=d.createElement('script');flipscript.src='http://flippant.artequalswork.com/flippant.js';flipscript.id='flippantscript';(d.body||d.getElementsByTagName('body')[0]).appendChild(flipscript);}else flippant();})(document);
```

**[MIN](http://min.artequalswork.com/):** Basic looks at type and layout.

```javascript
javascript:(function(d){'use strict';if(!d.getElementById('minscript')){var minscript=d.createElement('script');minscript.src='http://min.artequalswork.com/min.js';minscript.id='minscript';(d.body||d.getElementsByTagName('body')[0]).appendChild(minscript);}else m();})(document);
```

**[WhatFont](https://github.com/chengyin/WhatFont-Bookmarklet):** WhatFont is a JavaScript script to detect what font in the stack is being used on any elements of a web page.

```javascript
javascript:(function(d){'use strict';var s=d.createElement('script'),b=(d.body||d.getElementsByTagName('body')[0]),l=d.location;s.setAttribute('src','http://chengyinliu.com/wf.js?o='+encodeURIComponent(l.href)+'&t='+(new Date().getTime()));b.appendChild(s)})(document);
```

## Performance
**[CriticalCSS](https://gist.github.com/PaulKinlan/6284142):** CriticalCSS Bookmarklet and Devtool Snippet.js

```javascript
javascript:(function(win,doc){'use strict';function CSSCriticalPath(w,d,opts){var opt=opts||{},css={},splitRegex=/;(?![A-Za-z0-9])/;function pushCSS(r){if(!css[r.selectorText])css[r.selectorText]={};var styles=r.style.cssText.split(splitRegex);for(var i=0;i<styles.length;i++){if(!styles[i])continue;var pair=styles[i].split(': ');pair[0]=pair[0].trim();pair[1]=pair[1].trim();css[r.selectorText][pair[0]]=pair[1];}}function parseTree(){var height=w.innerHeight,walker=d.createTreeWalker(d,NodeFilter.SHOW_ELEMENT,function(node){return NodeFilter.FILTER_ACCEPT;},true);while(walker.nextNode()){var node=walker.currentNode,rect=node.getBoundingClientRect();if(rect.top<height||opt.scanFullPage){var rules=w.getMatchedCSSRules(node);if(!!rules)for(var r=0;r<rules.length;r++)pushCSS(rules[r]);}}}this.generateCSS=function(){var finalCSS='';for(var k in css)if(css.hasOwnProperty(k)){finalCSS+=k+' { ';for (var j in css[k])if(css[k].hasOwnProperty(j))finalCSS+=j+': '+css[k][j]+';';finalCSS+='}\n';}return finalCSS;};parseTree();}var cp=new CSSCriticalPath(win,doc),css=cp.generateCSS();console.log(css);return false;})(this,document);
```

**[ CSS Stress Test](https://github.com/andyedinborough/stress-css):** This project is a bookmarklet for stress testing the CSS on any given webpage.
It indexes all the elements and their classes, and then--class by class--it removes one, and times how long it takes to scroll the page. Selectors that save a considerable amount of time when removed indicate problem areas.

```javascript
javascript:(function(d){'use strict';var s=d.createElement('script');function doit(){if(typeof stressTest!=='undefined')stressTest.bookmarklet();else setTimeout(doit,100);}s.src='https://rawgit.com/andyedinborough/stress-css/master/stressTest.js?_='+Math.random();(d.head||d.getElementsByTagName('head')[0]).appendChild(s);doit();})(document);
```

**[pagespeedThis](https://github.com/kimblim/pagespeedThis):** A very simple bookmarklet that analyses the pagespeed of the current page in the browser

```javascript
javascript:window.location='https://developers.google.com/speed/pagespeed/insights/?url='+encodeURI(window.location);
```

**[perfmap](https://github.com/zeman/perfmap):** A bookmarklet to create a front-end performance heatmap of resources loaded in the browser using the Resource Timing API. A browser with support for the Resource Timing API is required.

```javascript
javascript:(function(d){var el=d.createElement('script');el.src='https://zeman.github.io/perfmap/perfmap.js';(d.body||d.getElementsByTagName('body')[0]).appendChild(el);})(document);
```

**[Performance-Bookmarklet](https://github.com/micmro/performance-bookmarklet):** Bookmarklet to analyze the current page through the Resource Timing API, Navigation Timing API and User-Timing - requests by type, domain, load times, marks and more - sort of a light live WebPageTest.

```javascript
javascript:(function(d){var l='https://micmro.github.io/performance-bookmarklet/dist/performanceBookmarklet.min.js',el=d.createElement('script');el.type='text/javascript';el.src=l;el.onerror=function(){alert('Looks like the Content Security Policy directive is blocking the use of bookmarklets\n\nYou can copy and paste the content of\n\n"+l+"\n\ninto your console instead\n\n(link is in console already)');console.log(l);};(d.body||d.getElementsByTagName('body')[0]).appendChild(el);})(document);
```

**[stats.js](https://github.com/mrdoob/stats.js):** This class provides a simple info box that will help you monitor your code performance. FPS Frames rendered in the last second. The higher the number the better. MS Milliseconds needed to render a frame. The lower the number the better.

```javascript
javascript:(function(d){'use strict';var raf=typeof requestAnimationFrame==='function'?requestAnimationFrame:function(f){return setTimeout(f,15);},s=d.createElement('script');s.onload=function(){var s=new Stats();function loop(){s.update();raf(loop)}s.domElement.style.cssText='position:fixed;left:0;top:0;z-index:10000';(d.body||d.getElementsByTagName('body')[0]).appendChild(s.domElement);raf(loop);};s.src='https://rawgit.com/mrdoob/stats.js/master/build/stats.min.js';(d.head||d.getElementsByTagName('head')[0]).appendChild(s);})(document);
```

**[timing.js](https://github.com/addyosmani/timing.js):** Timing.js is a small set of helpers for working with the Navigation Timing API to identify where your application is spending its time. Useful as a standalone script, DevTools Snippet or bookmarklet.

```javascript
javascript:(function(w){'use strict';w.timing=w.timing||{getTimes:function(opt){var p=w.performance||w.webkitPerformance||w.msPerformance||w.mozPerformance;if(!p){console.log('Unfortunately, your browser does not support the Navigation Timing API');return;}var timing=p.timing,api={},o=opt||{},k,f;if(timing){if(o&&!o.simple)for(k in timing)if(timing.hasOwnProperty(k))api[k]=timing[k];if(null==api.firstPaint){f=0;if(w.chrome&&w.chrome.loadTimes){f=w.chrome.loadTimes().firstPaintTime*1e3;api.firstPaintTime=f-w.chrome.loadTimes().startLoadTime*1e3;}else if(typeof p.timing.msFirstPaint==='number'){f=p.timing.msFirstPaint;api.firstPaintTime=f-p.timing.navigationStart;}if(o&&!o.simple)api.firstPaint=f}api.loadTime=timing.loadEventEnd-timing.navigationStart;api.domReadyTime=timing.domComplete-timing.domInteractive;api.readyStart=timing.fetchStart-timing.navigationStart;api.redirectTime=timing.redirectEnd-timing.redirectStart;api.appcacheTime=timing.domainLookupStart-timing.fetchStart;api.unloadEventTime=timing.unloadEventEnd-timing.unloadEventStart;api.lookupDomainTime=timing.domainLookupEnd-timing.domainLookupStart;api.connectTime=timing.connectEnd-timing.connectStart;api.requestTime=timing.responseEnd-timing.requestStart;api.initDomTreeTime=timing.domInteractive-timing.responseEnd;api.loadEventTime=timing.loadEventEnd-timing.loadEventStart;}return api;},printTable:function(opts){var table={},data=this.getTimes(opts);Object.keys(data).sort().forEach(function(k){table[k]={ms:data[k],s:+(data[k]/1e3).toFixed(2)};});console.table(table)},printSimpleTable:function(){this.printTable({simple:true});}};return w.timing.printSimpleTable();})(this);
```

**[YSLOW](http://yslow.org/):** YSlow analyzes web pages and why they're slow based on Yahoo!'s rules for high performance web sites

```javascript
javascript:(function(y){'use strict';var b=y.body||y.getElementsByTagName('body')[0],p=b.appendChild(y.createElement('iframe')),o=p.contentWindow.document;p.id='YSLOW-bookmarklet';p.style.cssText='display:none';o.open().write('<head></head><body onload="YUI_config={win:window.parent,doc:window.parent.document};var d=document;(d.head||d.getElementsByTagName(\'head\')[0]).appendChild(d.createElement(\'script\')).src=\'http://yslow.org/yslow-bookmarklet.js\'"></body>');o.close();})(document);
```

## Search Engine Optimization
**[OuiSEO](https://github.com/carlsednaoui/seo-bookmarklet):** An open-source bookmarklet that shows you on-page SEO and social metadata information.

```javascript
javascript:(function(d){if(typeof ouiseo==='undefined'){var jsCode=d.createElement('script');jsCode.setAttribute('src','https://carlsednaoui.s3.amazonaws.com/ouiseo/ouiseo.min.js');(d.body||d.getElementsByTagName('body')[0]).appendChild(jsCode);}else if(ouiseo&&!d.getElementById('ouiseo')){ouiseo();}else console.log('OuiSEO is already open');})(document);
```

**[SEO Bookmarklet](http://twkm.ca/projects/seo-bookmarklet):** A One-Stop SEO Bookmarklet to Quickly Review On-Site SEO

```javascript
javascript:(function(d){'use strict';var da=new Date(),b=d.body||d.getElementsByTagName('body')[0],ex=d.getElementById('twkmSEOScript'),z;try{if(!b)throw new ReferenceError('The body has not loaded yet.');if(!ex){z=d.createElement('script');z.setAttribute('src','https://twkm.ca/min/f=gadgets/resources/seo-bookmarklet/seo-stable.js?ts='+da.getTime());z.setAttribute('id','twkmSEOScript');z.setAttribute('class','03');b.appendChild(z);}else twkm_closeThisBox();}catch(_){console.log(_.message);}})(document);
```

Beta Version

```javascript
javascript:(function(d){'use strict';var da=new Date(),b=d.body||d.getElementsByTagName('body')[0],ex=d.getElementById('twkmSEOScript'),z;try{if(!b)throw new ReferenceError('The body has not loaded yet.');if(!ex){z=d.createElement('script');z.setAttribute('src','https://twkm.ca/min/f=gadgets/resources/seo-bookmarklet/seo-latest.js?ts='+da.getTime());z.setAttribute('id','twkmSEOScript');z.setAttribute('class','03');b.appendChild(z);}else twkm_closeThisBox();}catch(_){console.log(_.message);}})(document);
```

## Miscellaneous
**[ThemeForest Live Preview](https://gist.github.com/ozgrozer/91e8b759a1aaff39d9d5#file-themeforestlivepreview-js):**

```javascript
javascript:(function(d){'use strict';var u=d.URL,a=d.createElement('a'),v=['themeforest.net','www.themeforest.net'],l,s;a.href=u;if(v.indexOf(a.hostname)!==-1){l=d.getElementsByClassName('btn-icon live-preview')[0].href;s=document.createElement('script');s.src='https://akillidergi.com/app/themeforest/findNextURL.js?url='+encodeURIComponent(l);if(!(d.head||d.getElementsByTagName('head')[0]).appendChild(s))console.warn("Script tag couldn't be created!");}else console.error('This bookmarklet only runs on Themeforest pages.');})(document);
```
