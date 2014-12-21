# TrelloUI Helper Lib v0.0.1

A helper library for extending Trello's UI. You'll have little use for it outside browser extension development.

Currently extremely rudimentary, built for tutorial on SitePoint.com/javascript.

## Functionality and Usage

Currently, the library merely dispatches an event when the #board element has loaded, and/or the .list elements have appeared. This allows you to attach events and UI mods on those elements reliably - Trello's UI is very ajaxy and as such often emits a page ready event before the elements have loaded. This helper library makes that problem go away (for the most part).

To use it, simply include it in your project and then attach listeners for either (or all) of the following events:

- trelloui-boardready
- trelloui-listsready

like so:

```
document.addEventListener('trelloui-boardready', function() {
    console.log("Board is ready!");
});
```

## Contributions

Contributions are welcome - send me your pull requests and I'll take a look at them ASAP. The only rule is: no frameworks. No Angular, no Ember, none of that nonsense. The only allowed third party resource is jQuery, and that's just because Trello's JS client requires it.

Performance is king - if you need to sacrifice code verbosity or DRY principles for performance gains, do it - I'd rather use 1% less CPU than have fully reusable components.

I won't be writing tests because I hate writing JavaScript, but if you want to and know how, feel free, I'll be very grateful.

## License

See [LICENSE](LICENSE.md).

## Todo

- remove jQuery dependency (low priority - the Trello client needs it anyway)
- optimize the interval checker (sometimes uses more CPU than I'd like it to)
- add more events (menusready, avatarsready...?)