# My Firefox is pretty odd looking!

I have a side bar with Favicons only, I use VIM navigations keys and the top bar autohides because we are set in fullscreen mode at all times.

![](firefox.png)

Firstly, install FireFox, log in to your account. Type 'about:config' in address bar and agree to warning. Use search bar to find 'toolkit.legacyUserProfileCustomizations.stylesheets.' set this value to true. Close FireFox.

In ~/.mozilla/firefox there will now be a filder with a bunch of random looking numbers and letters. This is your profile folder. You may have more than one if you use any profile managing addons.

From this repo copy chome/userChrome.css (yes, that upper case C matters) into the profile folder. The file address should look like this /home/[username]/.mozilla/firefox/[profile]/chrome/userChrome.css

Now you need my addons/extensions (what are they called now? I don't care... moving on)

[AutoFullscreen](https://addons.mozilla.org/en-GB/firefox/addon/autofullscreen/?src=search)

[Hide-Scrollbars](https://addons.mozilla.org/en-GB/firefox/addon/hide-scrollbars/)

[Tab Center Reborn](https://addons.mozilla.org/en-GB/firefox/addon/tabcenter-reborn/)

[Vim Vixen](https://addons.mozilla.org/en-GB/firefox/addon/vim-vixen/)

I use a bunch more addons but these are the ones to make your firefox look and behave like mine. Others I recommend are Privacy Badger, HTTPS everywhere, uBlock Origin, PassFF (also requires local packages) and AutoPin. That said, addons are ALWAYS security holes. Think for your self!

Go to extensions settings (Guess they calling them extensions then, solved!) and select manage on Tab Center Reborn. Scroll down to Custom Stylesheet and tick the box. Now put the following squiggles into the box

	body .tab .tab-icon {
	  filter: url('data:image/svg+xml;,<svg xmlns="http://www.w3.org/2000/svg"><filter id="s"><feColorMatrix type="matrix" values="0 0 0 0 1 0 0 0 0 1 0 0 0 0 1 -0.2125 -0.7154 -0.0721 1 0" /><feMorphology operator="dilate" radius="1"/><feComponentTransfer><feFuncA type="gamma" offset="0" amplitude="1" exponent="2"/></feComponentTransfer><feGaussianBlur stdDeviation="0.5"/><feComposite in="SourceGraphic" operator="over"/></filter></svg>#s');
	}

Now if you want my Vim Vixen shortcuts you need to click Manage > preferences on that one too. Now select 'Use plain JSON' and put the below in the box. - There is sort of a lot!

*Note: if there is anything in the box already, delete it first*

	{
	  "keymaps": {
	    "0": { "type": "scroll.home" },
	    ":": { "type": "command.show" },
	    "o": { "type": "command.show.open", "alter": false },
	    "O": { "type": "command.show.open", "alter": true },
	    "t": { "type": "command.show.tabopen", "alter": false },
	    "T": { "type": "command.show.tabopen", "alter": true },
	    "w": { "type": "command.show.winopen", "alter": false },
	    "W": { "type": "command.show.winopen", "alter": true },
	    "b": { "type": "command.show.buffer" },
	    "a": { "type": "command.show.addbookmark", "alter": true },
	    "k": { "type": "scroll.vertically", "count": -1 },
	    "j": { "type": "scroll.vertically", "count": 1 },
	    "h": { "type": "scroll.horizonally", "count": -1 },
	    "l": { "type": "scroll.horizonally", "count": 1 },
	    "<C-U>": { "type": "scroll.pages", "count": -0.5 },
	    "<C-D>": { "type": "scroll.pages", "count": 0.5 },
	    "<C-B>": { "type": "scroll.pages", "count": -1 },
	    "<C-F>": { "type": "scroll.pages", "count": 1 },
	    "gg": { "type": "scroll.top" },
	    "G": { "type": "scroll.bottom" },
	    "$": { "type": "scroll.end" },
	    "d": { "type": "tabs.close" },
	    "D": { "type": "tabs.close", "select": "left" },
	    "x$": { "type": "tabs.close.right" },
	    "!d": { "type": "tabs.close.force" },
	    "u": { "type": "tabs.reopen" },
	    "K": { "type": "tabs.prev" },
	    "J": { "type": "tabs.next" },
	    "gT": { "type": "tabs.prev" },
	    "gt": { "type": "tabs.next" },
	    "g0": { "type": "tabs.first" },
	    "g$": { "type": "tabs.last" },
	    "<C-6>": { "type": "tabs.prevsel" },
	    "r": { "type": "tabs.reload", "cache": false },
	    "R": { "type": "tabs.reload", "cache": true },
	    "zp": { "type": "tabs.pin.toggle" },
	    "zd": { "type": "tabs.duplicate" },
	    "zi": { "type": "zoom.in" },
	    "zo": { "type": "zoom.out" },
	    "zz": { "type": "zoom.neutral" },
	    "f": { "type": "follow.start", "newTab": false },
	    "F": { "type": "follow.start", "newTab": true, "background": false },
	    "m": { "type": "mark.set.prefix" },
	    "'": { "type": "mark.jump.prefix" },
	    "H": { "type": "navigate.history.prev" },
	    "L": { "type": "navigate.history.next" },
	    "[[": { "type": "navigate.link.prev" },
	    "]]": { "type": "navigate.link.next" },
	    "gu": { "type": "navigate.parent" },
	    "gU": { "type": "navigate.root" },
	    "gi": { "type": "focus.input" },
	    "gf": { "type": "page.source" },
	    "gh": { "type": "page.home" },
	    "gH": { "type": "page.home", "newTab": true },
	    "y": { "type": "urls.yank" },
	    "p": { "type": "urls.paste", "newTab": false },
	    "P": { "type": "urls.paste", "newTab": true },
	    "/": { "type": "find.start" },
	    "n": { "type": "find.next" },
	    "N": { "type": "find.prev" },
	    ".": { "type": "repeat.last" },
	    "<S-Esc>": { "type": "addon.toggle.enabled" }
	  },
	  "search": {
	    "default": "ddg",
	    "engines": {
	"DEFAULT":"https://duckduckgo.com/?q={}",
	"goog": "https://www.google.co.uk/search?&q={}",
	"googi": "https://www.google.co.uk/search?q={}&tbm=isch",
	"wiki": "https://en.wikipedia.org/w/index.php?search={}",
	"steam": "http://store.steampowered.com/search/?term={}",
	"ddg": "https://duckduckgo.com/?q={}",
	"aur": "https://aur.archlinux.org/packages/?O=0&K={}",
	"arch": "https://wiki.archlinux.org/index.php?title=Special%3ASearch&search={}",
	"imdb": "http://www.imdb.com/find?ref_=nv_sr_fn&s=all&q={}",
	"dic": "http://www.dictionary.com/browse/{}",
	"ety": "http://www.etymonline.com/index.php?allowed_in_frame=0&search={}",
	"urban": "http://www.urbandictionary.com/define.php?term={}",
	"ddgi": "https://duckduckgo.com/?q={}&iar=images",
	"lutris": "https://lutris.net/games/?q={}",
	"deal": "https://isthereanydeal.com/search/?q={}",
	"gog": "https://www.gog.com/games?sort=popularity&search={}&page=1",
	"proton": "https://www.protondb.com/search?q={}",
	"qwant": "https://www.qwant.com/?q={}",
	"sp": "https://www.startpage.com/do/dsearch?query={}",
	"humble": "https://www.humblebundle.com/store/search?sort=bestselling&search={}",
	"itch": "https://itch.io/search?q={}"
	    }
	  },
	  "properties": {
	    "hintchars": "abcdefghijklmnopqrstuvwxyz",
	    "smoothscroll": false,
	    "complete": "sbh"
	  },
	  "blacklist": [
	  ]
	}

This means now, when you are in FireFox you can hit t for a new tab. o for current tab entry.

restart FireFox.

You now have keyboard navigation in your browser. I demo this in a few videos. mostly press 'f' to highlight click-able links with keyboard characters.

You have my search defaults too so you can type o proton [game name] for protondb search, or o steam for steam... o gog for gog search, you get the idea... just read the damned list you just pasted.

VimVixen doesnt work on firefox settings pages, or any firefox page come to think of it... because... i dont know.. the rest of the time its great.

The fullscreen thing, that wont work for you as it works for me unless you are using DWM with fakefullscreen patch (or other such thing) so you may want to handle that differently to me.

Thats it.

[You are welcome](https://www.patreon.com/hexdsl)
