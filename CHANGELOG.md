# Changelog

Newest first. These version numbers match the [releases page](https://github.com/hardlysleeping/xExtension-FavoriteCategories/releases).

**1.4.1** — the pin button stops colliding with a sibling's button in subscription management.

FreshRSS styles *every* `.btn` inside a category box's header as an absolutely positioned toggle — that
rule is written for the stats page's +/- buttons, but it also catches anything injected into
`div.box-title` on the subscription page. Two extensions that each add a button there therefore land
on the same spot (`right: 1rem`) and render intersecting and clipped. The pin now pins itself back into
the text flow: a selector one class more specific than core's, plus `!important` on `position`, `right`
and `top`, so neither a later core rule nor a theme that restyles `.box-title .btn` can put it back on
top of a neighbour.

Layout only. No migration, no settings, nothing changes on upgrade.

**1.4.0** — pinned categories only, and the name to match.

The extension is **Pinned Categories**. A pin sorts a category to the top of the sidebar behind a
pushpin, with the original order restored when it is unpinned, and one button narrows the sidebar
and the stream down to the pinned categories — or to everything except them. Feed visibility is
never touched outside Strict mode, so this can run alone or beside a category-hiding extension.

Pinning and the button's own state are callable from outside the settings form
(`setCategoryFavorite()`, `changeView()`), and each returns the state the server actually holds
rather than what was asked for, so a client and the form cannot drift apart. The first call now
answers with usable state instead of an empty reply, and failures come back as machine codes.

**1.3.2** and earlier — settings form layout, dim instead of hide, star or pin with shorter labels:
see the [releases page](https://github.com/hardlysleeping/xExtension-FavoriteCategories/releases).
