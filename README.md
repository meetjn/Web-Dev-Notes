# Web-Dev-Notes

### Basic understanding of HTML CSS and JavaScript.

Hypertext is a text which contains links to other text. Markup refers to tags and elements used within a document.

HTML stands for hypertext markup language, it works by using something called markup tags. These tags describe the content that is displayed in the browser window, this content can be things like headings, paragraphs, images and even multimedia elements such as audio and video, the way HTML describes the content is known as markup.

The way HTML describes the content is known as markup. CSS is short for cascading style sheets and adds visual enhancements like colors and layout to the web page, this is commonly known as styling. It works by enhancing the HTML elements and telling them how to display.

By default, nearly all HTML elements are organized into one of two categories namely in block and in line elements.


A block-level element will occupy the full horizontal width of its parent element and the vertical height of its content. Each block level element will have a new line before and after. Therefore, multiple block-level elements will stack on top of each other like a stack of boxes. 

In-line elements only occupy the width and height of their content. They don't appear on a new line, hence the name in line. Therefore, multiple in line elements can form a row of elements. When coding in HTML, you need to be able to recognize and use block elements. Some examples of block level elements include the tags, div form and heading. 

You also need to be familiar with common in-line elements. These include the tags anchor, image, input label, bold, italics, emphasis and span.

JavaScript is a programming language built into the browser. JavaScript provides web developers with tools for interactivity, data processing, control and action.

Question- 
But how exactly does web page/ Website code get translated to display the content that you see on your screen? 

When a copy of that webpage is sent from the web server to your browser, each line of code is processed in sequential order from first to last. As each line is interpreted, the browser creates the building blocks, which is the visual representation you see on the screen. This creation process is known as page rendering.

# Basic understanding of React.


Question 1: what happens when the website is first reloaded?

answer: the first request goes to the server and gets the HTML and then the second request goes out to get the javascript file in the react-based project. 

Note- 

A library is a collection of reusable code that a developer can call as needed, while a framework provides a structured application skeleton that the developer fills in with their code.

## ReactJs Notes

How does react work? 

React builds a representation of the browser Document Object Model or DOM in memory called the virtual DOM. As components are updated, React checks to see if the component’s HTML code in the virtual DOM matches the browser DOM. If a change is required, the browser DOM is updated. If nothing has changed, then no update is performed.

this is called the reconciliation process and can be broken down into the following steps:

Step 1: The virtual DOM is updated.

Step 2: The virtual DOM is compared to the previous version of the virtual DOM and checks which elements have changed.

Step 3: The changed elements are updated in the browser DOM.

Step 4: The displayed webpage updates to match the browser DOM.

 The concept of the single-page application or SPA for short? This is a one-page website where some of the page content changes based on user interaction.

 React provides two types of components, functional components and class components.

# NEXTJS (FULL STACK FRAMEWORK)

The problem nextJS has solved over reactjs is that -> 1) it solved the water falling problem and 2) it made the website SEO optimized. 

FEATURES OF NEXTJS 13:
1) Server-side rendering - Get rid of SEO problems -> Server-side rendering (SSR) in Next.js is a feature that allows you to render React components on the server instead of the client, improving performance and search engine optimization (SEO). Next.js provides built-in support for SSR through its file-based routing system and API routes.
2) API routes - Single codebase with frontend and backend -> (IT IS A FULL STACK FRAMEWORK WHERE AS REACT IS A FRONTEND FRAMEWORK).
3) File-based routing (no need for react-router-dom)
4) Bundle size optimisations, Static site generation
5) Maintained by the Vercel team.

The downside as well:
1) Can’t be distributed via a CDN (not easy to deploy on AWS), always needs a server running that does server-side rendering and hence is expensive (It is expensive at scale).
2) Very opinionated, very hard to move out of it. 

# 1) BOOTSTAPPING UP THE NEXTJS PROJECT:

         Run: npx create-next-app@latest

After running the command, you will notice that these three files have been initialized. 

next.config.mjs - Nextjs configuration file

tailwind.config.js - Tailwind configuration file

app - Contains all your code/components/layouts/routes/apis

NOTE:
package.json: which contains all the dependencies. YOU WILL NOTICE THAT IT HAS REACT AND REACT-ROUTER-DOM this is because Next is written on top of reactjs. 

Q2: how many dev dependencies do we have? 

A: TWO types -> dependencies and dev dependencies. 

# 2) UNDERSTANDING ROUTING IN NEXTJS

Next.js has a file-based router, which means that the way you create your files describes what renders on a route.
Each folder represents a route segment that maps to a URL segment. To create a nested route, you can nest folders inside each other.
A special page.js file is used to make route segments publicly accessible.

See official docs here -> https://nextjs.org/docs/app/building-your-application/routing/defining-routes

The next thing to understand in routing in nextjs is PAGES:

