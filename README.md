[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

# Bookmarklets

## Table of contents
* [Accessibility](#accessibility--validation)
* [Debug](#debug)
* [Fonts](#fonts)
* [Performance](#performance)
* [Search Engine Optimization](#search-engine-optimization)

## Accessibility & Validation
**[a11y.css](https://github.com/ffoodd/a11y.css):** This CSS file intends to warn developers about possible risks and mistakes that exist in HTML code. It can also be used to roughly evaluate a site's quality by simply including it as an external stylesheet.

```
javascript:(function(){a11ycss=document.createElement('LINK');a11ycss.href='https://rawgit.com/ffoodd/a11y.css/master/css/a11y-en.css';a11ycss.rel='stylesheet';a11ycss.media='all';document.body.appendChild(a11ycss);})();
```

**[HTML_CodeSniffer](https://github.com/squizlabs/HTML_CodeSniffer):** HTML_CodeSniffer is a client-side JavaScript that checks a HTML document or source code, and detects violations of a defined coding standard.

```
javascript:(function() {var _p='//squizlabs.github.io/HTML_CodeSniffer/build/';var _i=function(s,cb) {var sc=document.createElement('script');sc.onload = function() {sc.onload = null;sc.onreadystatechange = null;cb.call(this);};sc.onreadystatechange = function(){if(/^(complete|loaded)$/.test(this.readyState) === true){sc.onreadystatechange = null;sc.onload();}};sc.src=s;if (document.head) {document.head.appendChild(sc);} else {document.getElementsByTagName('head')[0].appendChild(sc);}}; var options={path:_p};_i(_p+'HTMLCS.js',function(){HTMLCSAuditor.run('WCAG2AA',null,options);});})();
```

**[Readability Bookmarklet](http://accessibility.oit.ncsu.edu/tools/readability/):** This tool will show you how readable selected text is on a page. The readability guidelines are based on WCAG 2 Level AAA Conformance. Note, there is no readability requirement for WCAG 2, Level AA Conformance. The results are based on six tests.

```
javascript:%20(function()%7Bvar%20yourURL=(window.location.protocol=='http:'?'https://webapps.ncsu.edu/accessibility-readability/readability.php':'https://webapps.ncsu.edu/accessibility-readability/readability.php');function%20getScript(url,success)%7Bvar%20script=document.createElement('script');script.src=url;var%20head=document.getElementsByTagName('head')%5B0%5D,done=false;script.onload=script.onreadystatechange=function()%7Bif(!done&&(!this.readyState%7C%7Cthis.readyState=='loaded'%7C%7Cthis.readyState=='complete'))%7Bdone=true;success();script.onload=script.onreadystatechange=null;head.removeChild(script);%7D%7D;head.appendChild(script);%7D%20getScript(yourURL,function()%7B%7D);%7D)();
```

**[REVENGE.CSS](https://github.com/Heydon/REVENGE.CSS):** The premise of revenge.css is simple: A CSS bookmarklet that uses selectors to find bad markup, displaying ugly pink error messages in comic sans serif wherever you write bad HTML.

```
javascript:(function(){revenge=document.createElement('LINK');revenge.href='https://rawgithub.com/Heydon/REVENGE.CSS/master/revenge.css';revenge.rel='stylesheet';revenge.media='all';document.body.appendChild(revenge);})();
```

**[Web Evaluation Tools Bookmarklet](http://accessibility.oit.ncsu.edu/tools/web-evaluation-tools):** This set of tools allows you to check for several aspects of Web accessibility that other tools do not. It is not designed to replace any other tools, but rather to supplement them.

```
javascript:%20(function()%7Bvar%20yourURL=(window.location.protocol=='http:'?'http://webapps.ncsu.edu/web-evaluation-tools/web-evaluation-tools.php':'https://webapps.ncsu.edu/web-evaluation-tools/web-evaluation-tools.php');function%20getScript(url,success)%7Bvar%20script=document.createElement('script');script.src=url;var%20head=document.getElementsByTagName('head')%5B0%5D,done=false;script.onload=script.onreadystatechange=function()%7Bif(!done&&(!this.readyState%7C%7Cthis.readyState=='loaded'%7C%7Cthis.readyState=='complete'))%7Bdone=true;success();script.onload=script.onreadystatechange=null;head.removeChild(script);%7D%7D;head.appendChild(script);%7D%20getScript(yourURL,function()%7B%7D);%7D)();
```

## Debug
**[CSS Debugger](https://github.com/roykolak/css-debugger):** CSS styles to highlight problematic and malformed html

```
javascript:(function(){document.body.appendChild(document.createElement('script')).src='http://roykolak.github.io/css-debugger/bookmarklet.js';})();
```

**[CSS Layout Debugger](https://gist.github.com/addyosmani/fd3999ea7fce242756b1):** A tweet-sized debugger for visualizing your CSS layouts. Outlines every DOM element on your page a random (valid) CSS hex color.
```
[].forEach.call($$("*"),function(a){a.style.outline="1px solid #"+(~~(Math.random()*(1<<24))).toString(16)})
```

**[debugCSS](https://github.com/yahoo/debugCSS):** debugCSS is meant to be loaded on an existing page to highlight potentially broken, malformed or legacy (X)HTML.

```
javascript:(function(d,i,l){l=d.getElementById(i);if(l){l.parentNode.removeChild(l);return;}l=d.createElement('link');l.id=i;l.rel='stylesheet';l.type='text/css';l.href='//yahoo.github.io/debugCSS/debugCSS.css';d.getElementsByTagName('head')[0].appendChild(l);}(document,'debugCSS'))
```

## Fonts
**[FFFFALLBACK](http://ffffallback.com/):** Web fonts are here, sparking an exciting new era in web design. FFFFALLBACK makes it easy to find the perfect fallback fonts, so that your designs degrade gracefully.

```
javascript:(function() {  var scriptTag = document.createElement('script');  scriptTag.setAttribute('src', 'http://ffffallback.com/#/bookmarklet/ffffallback.js?r=0.8986018379218876');  var linkTag = document.createElement('link');  linkTag.setAttribute('href', 'http://ffffallback.com/#/bookmarklet/ffffallback.css?r=0.747470646398142');  linkTag.setAttribute('rel','stylesheet');  document.body.appendChild(scriptTag);  document.body.appendChild(linkTag);})();
```

**[FontFriend](http://somadesign.ca/projects/fontfriend/):** Font­Friend is a book­marklet for typo­graph­i­cally obsessed web design­ers. It enables rapid check­ing of fonts and font styles directly in the browser with­out edit­ing code and refresh­ing pages, mak­ing it the ideal com­pan­ion for cre­at­ing CSS font stacks.

```
javascript:(function()%20{if(typeof%20jQuery=='undefined'){var%20jqit=document.createElement('script');jqit.type='text/javascript';jqit.src='//ajax.googleapis.com/ajax/libs/jquery/1/jquery.min.js';document.getElementsByTagName('head')[0].appendChild(jqit);}%20_my_script=document.createElement('script');_my_script.type='text/javascript';_my_script.src='//font-friend.googlecode.com/svn/trunk/font-friend.js';document.getElementsByTagName('head')[0].appendChild(_my_script);})();
```

**[Fount](http://fount.artequalswork.com/):** http://fount.artequalswork.com/

```
javascript:(function(){if(!document.getElementById('fountscripton')&&!document.getElementById('fountscript')){var founts=document.createElement('script');founts.src='http://fount.artequalswork.com/fount.js';founts.id='fountscript';document.body.appendChild(founts);}else fountReset(false);})();
```

**[WhatFont](https://github.com/chengyin/WhatFont-Bookmarklet):** WhatFont is a JavaScript script to detect what font in the stack is being used on any elements of a web page.

```
javascript:(function(){var d=document,s=d.createElement('scr'+'ipt'),b=d.body,l=d.location;s.setAttribute('src','http://chengyinliu.com/wf.js?o='+encodeURIComponent(l.href)+'&t='+(new Date().getTime()));b.appendChild(s)})();
```

## Performance
**[CriticalCSS](https://gist.github.com/PaulKinlan/6284142):** CriticalCSS Bookmarklet and Devtool Snippet.js

```
!function(){var a=function(a,b,c){var d=c||{},e={},f=function(a){!!e[a.selectorText]==!1&&(e[a.selectorText]={});for(var b=a.style.cssText.split(/;(?![A-Za-z0-9])/),c=0;c<b.length;c++)if(!!b[c]!=!1){var d=b[c].split(": ");d[0]=d[0].trim(),d[1]=d[1].trim(),e[a.selectorText][d[0]]=d[1]}},g=function(){for(var c=a.innerHeight,e=b.createTreeWalker(b,NodeFilter.SHOW_ELEMENT,function(){return NodeFilter.FILTER_ACCEPT},!0);e.nextNode();){var g=e.currentNode,h=g.getBoundingClientRect();if(h.top<c||d.scanFullPage){var i=a.getMatchedCSSRules(g);if(i)for(var j=0;j<i.length;j++)f(i[j])}}};this.generateCSS=function(){var a="";for(var b in e){a+=b+" { ";for(var c in e[b])a+=c+": "+e[b][c]+"; ";a+="}\n"}return a},g()},b=new a(window,document),c=b.generateCSS();console.log(c)}();
```

**[ CSS Stress Test](https://github.com/andyedinborough/stress-css):** This project is a bookmarklet for stress testing the CSS on any given webpage.
It indexes all the elements and their classes, and then--class by class--it removes one, and times how long it takes to scroll the page. Selectors that save a considerable amount of time when removed indicate problem areas.

```
javascript:(function()%7Bvar%20d=document,s=d.createElement('script'),doit=function()%7Bif(window.stressTest)%7BstressTest.bookmarklet();%7Delse%7BsetTimeout(doit,100);%7D%7D;s.src='https://rawgithub.com/andyedinborough/stress-css/master/stressTest.js?_='%2BMath.random();(d.body%7C%7Cd.getElementsByTagName('head')%5B0%5D).appendChild(s);doit();%7D)();
```

**[pagespeedThis](https://github.com/kimblim/pagespeedThis):** A very simple bookmarklet that analyses the pagespeed of the current page in the browser

```
javascript:window.location='https://developers.google.com/speed/pagespeed/insights/?url='+encodeURI(window.location);
```

**[perfmap](https://github.com/zeman/perfmap):** A bookmarklet to create a front-end performance heatmap of resources loaded in the browser using the Resource Timing API. A browser with support for the Resource Timing API is required.

```
javascript:(function(){var el=document.createElement('script');el.src='https://zeman.github.io/perfmap/perfmap.js';document.body.appendChild(el);})();
```

**[Performance-Bookmarklet](https://github.com/micmro/performance-bookmarklet):** Bookmarklet to analyze the current page through the Resource Timing API, Navigation Timing API and User-Timing - requests by type, domain, load times, marks and more - sort of a light live WebPageTest.

```
javascript:(function(){var el=document.createElement('script');el.type='text/javascript';el.src='https://micmro.github.io/performance-bookmarklet/dist/performanceBookmarklet.min.js';el.onerror=function(){alert("Looks like the Content Security Policy directive is blocking the use of bookmarklets\n\nYou can copy and paste the content of:\n\n\"https://micmro.github.io/performance-bookmarklet/dist/performanceBookmarklet.min.js\"\n\ninto your console instead\n\n(link is in console already)");console.log("https://micmro.github.io/performance-bookmarklet/dist/performanceBookmarklet.min.js");};document.getElementsByTagName('body')[0].appendChild(el);})();
```

**[stats.js](https://github.com/mrdoob/stats.js):** This class provides a simple info box that will help you monitor your code performance. FPS Frames rendered in the last second. The higher the number the better. MS Milliseconds needed to render a frame. The lower the number the better.

```
javascript:(function(){var script=document.createElement('script');script.onload=function(){var stats=new Stats();stats.domElement.style.cssText='position:fixed;left:0;top:0;z-index:10000';document.body.appendChild(stats.domElement);requestAnimationFrame(function loop(){stats.update();requestAnimationFrame(loop)});};script.src='//rawgit.com/mrdoob/stats.js/master/build/stats.min.js';document.head.appendChild(script);})()
```

**[timing.js](https://github.com/addyosmani/timing.js):** Timing.js is a small set of helpers for working with the Navigation Timing API to identify where your application is spending its time. Useful as a standalone script, DevTools Snippet or bookmarklet.

```
javascript:(function(window){"use strict";window.timing=window.timing||{getTimes:function(opts){var performance=window.performance||window.webkitPerformance||window.msPerformance||window.mozPerformance;if(performance===undefined){console.log("Unfortunately, your browser does not support the Navigation Timing API");return}var timing=performance.timing;var api={};opts=opts||{};if(timing){if(opts&&!opts.simple){for(var k in timing){if(timing.hasOwnProperty(k)){api[k]=timing[k]}}}if(api.firstPaint===undefined){var firstPaint=0;if(window.chrome&&window.chrome.loadTimes){firstPaint=window.chrome.loadTimes().firstPaintTime*1e3;api.firstPaintTime=firstPaint-window.chrome.loadTimes().startLoadTime*1e3}else if(typeof window.performance.timing.msFirstPaint==="number"){firstPaint=window.performance.timing.msFirstPaint;api.firstPaintTime=firstPaint-window.performance.timing.navigationStart}if(opts&&!opts.simple){api.firstPaint=firstPaint}}api.loadTime=timing.loadEventEnd-timing.navigationStart;api.domReadyTime=timing.domComplete-timing.domInteractive;api.readyStart=timing.fetchStart-timing.navigationStart;api.redirectTime=timing.redirectEnd-timing.redirectStart;api.appcacheTime=timing.domainLookupStart-timing.fetchStart;api.unloadEventTime=timing.unloadEventEnd-timing.unloadEventStart;api.lookupDomainTime=timing.domainLookupEnd-timing.domainLookupStart;api.connectTime=timing.connectEnd-timing.connectStart;api.requestTime=timing.responseEnd-timing.requestStart;api.initDomTreeTime=timing.domInteractive-timing.responseEnd;api.loadEventTime=timing.loadEventEnd-timing.loadEventStart}return api},printTable:function(opts){var table={};var data=this.getTimes(opts);Object.keys(data).sort().forEach(function(k){table[k]={ms:data[k],s:+(data[k]/1e3).toFixed(2)}});console.table(table)},printSimpleTable:function(){this.printTable({simple:true})}};return window.timing.printSimpleTable()})(this);
```

**[YSLOW](http://yslow.org/):** YSlow analyzes web pages and why they're slow based on Yahoo!'s rules for high performance web sites

```
javascript:(function(y,p,o){p=y.body.appendChild(y.createElement('iframe'));p.id='YSLOW-bookmarklet';p.style.cssText='display:none';o=p.contentWindow.document;o.open().write('<head><body onload="YUI_config={win:window.parent,doc:window.parent.document};var d=document;d.getElementsByTagName(\'head\')[0].appendChild(d.createElement(\'script\')).src=\'http://yslow.org/yslow-bookmarklet.js\'">');o.close()}(document))
```

## Search Engine Optimization
**[OuiSEO](https://github.com/carlsednaoui/seo-bookmarklet):** An open-source bookmarklet that shows you on-page SEO and social meta data information.

```
javascript:(function(){if(window.ouiseo===undefined){var jsCode=document.createElement('script');jsCode.setAttribute('src','//carlsednaoui.s3.amazonaws.com/ouiseo/ouiseo.min.js');document.body.appendChild(jsCode);}else if(!!window.ouiseo&&!document.getElementById('ouiseo')){ouiseo();}else{console.log('ouiseo is already open');}})();
```

**[SEO Bookmarklet](http://twkm.ca/projects/seo-bookmarklet):** A One-Stop SEO Bookmarklet to Quickly Review On-Site SEO

```
javascript:function run(){var d=document,da=new Date(),b=d.body,p=('https:' == document.location.protocol ? 'https://' : 'http://'),ex=d.getElementById('twkmSEOScript');try{if(!b)throw(0);if(!ex){z=d.createElement('scr'+'ipt');z.setAttribute('src',p+'twkm.ca/min/f=gadgets/resources/seo-bookmarklet/seo-stable.js?ts='+da.getTime());z.setAttribute('id','twkmSEOScript');z.setAttribute('class','025');b.appendChild(z);}}catch(e){alert('Please wait until the page has loaded.');}}run();void(0)
```

## License
[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](//creativecommons.org/publicdomain/zero/1.0/)
