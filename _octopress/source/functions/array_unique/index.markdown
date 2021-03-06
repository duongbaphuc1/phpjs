---
layout: page
title: "JavaScript array_unique function"
comments: true
sharing: true
footer: true
alias:
- /functions/view/array_unique:346
- /functions/view/array_unique
- /functions/view/346
- /functions/array_unique:346
- /functions/346
---
<!-- Generated by Rakefile:build -->
A JavaScript equivalent of PHP's array_unique

{% codeblock array/array_unique.js lang:js https://raw.github.com/kvz/phpjs/master/functions/array/array_unique.js raw on github %}
function array_unique (inputArr) {
  // From: http://phpjs.org/functions
  // +   original by: Carlos R. L. Rodrigues (http://www.jsfromhell.com)
  // +      input by: duncan
  // +   bugfixed by: Kevin van Zonneveld (http://kevin.vanzonneveld.net)
  // +   bugfixed by: Nate
  // +      input by: Brett Zamir (http://brett-zamir.me)
  // +   bugfixed by: Kevin van Zonneveld (http://kevin.vanzonneveld.net)
  // +   improved by: Michael Grier
  // +   bugfixed by: Brett Zamir (http://brett-zamir.me)
  // %          note 1: The second argument, sort_flags is not implemented;
  // %          note 1: also should be sorted (asort?) first according to docs
  // *     example 1: array_unique(['Kevin','Kevin','van','Zonneveld','Kevin']);
  // *     returns 1: {0: 'Kevin', 2: 'van', 3: 'Zonneveld'}
  // *     example 2: array_unique({'a': 'green', 0: 'red', 'b': 'green', 1: 'blue', 2: 'red'});
  // *     returns 2: {a: 'green', 0: 'red', 1: 'blue'}
  var key = '',
    tmp_arr2 = {},
    val = '';

  var __array_search = function (needle, haystack) {
    var fkey = '';
    for (fkey in haystack) {
      if (haystack.hasOwnProperty(fkey)) {
        if ((haystack[fkey] + '') === (needle + '')) {
          return fkey;
        }
      }
    }
    return false;
  };

  for (key in inputArr) {
    if (inputArr.hasOwnProperty(key)) {
      val = inputArr[key];
      if (false === __array_search(val, tmp_arr2)) {
        tmp_arr2[key] = val;
      }
    }
  }

  return tmp_arr2;
}
{% endcodeblock %}

 - [Raw function on GitHub](https://github.com/kvz/phpjs/blob/master/functions/array/array_unique.js)

Please note that php.js uses JavaScript objects as substitutes for PHP arrays, they are 
the closest match to this hashtable-like data structure. 

Please also note that php.js offers community built functions and goes by the 
[McDonald's Theory](https://medium.com/what-i-learned-building/9216e1c9da7d). We'll put online 
functions that are far from perfect, in the hopes to spark better contributions. 
Do you have one? Then please just: 

 - [Edit on GitHub](https://github.com/kvz/phpjs/edit/master/functions/array/array_unique.js)

### Example 1
This code
{% codeblock lang:js example %}
array_unique(['Kevin','Kevin','van','Zonneveld','Kevin']);
{% endcodeblock %}

Should return
{% codeblock lang:js returns %}
{0: 'Kevin', 2: 'van', 3: 'Zonneveld'}
{% endcodeblock %}

### Example 2
This code
{% codeblock lang:js example %}
array_unique({'a': 'green', 0: 'red', 'b': 'green', 1: 'blue', 2: 'red'});
{% endcodeblock %}

Should return
{% codeblock lang:js returns %}
{a: 'green', 0: 'red', 1: 'blue'}
{% endcodeblock %}


### Other PHP functions in the array extension
{% render_partial _includes/custom/array.html %}