A page is a UI that is unique to a route. You can define a page by default exporting a component from a page.js file.

For example, to create your index page, add the page.js file inside the app directory: 
CODE:


<img width="633" alt="Screenshot 2024-03-22 at 7 44 29 AM" src="https://github.com/meetjn/Web-Dev-Notes/assets/141674944/3ad4d09a-b069-4e56-9811-0b05d1dcfacd">


Then, to create further pages, create a new folder and add the page.js file inside it. For example, to create a page for the /dashboard route, create a new folder called a dashboard, and add the page.js file inside it:

<img width="633" alt="Screenshot 2024-03-22 at 7 44 08 AM" src="https://github.com/meetjn/Web-Dev-Notes/assets/141674944/84f5b044-cf32-45d9-8524-361b15f12fec">

# 3) UNDERSTANDING LAYOUT IN NEXTJS

A layout is a UI that is shared between multiple routes. On navigation, layouts preserve state, remain interactive, and do not re-render. Layouts can also be nested.
You can define a layout by default exporting a React component from a layout.js file. The component should accept a children prop that will be populated with a child layout (if it exists) or a page during rendering.

See docs here: https://nextjs.org/docs/app/building-your-application/routing/pages-and-layouts#layouts

For example, the layout will be shared with the /dashboard and /dashboard/settings pages:
<img width="633" alt="Screenshot 2024-03-22 at 7 53 28 AM" src="https://github.com/meetjn/Web-Dev-Notes/assets/141674944/1a5577df-5a67-4441-b171-f9c8e6481c1a">

3.1) Root Layout (Required) 

<img width="157" alt="Screenshot 2024-03-22 at 8 26 29 AM" src="https://github.com/meetjn/Web-Dev-Notes/assets/141674944/bd615819-08e5-4eb3-9332-f613ed0e81bf">

The root layout is defined at the top level of the app directory and applies to all routes. This layout is required and must contain HTML and body tags, allowing you to modify the initial HTML returned from the server.
This will be present in the root layout file and will shown throughout the web pages. 
You can access this in the root app directory above pages.tsx file. 

<img width="643" alt="Screenshot 2024-03-22 at 8 29 43 AM" src="https://github.com/meetjn/Web-Dev-Notes/assets/141674944/57288b35-b0e7-4bd7-93ed-d29732bfafe9">



Always remember to render it as under the children component. 

3.2) Nesting Layouts

By default, layouts in the folder hierarchy are nested, which means they wrap child layouts via their children prop. You can nest layouts by adding layout.js inside specific route segments (folders).

For example, to create a layout for the /dashboard route, add a new layout.js file inside the dashboard folder:

