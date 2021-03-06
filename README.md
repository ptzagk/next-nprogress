# next-nprogress

Next.js HOC to integrate NProgress inside your app.

This is configured to run only after a delay of (default) 300ms. This means if the page change takes too long it will render the progress bar, but if it's fast enough it will avoid rendering it.

## Usage

Install it

```bash
yarn add next-nprogress
```

Import it inside your `pages/_app.js`;

```js
import withNProgress from "next-nprogress";
import NProgressStyles from "next-nprogress/styles";
```

Wrap your [custom App container](https://nextjs.org/docs#custom-%3Capp%3E) with it

```js
const msDelay = 300; // default is 300
export default withNProgress(msDelay)(MyApp);
```

And render `NProgressStyles` inside your App container or [layout component](https://github.com/zeit/next.js/tree/canary/examples/layout-component)

```js
// the default progress bar and spinner color is #29d, it could be changed for any CSS color
<NProgressStyles color="#29d" />
```

That's it. Now NProgress will work automatically and will render the correct styles using styled-jsx.
