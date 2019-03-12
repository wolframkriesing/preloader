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

## So what does it do?

The intention is to use the standard web technologies for most of what bundlers do today.
1) Use HTTP2 for loading all of the modules (javascript files), assuming that it's
overhead for loading multiple files is small enough.
2) Generate a list of modules to preload, so that every `import` is faster by finding
the files already preloaded in the browser.
3) Maybe at some later stage the list of preloaded files for various entry points can be compared
and commonalities can be put into one file, so that even less gets loaded.

In the end for all above stands: ONLY NUMBERS COUNT. MEASURE IT.