If you were to combine the two layouts above, the root layout (app/layout.js) would wrap the dashboard layout (app/dashboard/layout.js), which would wrap route segments inside app/dashboard/*.

The two layouts would be nested as such:

<img width="643" alt="Screenshot 2024-03-22 at 8 31 40 AM" src="https://github.com/meetjn/Web-Dev-Notes/assets/141674944/2c75abfe-b093-4dd6-878e-32e14fd65c4f">

3.3) Merging Routes

This is useful when two files need to have the same layout, so to do this there are two approaches. 

1) Move both the sign-in and signup folders inside an auth folder where we have the layout
<img width="526" alt="Screenshot 2024-03-22 at 8 57 28 AM" src="https://github.com/meetjn/Web-Dev-Notes/assets/141674944/67ab5539-06cd-4121-806a-c869b1ff103a">

You can access the routes at 
http://localhost:3000/auth/signup and http://localhost:3000/auth/signin

2) if you do not want to change the route handler then you can use create a new folder with () around the name. 
The router ignores this folder.
<img width="685" alt="Screenshot 2024-03-22 at 8 58 54 AM" src="https://github.com/meetjn/Web-Dev-Notes/assets/141674944/5f618fb4-7480-4da1-9738-169210da142a">

You can access the routes at 
http://localhost:3000/signup and http://localhost:3000/signin

# 4) SERVER AND CLIENT COMPONENTS

To understand how Server and Client Components work, it's helpful to be familiar with two foundational web concepts:

See docs here: https://nextjs.org/learn/react-foundations/server-and-client-components#server-and-client-environments

The environments your application code can be executed in: are the server and the client.
The network boundary that separates server and client code

4.1) Server and Client Environments

4.1.1) In the context of web applications:

-> The client refers to the browser on a user’s device that sends a request to a server for your application code. It then turns the response it receives from the server into an    interface the user can interact with.

-> The server refers to the computer in a data centre that stores your application code, receives requests from a client, does some computation, and sends back an appropriate      response.

4.1.2) Network Boundary

The Network Boundary is a conceptual line that separates the different environments.

NextJS expects you to identify all your components as either client or server By default, all components are server components.

If you want to mark a component as a client component, you need to add the following to the top of the component - 
"use client"

question: When should you create client components?

Whenever you get an error that tells you that you need to create a client component

Whenever you’re using something the server doesn’t understand (useEffect, useState, onClick…)

The rule of thumb is to defer the client as much as possible

# 5) BACKEND IN NEXTJS

Next.js is a full-stack framework
This means the same process can handle frontend and backend code.

Why?
Single codebase for all your codebase

No cors issues, single domain name for your FE and BE

Ease of deployment, deploy a single codebase

5.1) Data Fetching, Caching, and Revalidating

There are four ways you can fetch data:

1. On the server, with fetch

2. On the server, with third-party libraries

3. On the client, via a Route Handler

4. On the client, with third-party libraries.

Ref: https://nextjs.org/docs/app/building-your-application/data-fetching/fetching-caching-and-revalidating#fetching-data-on-the-server-with-fetch

5.1) Fetching Data on the Server with fetch

Next.js extends the native fetch Web API to allow you to configure the caching and revalidating behaviour for each fetch request on the server. React extends fetch to memoize fetch requests while rendering a React component tree automatically.

You can use fetch with async/await in Server Components, in Route Handlers, and in Server Actions. (i.e. server components can be asynchronous).

<img width="697" alt="Screenshot 2024-03-23 at 11 44 04 AM" src="https://github.com/meetjn/Web-Dev-Notes/assets/141674944/1a90bd2a-f755-46cb-aab7-66140c6479a6">

While fetching data you want to make sure that if the fetching data from the backend takes a long time, the user sees a loader in the meantime

5.2) loading.tsx file

Just like page.tsx and layout.tsx, you can define a skeleton.tsx file that will render until all the async operations finish
Create a loading.tsx file in the root folder

NOTE: NEXT js provides more such files but these are the bare minimum. 

6) Introducing API routes in Next.js

NextJS lets you write backend routes, just like Express does. This is why Next is considered to be a full-stack framework.

The benefits of using NextJS for the backend include - 

1. Code in a single repo

2. All standard things you get in a backend framework like Express

3. Server components can directly talk to the backend

# DEFINING ROUTES IN THE BACKEND

We want to introduce a route that returns hardcoded values for a user’s details (email, name) for example.


1. Introduce a new folder called API
2. Add a folder inside called the user
3. Add a file inside called route.ts
4. Initialize a GET route inside it

NOTE:
Route the user to the landing page if the signup succeeded
Ref use router hook - https://nextjs.org/docs/app/building-your-application/routing/linking-and-navigating#userouter-hook


   
Question 3) What is the difference between authentication and authorization?
answer: Authentication and authorization for both servers have different purposes

Authentication
Authentication is the process of verifying the identity of a user or system attempting to access a resource or service. It involves presenting credentials, such as a username/password combination, or any other means of identification.

Authorization
Authorization is the process of determining what actions or operations an authenticated user is allowed to perform within a system or on a specific resource.

It ensures that authenticated users or systems can only perform actions or access resources that they have been explicitly granted permission to access.


# 7) NEXTAUTH.JS

NextAuth.js is a complete open-source authentication solution for Next.js applications.

It is designed from the ground up to support Next.js and Serverless.

Let's say you want to create a catch-all route handler the way to do this is: 

Create a simple next.js app 

      npx create-next-app@latest

Create app/api/auth/[...nextauth]/route.ts 

      npm install next-auth

Adding providers - There are three broad types of providers
1) OAuth (Login with Google)
2) Email (Passwordless Email login via email OTP)
3) Credentials (your own strategy)

ref: https://next-auth.js.org/configuration/providers/oauth

7.3) CREDENTIALS 

ref: https://next-auth.js.org/configuration/providers/credentials

GOOGLE AUTH : https://next-auth.js.org/providers/google 

GITHUB AUTH: https://next-auth.js.org/providers/github

# Middlewares in NextJs

Middleware allows you to run code before a request is completed. Then, based on the incoming request, you can modify the response by rewriting, redirecting, modifying the request or response headers, or responding directly.

Middleware runs before cached content and routes are matched. See Matching Paths for more details.

see docs here: https://nextjs.org/docs/app/building-your-application/routing/middleware

# CSR And SSr And SSG

Client-side rendering (CSR) is a modern technique used in web development where the rendering of a webpage is performed in the browser using JavaScript. Instead of the server sending a fully rendered HTML page to the client
Good example of CSR - React 

SSR
When the rendering process (converting JS components to HTML) happens on the server, it’s called SSR.
Why SSR?
SEO Optimisations
Gets rid of the waterfalling problem
No white flash before you see content

SSG

If a page uses Static Generation, the page HTML is generated at build time. That means in production, the page HTML is generated when you run next build. This HTML will then be reused on each request. It can be cached by a CDN.

Why?
If you use static site generation, you can defer the expensive operation of rendering a page to the build time so it only happens once. 
