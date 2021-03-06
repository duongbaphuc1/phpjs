---
layout: page
title: "JavaScript rtrim function"
comments: true
sharing: true
footer: true
alias:
- /functions/view/rtrim:507
- /functions/view/rtrim
- /functions/view/507
- /functions/rtrim:507
- /functions/507
---
<!-- Generated by Rakefile:build -->
A JavaScript equivalent of PHP's rtrim

{% codeblock strings/rtrim.js lang:js https://raw.github.com/kvz/phpjs/master/functions/strings/rtrim.js raw on github %}
function rtrim (str, charlist) {
  // From: http://phpjs.org/functions
  // +   original by: Kevin van Zonneveld (http://kevin.vanzonneveld.net)
  // +      input by: Erkekjetter
  // +   improved by: Kevin van Zonneveld (http://kevin.vanzonneveld.net)
  // +   bugfixed by: Onno Marsman
  // +   input by: rem
  // +   bugfixed by: Brett Zamir (http://brett-zamir.me)
  // *     example 1: rtrim('    Kevin van Zonneveld    ');
  // *     returns 1: '    Kevin van Zonneveld'
  charlist = !charlist ? ' \\s\u00A0' : (charlist + '').replace(/([\[\]\(\)\.\?\/\*\{\}\+\$\^\:])/g, '\\$1');
  var re = new RegExp('[' + charlist + ']+$', 'g');
  return (str + '').replace(re, '');
}
{% endcodeblock %}

 - [Raw function on GitHub](https://github.com/kvz/phpjs/blob/master/functions/strings/rtrim.js)

Please note that php.js uses JavaScript objects as substitutes for PHP arrays, they are 
the closest match to this hashtable-like data structure. 

Please also note that php.js offers community built functions and goes by the 
[McDonald's Theory](https://medium.com/what-i-learned-building/9216e1c9da7d). We'll put online 
functions that are far from perfect, in the hopes to spark better contributions. 
Do you have one? Then please just: 

 - [Edit on GitHub](https://github.com/kvz/phpjs/edit/master/functions/strings/rtrim.js)

### Example 1
This code
{% codeblock lang:js example %}
rtrim('    Kevin van Zonneveld    ');
{% endcodeblock %}

Should return
{% codeblock lang:js returns %}
'    Kevin van Zonneveld'
{% endcodeblock %}


### Other PHP functions in the strings extension
{% render_partial _includes/custom/strings.html %}
