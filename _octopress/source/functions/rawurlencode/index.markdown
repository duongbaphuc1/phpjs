---
layout: page
title: "JavaScript rawurlencode function"
comments: true
sharing: true
footer: true
alias:
- /functions/view/rawurlencode:501
- /functions/view/rawurlencode
- /functions/view/501
- /functions/rawurlencode:501
- /functions/501
---
<!-- Generated by Rakefile:build -->
A JavaScript equivalent of PHP's rawurlencode

{% codeblock url/rawurlencode.js lang:js https://raw.github.com/kvz/phpjs/master/functions/url/rawurlencode.js raw on github %}
function rawurlencode (str) {
  // From: http://phpjs.org/functions
  // +   original by: Brett Zamir (http://brett-zamir.me)
  // +      input by: travc
  // +      input by: Brett Zamir (http://brett-zamir.me)
  // +   bugfixed by: Kevin van Zonneveld (http://kevin.vanzonneveld.net)
  // +      input by: Michael Grier
  // +   bugfixed by: Brett Zamir (http://brett-zamir.me)
  // +      input by: Ratheous
  // +      reimplemented by: Brett Zamir (http://brett-zamir.me)
  // +   bugfixed by: Joris
  // +      reimplemented by: Brett Zamir (http://brett-zamir.me)
  // %          note 1: This reflects PHP 5.3/6.0+ behavior
  // %        note 2: Please be aware that this function expects to encode into UTF-8 encoded strings, as found on
  // %        note 2: pages served as UTF-8
  // *     example 1: rawurlencode('Kevin van Zonneveld!');
  // *     returns 1: 'Kevin%20van%20Zonneveld%21'
  // *     example 2: rawurlencode('http://kevin.vanzonneveld.net/');
  // *     returns 2: 'http%3A%2F%2Fkevin.vanzonneveld.net%2F'
  // *     example 3: rawurlencode('http://www.google.nl/search?q=php.js&ie=utf-8&oe=utf-8&aq=t&rls=com.ubuntu:en-US:unofficial&client=firefox-a');
  // *     returns 3: 'http%3A%2F%2Fwww.google.nl%2Fsearch%3Fq%3Dphp.js%26ie%3Dutf-8%26oe%3Dutf-8%26aq%3Dt%26rls%3Dcom.ubuntu%3Aen-US%3Aunofficial%26client%3Dfirefox-a'
  str = (str + '').toString();

  // Tilde should be allowed unescaped in future versions of PHP (as reflected below), but if you want to reflect current
  // PHP behavior, you would need to add ".replace(/~/g, '%7E');" to the following.
  return encodeURIComponent(str).replace(/!/g, '%21').replace(/'/g, '%27').replace(/\(/g, '%28').
  replace(/\)/g, '%29').replace(/\*/g, '%2A');
}
{% endcodeblock %}

 - [Raw function on GitHub](https://github.com/kvz/phpjs/blob/master/functions/url/rawurlencode.js)

Please note that php.js uses JavaScript objects as substitutes for PHP arrays, they are 
the closest match to this hashtable-like data structure. 

Please also note that php.js offers community built functions and goes by the 
[McDonald's Theory](https://medium.com/what-i-learned-building/9216e1c9da7d). We'll put online 
functions that are far from perfect, in the hopes to spark better contributions. 
Do you have one? Then please just: 

 - [Edit on GitHub](https://github.com/kvz/phpjs/edit/master/functions/url/rawurlencode.js)

### Example 1
This code
{% codeblock lang:js example %}
rawurlencode('Kevin van Zonneveld!');
{% endcodeblock %}

Should return
{% codeblock lang:js returns %}
'Kevin%20van%20Zonneveld%21'
{% endcodeblock %}

### Example 2
This code
{% codeblock lang:js example %}
rawurlencode('http://kevin.vanzonneveld.net/');
{% endcodeblock %}

Should return
{% codeblock lang:js returns %}
'http%3A%2F%2Fkevin.vanzonneveld.net%2F'
{% endcodeblock %}

### Example 3
This code
{% codeblock lang:js example %}
rawurlencode('http://www.google.nl/search?q=php.js&ie=utf-8&oe=utf-8&aq=t&rls=com.ubuntu:en-US:unofficial&client=firefox-a');
{% endcodeblock %}

Should return
{% codeblock lang:js returns %}
'http%3A%2F%2Fwww.google.nl%2Fsearch%3Fq%3Dphp.js%26ie%3Dutf-8%26oe%3Dutf-8%26aq%3Dt%26rls%3Dcom.ubuntu%3Aen-US%3Aunofficial%26client%3Dfirefox-a'
{% endcodeblock %}


### Other PHP functions in the url extension
{% render_partial _includes/custom/url.html %}
