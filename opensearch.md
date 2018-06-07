It's link tag for browser to defined the page as a search page, in chrome, it also can be add to search engineer as well.

Example: `<link rel="search" type="application/opensearchdescription+xml" title="Stack Overflow" href="/opensearch.xml" />`

XML: 
  ```xml
      <OpenSearchDescription xmlns="http://a9.com/-/spec/opensearch/1.1/" xmlns:moz="http://www.mozilla.org/2006/browser/search/">
    <ShortName>Stack Overflow</ShortName>
    <Description>
    Search Stack Overflow: Q&A for professional and enthusiast programmers
    </Description>
    <InputEncoding>UTF-8</InputEncoding>
    <Image width="16" height="16" type="image/x-icon">
    https://cdn.sstatic.net/Sites/stackoverflow/img/favicon.ico?v=4f32ecc8f43d
    </Image>
    <Url type="text/html" method="get" template="http://stackoverflow.com/search?q={searchTerms}"/>
    </OpenSearchDescription>
    var long_domains = ['.com.cn', '.net.cn', '.com.hk','.co.id','.com.ph','.com.my','.co.th'];function isEndWith(s1, s2) {var l1 = s1.length, l2 = s2.length;return l1 >= l2 && s1.indexOf(s2) == (l1 - l2);};function any(arr, fn) {var i;var l = arr.length;for (i = 0; i < l; i++) {if (fn(arr[i])) {return true;}}return false;};function getDomain(full_domain) {var a = full_domain.split('.');var l = a.length;var top;if (any(long_domains,function(d) {return isEndWith(full_domain, d);})) {top = a.slice(l - 3);} else {top = a.slice(l - 2);}return top.join('.');};function setCookie(name, val, options) {if (!options) {options = {};}val += '; domain=' + (options.domain ? options.domain : getDomain(location.hostname));val += '; path=' + (options.path ? options.path : '/');document.cookie = name + '=' + val;};function getCookie(key) {var cookie_val = document.cookie.match(new RegExp('(?:^|;)\\s*' + key + '=([^;]+)'));return cookie_val ? cookie_val[1] : '';};if( getCookie('udata-terminal') === 'phone'){setCookie('udata-terminal',null);window.location.reload();}
  ```

 
 