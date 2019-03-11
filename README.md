# Preloader

is not a bundler. Intentionally.
This is an experiemnt to find out if a bundler is not actually obsolete.

## The idea

Initiated by [@littledan] at the March 2019 #jslang meetup, my constant discomfort for bundlers, a discussion
with [@bmeurer], [@Jhnnns] and [@lukastaegert] at the [JSKongress] 2019, I wanted to
try out if [modulepreload] and HTTP2 would not be enough to either remove or
at least reduce the (imho) imense complexity of bundlers.

> The modulepreload keyword is a specialized alternative to the preload keyword, with a processing
> model geared toward preloading module scripts.

For example looking like this: `<link rel="modulepreload" href="app.mjs">`

[@Jhnnns]: https://twitter.com/Jhnnns
[@littledan]: https://twitter.com/littledan
[@lukastaegert]: https://twitter.com/lukastaegert
[JSKongress]: https://js-kongress.com/
[@bmeurer]: https://twitter.com/bmeurer
[modulepreload]: https://html.spec.whatwg.org/multipage/links.html#link-type-modulepreload