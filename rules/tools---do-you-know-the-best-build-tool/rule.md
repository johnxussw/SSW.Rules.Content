---
type: rule
archivedreason: 
title: Tools - Do you know the best Build Tool?
guid: 8ab387eb-94d0-4c05-8f6f-f682238d92db
uri: tools---do-you-know-the-best-build-tool
created: 2016-08-02T14:15:28.0000000Z
authors:
- id: 24
  title: Adam Stephensen
- id: 34
  title: Brendan Richards
related: []

---

Building, bundling and compiling Angular applications can get complicated. You need great build tools.

<!--endintro-->
<dl class="badImage">&lt;dt&gt; <img alt="gulp.png" src="gulp.png"> &lt;/dt&gt;<dd>Figure: Bad Example - Gulp requires hundreds of lines of config to build and bundle Angular applications<br></dd></dl><dl class="goodImage">&lt;dt&gt; <img alt="webpack.png" src="webpack.png"> <br>
   &lt;/dt&gt;<dd>Figure: Good Example - Webpack is an open-source JavaScript module bundler that can be used to build your application (and lots more as well). Teams with advanced build requirements use Webpack. The downside of Webpack is that it requires a large investment in learning Webpack - if it isn't required, the Angular CLI is a better choice</dd></dl><dl class="goodImage">&lt;dt&gt; <img alt="cli.png" src="cli.png" style="width:400px;"> &lt;/dt&gt;<dd>Figure: Good Example - Use the Angular CLI on all new projects that don't require custom Webpack builds. The Angular CLI generates components, routes, services, and pipes, follows best practices as well as building applications for production. The Angular CLI build includes best practices including Tree Shaking and Ahead of Time (AoT) compilation out of the box! The Angular CLI uses Webpack under the covers <br></dd></dl>