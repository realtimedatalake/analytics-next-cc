# analytics-next-cc - Analytics Next (aka Analytics.js 2.0) Carbon Copy

This is a fork of Analytics Next (aka Analytics.js 2.0) made to enable carbon copying (cc-ing) an additional endpoint as well as turning off the send to Segment and only sending to the cc endpoint. This is a drop-in replacement for Segment's Analytics Next.

## rtdl - The Real-Time Data Lake
This is a sub-project of [rtdl](https://github.com/realtimedatalake/rtdl) – the real-time 
data lake. Please go to rtdl's repo and give it a star.

## How to Use

### Standard Segment Analytics Next Snippet

```
<script>
  !function(){var analytics=window.analytics=window.analytics||[];if(!analytics.initialize)if(analytics.invoked)window.console&&console.error&&console.error("Segment snippet included twice.");else{analytics.invoked=!0;analytics.methods=["trackSubmit","trackClick","trackLink","trackForm","pageview","identify","reset","group","track","ready","alias","debug","page","once","off","on","addSourceMiddleware","addIntegrationMiddleware","setAnonymousId","addDestinationMiddleware"];analytics.factory=function(e){return function(){var t=Array.prototype.slice.call(arguments);t.unshift(e);analytics.push(t);return analytics}};for(var e=0;e<analytics.methods.length;e++){var key=analytics.methods[e];analytics[key]=analytics.factory(key)}analytics.load=function(key,e){var t=document.createElement("script");t.type="text/javascript";t.async=!0;t.src="https://cdn.segment.com/analytics.js/v1/" + key + "/analytics.min.js";var n=document.getElementsByTagName("script")[0];n.parentNode.insertBefore(t,n);analytics._loadOptions=e};analytics._writeKey="[your_write_key]";;analytics.SNIPPET_VERSION="4.15.3";
  analytics.load("[your_write_key]");
  analytics.page();
  }}();
</script>
```

### analytics-next-cc Snippet

For `analytics-next-cc`, you just need to replace `t.src="https://cdn.segment.com/analytics.js/v1/" + key + "/analytics.min.js"` in the above snippet with `t.src="https://cdn.jsdelivr.net/gh/realtimedatalake/analytics-next-cc@main/dist/analytics.min.js"`.

#### cc and send to Segment

```
<script>
  !function(){var analytics=window.analytics=window.analytics||[];if(!analytics.initialize)if(analytics.invoked)window.console&&console.error&&console.error("Segment snippet included twice.");else{analytics.invoked=!0;analytics.methods=["trackSubmit","trackClick","trackLink","trackForm","pageview","identify","reset","group","track","ready","alias","debug","page","once","off","on","addSourceMiddleware","addIntegrationMiddleware","setAnonymousId","addDestinationMiddleware"];analytics.factory=function(e){return function(){var t=Array.prototype.slice.call(arguments);t.unshift(e);analytics.push(t);return analytics}};for(var e=0;e<analytics.methods.length;e++){var key=analytics.methods[e];analytics[key]=analytics.factory(key)}analytics.load=function(key,e){var t=document.createElement("script");t.type="text/javascript";t.async=!0;t.src="https://cdn.jsdelivr.net/gh/realtimedatalake/analytics-next-cc@main/dist/analytics.min.js";var n=document.getElementsByTagName("script")[0];n.parentNode.insertBefore(t,n);analytics._loadOptions=e};analytics._writeKey="[your_write_key]";;analytics.SNIPPET_VERSION="4.15.3";
  analytics.load("[your_write_key]", { ccUrl: "http://localhost:8080/ingest", dontSendToSegment: false });
  analytics.page();
  }}();
</script>
```

#### cc and don't send to Segment

```
<script>
  !function(){var analytics=window.analytics=window.analytics||[];if(!analytics.initialize)if(analytics.invoked)window.console&&console.error&&console.error("Segment snippet included twice.");else{analytics.invoked=!0;analytics.methods=["trackSubmit","trackClick","trackLink","trackForm","pageview","identify","reset","group","track","ready","alias","debug","page","once","off","on","addSourceMiddleware","addIntegrationMiddleware","setAnonymousId","addDestinationMiddleware"];analytics.factory=function(e){return function(){var t=Array.prototype.slice.call(arguments);t.unshift(e);analytics.push(t);return analytics}};for(var e=0;e<analytics.methods.length;e++){var key=analytics.methods[e];analytics[key]=analytics.factory(key)}analytics.load=function(key,e){var t=document.createElement("script");t.type="text/javascript";t.async=!0;t.src="https://cdn.jsdelivr.net/gh/realtimedatalake/analytics-next-cc@main/dist/analytics.min.js";var n=document.getElementsByTagName("script")[0];n.parentNode.insertBefore(t,n);analytics._loadOptions=e};analytics._writeKey="[your_write_key]";;analytics.SNIPPET_VERSION="4.15.3";
  analytics.load("[your_write_key]", { ccUrl: "http://localhost:8080/ingest", dontSendToSegment: true });
  analytics.page();
  }}();
</script>
```

#### No cc and send to Segment

```
<script>
  !function(){var analytics=window.analytics=window.analytics||[];if(!analytics.initialize)if(analytics.invoked)window.console&&console.error&&console.error("Segment snippet included twice.");else{analytics.invoked=!0;analytics.methods=["trackSubmit","trackClick","trackLink","trackForm","pageview","identify","reset","group","track","ready","alias","debug","page","once","off","on","addSourceMiddleware","addIntegrationMiddleware","setAnonymousId","addDestinationMiddleware"];analytics.factory=function(e){return function(){var t=Array.prototype.slice.call(arguments);t.unshift(e);analytics.push(t);return analytics}};for(var e=0;e<analytics.methods.length;e++){var key=analytics.methods[e];analytics[key]=analytics.factory(key)}analytics.load=function(key,e){var t=document.createElement("script");t.type="text/javascript";t.async=!0;t.src="https://cdn.jsdelivr.net/gh/realtimedatalake/analytics-next-cc@main/dist/analytics.min.js";var n=document.getElementsByTagName("script")[0];n.parentNode.insertBefore(t,n);analytics._loadOptions=e};analytics._writeKey="[your_write_key]";;analytics.SNIPPET_VERSION="4.15.3";
  analytics.load("[your_write_key]");
  analytics.page();
  }}();
</script>
```

#### No cc and don't send to Segment

```
<script>
  !function(){var analytics=window.analytics=window.analytics||[];if(!analytics.initialize)if(analytics.invoked)window.console&&console.error&&console.error("Segment snippet included twice.");else{analytics.invoked=!0;analytics.methods=["trackSubmit","trackClick","trackLink","trackForm","pageview","identify","reset","group","track","ready","alias","debug","page","once","off","on","addSourceMiddleware","addIntegrationMiddleware","setAnonymousId","addDestinationMiddleware"];analytics.factory=function(e){return function(){var t=Array.prototype.slice.call(arguments);t.unshift(e);analytics.push(t);return analytics}};for(var e=0;e<analytics.methods.length;e++){var key=analytics.methods[e];analytics[key]=analytics.factory(key)}analytics.load=function(key,e){var t=document.createElement("script");t.type="text/javascript";t.async=!0;t.src="https://cdn.jsdelivr.net/gh/realtimedatalake/analytics-next-cc@main/dist/analytics.min.js";var n=document.getElementsByTagName("script")[0];n.parentNode.insertBefore(t,n);analytics._loadOptions=e};analytics._writeKey="[your_write_key]";;analytics.SNIPPET_VERSION="4.15.3";
  analytics.load("[your_write_key]", { dontSendToSegment: true });
  analytics.page();
  }}();
</script>
```

## Changed Files

- Updated `/src/analytics.ts`
- Updated `/src/plugins/segmentio/index.ts`
- Updated `/.gitignore` -- restricted `dist` ignore to its individual subfolders
- Added `/dist/analytics.min.js`
- Added `/dist/index.js`
- Added `/dist/index.js.map`
- Added `/dist/standalone.js`
- Added `/dist/standalone.js.map`
- Added `/.prettierignore` -- ignored `/dist/`

## How to Build

1.  Switch to NPM version 14/fermium (install lts/fermium first if necessary).
    `% nvm use lts/fermium`
2.  Install NPM dependencies.
    `% make node_modules`
3.  Test updates on a local dev environment.
    `% make dev`
    Go to [http://localhost:3000/](http://localhost:3000/) in your web browser to test your updats.
4.  Clean and build.
    ```
    % make clean
    rm -rf dist generated
    % make build-prod
    ...
    ```
5.  Copy the UMD files to the dist folder
    ```
    % cp -p ./dist/umd/standalone.js ./dist/analytics.min.js
    % cp -p ./dist/umd/standalone.js ./dist/umd/standalone.js.map ./dist/umd/index.js ./dist/umd/index.js.map ./dist/
    ```

---

# Analytics Next

Analytics Next (aka Analytics 2.0) is the latest version of Segment’s JavaScript SDK - enabling you to send your data to any tool without having to learn, test, or use a new API every time.

### Table of Contents

- [🏎️ Quickstart](#-quickstart)
  - [💡 Using with Segment](#-using-with-segment)
  - [💻 Using as an NPM package](#-using-as-an-npm-package)
- [🔌 Plugins](#-plugins)
- [🐒 Development](#-development)
- [🧪 Testing](#-testing)
  - [✅ Unit Testing](#-unit-testing)

---

# 🏎️ Quickstart

The easiest and quickest way to get started with Analytics 2.0 is to [use it through Segment](#-using-with-segment). Alternatively, you can [install it through NPM](#-using-as-an-npm-package) and do the instrumentation yourself.

## 💡 Using with Segment

1. Create a javascript source at [Segment](https://app.segment.com) - new sources will automatically be using Analytics 2.0! Segment will automatically generate a snippet that you can add to your website. For more information visit our [documentation](https://segment.com/docs/connections/sources/catalog/libraries/website/javascript/)).

2. Start tracking!

## 💻 Using as an NPM package

1. Install the package

```sh
# npm
npm install @segment/analytics-next

# yarn
yarn add @segment/analytics-next

#pnpm
pnpm add @segment/analytics-next
```

2. Import the package into your project and you're good to go (with working types)! Example react app:

```ts
import { Analytics, AnalyticsBrowser, Context } from '@segment/analytics-next'
import { useEffect, useState } from 'react'
import logo from './logo.svg'

function App() {
  const [analytics, setAnalytics] = useState<Analytics | undefined>(undefined)
  const [writeKey, setWriteKey] = useState('<YOUR_WRITE_KEY>')

  useEffect(() => {
    const loadAnalytics = async () => {
      let [response] = await AnalyticsBrowser.load({ writeKey })
      setAnalytics(response)
    }
    loadAnalytics()
  }, [writeKey])

  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          onClick={(e) => {
            e.preventDefault()
            analytics?.track('Hello world')
          }}
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Track
        </a>
      </header>
    </div>
  )
}

export default App
```

### using `Vite` with `Vue 3`

1. add to your `index.html`

```html
<script>
  window.global = window
  var exports = {}
</script>
```

2. create composable file `segment.ts` with factory ref analytics:

```ts
import { ref, reactive } from 'vue'
import { Analytics, AnalyticsBrowser } from '@segment/analytics-next'

const analytics = ref<Analytics>()

export const useSegment = () => {
  if (!analytics.value) {
    AnalyticsBrowser.load({
      writeKey: '<YOUR_WRITE_KEY>',
    })
      .then(([response]) => {
        analytics.value = response
      })
      .catch((e) => {
        console.log('error loading segment')
      })
  }

  return reactive({
    analytics,
  })
}
```

3. in component

```vue
<template>
  <button @click="track()">Track</button>
</template>

<script>
import { defineComponent } from 'vue'
import { useSegment } from './services/segment'

export default defineComponent({
  setup() {
    const { analytics } = useSegment()

    function track() {
      analytics?.track('Hello world')
    }

    return {
      track,
    }
  },
})
</script>
```

# 🐒 Development

First, clone the repo and then startup our local dev environment:

```sh
$ git clone git@github.com:segmentio/analytics-next.git
$ cd analytics-next
$ make dev
```

Then, make your changes and test them out in the test app!

<img src="https://user-images.githubusercontent.com/2866515/135407053-7561d522-b969-484d-8d3a-6f1c4d9c025b.gif" alt="Example of the development app" width="500px">

# 🔌 Plugins

When developing against Analytics Next you will likely be writing plugins, which can augment functionality and enrich data. Plugins are isolated chunks which you can build, test, version, and deploy independently of the rest of the codebase. Plugins are bounded by Analytics Next which handles things such as observability, retries, and error management.

Plugins can be of two different priorities:

1. **Critical**: Analytics Next should expect this plugin to be loaded before starting event delivery
2. **Non-critical**: Analytics Next can start event delivery before this plugin has finished loading

and can be of five different types:

1. **Before**: Plugins that need to be run before any other plugins are run. An example of this would be validating events before passing them along to other plugins.
2. **After**: Plugins that need to run after all other plugins have run. An example of this is the segment.io integration, which will wait for destinations to succeed or fail so that it can send its observability metrics.
3. **Destination**: Destinations to send the event to (ie. legacy destinations). Does not modify the event and failure does not halt execution.
4. **Enrichment**: Modifies an event, failure here could halt the event pipeline.
5. **Utility**: Plugins that change Analytics Next functionality and don't fall into the other categories.

Here is an example of a simple plugin that would convert all track events event names to lowercase before the event gets sent through the rest of the pipeline:

```ts
export const lowercase: Plugin = {
  name: 'Lowercase events',
  type: 'before',
  version: '1.0.0',

  isLoaded: () => true,
  load: () => Promise.resolve(),

  track: (ctx) => {
    ctx.event.event = ctx.event.event.toLowerCase()
    return ctx
  },
  identify: (ctx) => ctx,
  page: (ctx) => ctx,
  alias: (ctx) => ctx,
  group: (ctx) => ctx,
  screen: (ctx) => ctx,
}
```

For further examples check out our [existing plugins](https://github.com/segmentio/analytics-next/tree/master/src/plugins).

# 🧪 Testing

The tests are written in [Jest](https://jestjs.io) and can be run be using `make test-unit`
Linting is done using [ESLint](https://github.com/typescript-eslint/typescript-eslint/) and can be run using `make lint`.

## ✅ Unit Testing

Please write small, and concise unit tests for every feature you work on.

```sh
$ make test-unit # runs all tests
$ yarn jest src/<path> # runs a specific test or tests in a folder
```
