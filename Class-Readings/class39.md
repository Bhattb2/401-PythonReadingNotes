# NEXT JS


[NextJS](https://nextjs.org/learn/basics/create-nextjs-app)

[Deployment from Vercel](https://nextjs.org/docs/deployment)

Next.js: The React Framework Enter Next.js, the React Framework. Next.js provides a solution to all of the above problems. But more importantly, it puts you and your team in the pit of success when building React applications.

Next.js has the best-in-class "Developer Experience" and many built-in features; a sample of them are:

An intuitive page-based routing system (with support for dynamic routes) Pre-rendering, both static generation (SSG) and server-side rendering (SSR) are supported on a per-page basis Automatic code splitting for faster page loads Client-side routing with optimized prefetching Built-in CSS and Sass support, and support for any CSS-in-JS library Development environment which supports Hot Module Replacement API routes to build API endpoints with Serverless Functions Fully extendable Next.js is used in tens of thousands of production-facing websites and web applications, including many of the world's largest brands.

Next.js is a framework built on top of React.

To start a project run:

`npx create-next-app <app-name>`

You can include an --example flag to build an app from a template.

Then to run a development server:

`npm run dev`

Which is a script define in your package.json file at the root of the app.

This server will refresh your page anytime it is saved.

## Routing

No need to define routes, its all handled by placing files in the `pages/` directory.

## Linking other pages

To do client-side navigation use the <Link> tag:

    `<Link href="url">
        <a>Text to be inked</a>
    </Link>`

## Code splitting and prefetching

Next.js automatically does code splitting, so that every page only loads what it needs. Next.js also pre-fetches linked pages, so that when you click a link its already loaded.

## Assets

static files, like images can go in the `public/ `top level directory.

## Metadata

`<Head>` is a built in component, and can be imported from 'next/head'

## CSS

Next.js supports CSS and Sass.

CSS modules
To create a css module, create a `file /components/<component name>.js`, and the corresponding `/components/<component name>.module.css`

important note: your css file MUST end in `.module.css`

We'll use layout as our component, from the next.js totorial

    // `layout.js`

    import styles from './layout.module.css'

    export default function Layout({ children }) {
      return <div className={styles.container}>{children}</div>
    }


    // layout.module.css

    .container {
       max-width: 36rem;
       padding: 0 1rem;
       margin: 3rem auto 6rem
    }

Then finally, use the `<Layout>` component to wrap the JSX output of the content in a page.

Then your css will be applied, and the magical part is that the actual classes that the browser sees are automatically generated, so you never get class collisions.

## global CSS

Another use-case for CSS is to apply styles globally. Another, example from the tutorial:

    // pages/_app.js

    import '../styles/global.css'

    export default function App({ Component, pageProps }) {
        return <Component {...pageProps } />
    }

Important: You need to restart the development server when you add pages/_app.js. Press Ctrl + c to stop the server and run: `npm run dev`

Then make a `global.css` file in a new root-level directory called styles/ and make some global styles.

    /* /styles/global.css */

    html,
    body {
        background-colour: black
    }

## Classnames library

`npm install classnames`

You can use the classnames library to further customize your React app.

## Sass

You can use Sass with both `.scss` and also .sass file extentions, and use them at the module level with `.module.scss` and `.module.sass`.