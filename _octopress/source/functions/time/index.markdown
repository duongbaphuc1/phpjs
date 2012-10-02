---
layout: page
title: "JavaScript time function"
comments: true
sharing: true
footer: true
alias:
- /functions/time:562
- /functions/562
---
A JavaScript equivalent of PHP's time

{% codeblock datetime/time.js lang:js https://raw.github.com/kvz/phpjs/master/functions/datetime/time.js raw on github %}
function time () {
    // http://kevin.vanzonneveld.net
    // +   original by: GeekFG (http://geekfg.blogspot.com)
    // +   improved by: Kevin van Zonneveld (http://kevin.vanzonneveld.net)
    // +   improved by: metjay
    // +   improved by: HKM
    // *     example 1: timeStamp = time();
    // *     results 1: timeStamp > 1000000000 && timeStamp < 2000000000
    return Math.floor(new Date().getTime() / 1000);
}
{% endcodeblock %}

 - [view on github](https://github.com/kvz/phpjs/blob/master/functions/datetime/time.js)
 - [edit on github](https://github.com/kvz/phpjs/edit/master/functions/datetime/time.js)