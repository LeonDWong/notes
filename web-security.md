## XSS

#### What

Known as **Cross-Site Scripting**. It can harm your web while some script running without user's consciousness. Like web load a image tag like `<img onError="alert(window.document.cookie)" src="233"/>`, and it will print user's cookie, it definitely leak user's privacy, and could even cause property damage.

#### How

Like img and script tag, even some data can also make XSS.

#### RESOLUTION

Avoid to insert unstrusted data to html. It u need, try serialize it before you take it to you web. Some tool like [Yahoo/xss-filters](https://github.com/yahoo/xss-filters) can help you in a convinient way. And also developer can use [CSP(Content-Security-Policy)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy) or [X-XXS-Protection](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-XSS-Protection) to prevent XSS attack.
> NOTE: CSP is better than X-XSS-Protection, but CSP won't work once the browser doesn't support it(like IE and Edge below 15, etc....). 

## CSRF

#### What

Known as **Cross-Site Request Forgery**. It can harm your property by open a new tab which is requesting some critical operation, like transaction or payment.

#### How

Image you have already logged in site **www.bank.com**, and then you open a new tab which access **www.malicious.com**. And **www.malicious.com** offer a ad link that direct to **www.bank.com/transfer?receiver=XXXX&money=XXXXX**. And you click it and access the link, then the link will be request with your session information in this site **www.bank.com**. And transaction complete, you lost your money.....

#### RESOLUTION

**CSRF** only work once server believe the request is coming from the exact user, and hacker doesn't know your session information at all. So, you can make your server to judge whether the request is coming from you deliberately. So your can make those critical operation request with post method(hmmmm, restful win), and add some header like **X-CSRF-Token** or somewhat, and server check the header that cant be send without knowing the session information. Pass or not pass, it's not a question ))))))))))

## OTHERS

#### X-Content-Type-Options

This header prevents "mime" based attacks. This header prevents Internet Explorer from MIME-sniffing a response away from the declared content-type as the header instructs the browser not to override the response content type. With the nosniff option, if the server says the content is text/html, the browser will render it as text/html.

#### X-Frame-Options

The **X-Frame-Options** HTTP response header can be used to indicate whether or not a browser should be allowed to render a page in a `<frame>`, `<iframe>` or `<object>` . Sites can use this to avoid **clickjacking** attacks, by ensuring that their content is not embedded into other sites.

> X-Frame-Options: DENY
> X-Frame-Options: SAMEORIGIN
> X-Frame-Options: ALLOW-FROM https://example.com/

#### Strict-Transport-Security

The HTTP **Strict-Transport-Security** response header (often abbreviated as HSTS)  lets a web site tell browsers that it should only be accessed using HTTPS, instead of using HTTP.(using in https site)

> Strict-Transport-Security: max-age=<expire-time>
> Strict-Transport-Security: max-age=<expire-time>; includeSubDomains
> Strict-Transport-Security: max-age=<expire-time>; preload

#### rel=noopener

A link can open a web in new tab usually looks like `<a href="http://new.link.com" target="_blank"></a>` in **site a**, when user click it, a new web in new tab occurs. Hmmmmm, everything fine yet. But you print `console.log(window.opener.document.cookie)` in browser console, and cookie of **site a** is printed in console, even `alert(1)` is working for **site a** too.
Avoiding potential security vulnerability, you can define the link tag with **rel=noopener**`<a href="http://new.link.com" target="_blank" rel="noopener"></a>`. And the `console.log(window.opener)` will output `null`. Cool, even you want to support MS's browser(`noopener won't work for ie and edge`), you can add `rel="noopener norefer"` as well(no refer in header for new link webpage). Besides, javascript support is available.

> var otherWindow = window.open();
> otherWindow.opener = null;
> otherWindow.location = url;

