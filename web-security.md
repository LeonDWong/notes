## XSS

#### What

Known as **Cross-Site Scripting**. It can harm your web while some script running without user's consciousness. Like web load a image tag like `<img onError="alert(window.document.cookie)" src="233"/>`, and it will print user's cookie, it definitely leak user's privacy, and could even cause property damage.

#### HOW

Like img and script tag, even some data can also make XSS.

#### AGAINST

Avoid to insert unstrusted data to html. It u need, try serialize it before you take it to you web. Some tool like [Yahoo/xss-filters](https://github.com/yahoo/xss-filters) can help you in a comfort way. And also    