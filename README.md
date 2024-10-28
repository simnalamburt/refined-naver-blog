refined-naver-blog
========
Makes Naver blogs more readable and less distractive.

- [**Install this extension** at addons.mozilla.org](https://addons.mozilla.org/en-US/firefox/addon/refined-naver-blog/)
- [**Install this extension** at github.com](https://github.com/simnalamburt/refined-naver-blog/releases/latest)

before    | after
:--------:|:--------:
![before] | ![after]

```bash
# Build extension
zip -r refined-naver-blog.xpi icons main.css manifest.json
```

&nbsp;

## Userscript version
I haven't made this plugin into a Chrome browser extension yet because I found it a bit bothersome. Chrome users can install the [ViolentMonkey extension](https://chromewebstore.google.com/detail/violentmonkey/jinjaccalgkegednnccohejagnlnfdag) and then add the user script below.
```js
// ==UserScript==
// @name    refined-naver-blog
// @match   *://m.blog.naver.com/*
// @grant   GM_addStyle
// @run-at  document-start
// ==/UserScript==
GM_addStyle(`

body#body {
  position: relative;
  padding-bottom: 10rem;

  .Ngnb.gnb_bg_white, /* top nav bar */
  .floating_menu, /* bottom floating menu */
  .tablet_aside._relatedCategoryPostListArea, /* right pannel */
  #ct .blog_btnArea, /* buttons near title */
  #ct .naver-splugin.btn_share._returnFalse /* share button */
  {
    display: none;
  }

  /* disable horizontal line below title */
  .se-viewer .se-documentTitle .se-component-content::after {
    border-bottom: none;
  }

  /* wide post area */
  #_post_area {
    padding-right: 0;
  }

  #blog_fe_feed {
    #post_writer, /* writer info */
    .recommend_section__wqomV, /* recommendations */
    .banner_wrap__XF_zb, /* banners */
    .footer_wrap__A8tgh /* "맨 위로", "PC 버전으로 보기" */
    {
      display: none;
    }
  }
}

`)
```

&nbsp;

---

*refined-naver-blog* is primarily distributed under the terms of the [GNU
General Public License v3.0] or any later version. See [COPYRIGHT] for details.

[before]: https://raw.githubusercontent.com/simnalamburt/i/master/refined-naver-blog/before.png
[after]: https://raw.githubusercontent.com/simnalamburt/i/master/refined-naver-blog/after.png
[GNU General Public License v3.0]: LICENSE
[COPYRIGHT]: COPYRIGHT
