# Web performance checklist

## Why it’s important

- [ ] WPO Stats ([website](https://wpostats.com/))
- [ ] Why performance matters ([website](https://developers.google.com/web/fundamentals/performance/why-performance-matters))

## Testing

- [ ] PageSpeed Insights ([website](https://developers.google.com/speed/pagespeed/insights/))
- [ ] Setup Lighthouse in pull requests ([article](https://bitsofco.de/your-first-performance-budget-with-lighthouse/))
- [ ] Lighthouse in DevTools ([docs](https://developers.google.com/web/tools/lighthouse#devtools))
- [ ] WebPageTest ([website](https://www.webpagetest.org/))
- [ ] What does my site cost? ([website](https://whatdoesmysitecost.com/))

## General rule of thumb

- [ ] Reduce number of requests
- [ ] Minify assets
- [ ] Concatenate assets (make multiple files into one)
- [ ] Lazy load/defer loading ([tweet](https://twitter.com/bdc/status/1030506494762971137?ref_src=twsrc%5Etfw%7Ctwcamp%5Etweetembed%7Ctwterm%5E1030506494762971137&ref_url=https%3A%2F%2Fcss-tricks.com%2Fthe-low-hanging-fruit-of-web-performance%2F))

## Images

- [ ] Use SVG where possible ([article](https://css-tricks.com/using-svg/))
- [ ] Optimize SVGs ([SVGOMG](https://jakearchibald.github.io/svgomg/))
- [ ] Optimize jpg/png/webp ([ImageOptim](https://imageoptim.com/mac))
- [ ] Use webp image format and the picture element ([article](https://css-tricks.com/using-webp-images/))
- [ ] Setup responsive images ([article](https://css-tricks.com/responsive-images-css/))
- [ ] Replace gifs with video ([article](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/replace-animated-gifs-with-video))

## Fonts

- [ ] Reduce number of font files
- [ ] Subset fonts so that they contain only the languages/glyphs you need ([Font Squirrel](https://www.fontsquirrel.com/) / [glyphhanger](https://github.com/filamentgroup/glyphhanger))
- [ ] Use .woff/.woff2
- [ ] `font-display: swap` ([article](https://css-tricks.com/almanac/properties/f/font-display/))

## Server side

- [ ] Setup a CDN (Cloudflare, Netlify, etc.)
- [ ] Browser caching
- [ ] GZIP assets
- [ ] HTTP/2

## Scripts

- [ ] Turbolinks ([link](https://github.com/turbolinks/turbolinks))
- [ ] Uglify and concatenate
- [ ] Avoid multiple analytics scripts
- [ ] Tree-shaking ([docs](https://webpack.js.org/guides/tree-shaking/))
- [ ] Measure bundle size ([repo](https://github.com/webpack-contrib/webpack-bundle-analyzer))

## Styles

- [ ] Avoid animating anything besides `position`, `scale`, `rotation`, `opacity` ([article](https://www.html5rocks.com/en/tutorials/speed/high-performance-animations/))
- [ ] Use Critical CSS if possible ([article](https://www.smashingmagazine.com/2015/08/understanding-critical-css/))
- [ ] Write styles mobile first ([article](https://zellwk.com/blog/how-to-write-mobile-first-css/))
- [ ] Concatenate styles into one CSS file
- [ ] Remove duplicate styles ([CSS Stats](https://cssstats.com))
- [ ] Tell the browser which properties will animate with `will-change` ([article](https://dev.opera.com/articles/css-will-change-property/))

## HTML

- [ ] Make fewer HTTP requests
- [ ] Preload, prefetch assets where it makes sense ([article](https://css-tricks.com/prefetching-preloading-prebrowsing/))

[SOURCE](https://www.notion.so/Web-performance-checklist-02fbc975d9bd432993bdadce73de1b17)
