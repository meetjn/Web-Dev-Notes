# Web-Dev-Notes
This repo will contain all the resources and notes that I will use to prepare for my web development journey. 

PRE-REQUISITES:

Basic understanding of React and some of its frameworks. 


Question 1: what happens when the website is first reloaded?

answer: the first request goes to the server and gets the HTML and then the second request goes out to get the javascript file in the react based project. 

NEXTJS (FULL STACK FRAMEWORK)

The problem nextJS has solved over reactjs is that -> 1) it solved the water falling problem and 2) made the website SEO optimized. 

FEATURES OF NEXTJS:
1) Server-side rendering - Get rid of SEO problems -> Server-side rendering (SSR) in Next.js is a feature that allows you to render React components on the server instead of the client, improving performance and search engine optimization (SEO). Next.js provides built-in support for SSR through its file-based routing system and API routes.
2) API routes - Single codebase with frontend and backend -> (IT IS A FULL STACK FRAMEWORK WHERE AS REACT IS A FRONTEND FRAMEWORK).
3) File-based routing (no need for react-router-dom)
4) Bundle size optimisations, Static site generation
5) Maintained by the Vercel team.

Downside as well:
1) Can’t be distributed via a CDN (not easy to deploy on AWS), always needs a server running that does server-side rendering and hence is expensive (It is expensive at scale).
2) Very opinionated, very hard to move out of it. 

1) BOOTSTAPPING UP THE NEXTJS PROJECT:

Run: npx create-next-app@latest

After running the command, you will notice that these three files have been initialized. 

next.config.mjs - Nextjs configuration file

tailwind.config.js - Tailwind configuration file

app - Contains all your code/components/layouts/routes/apis

NOTE:
package.json: which contains all the dependencies. YOU WILL NOTICE THAT IT HAS REACT AND REACT-ROUTER-DOM this is because Next is written on top of reactjs. 

Q2: how many dev dependencies do we have? 

A: TWO types -> dependencies and dev dependencies. 

2) UNDERSTANDING ROUTING IN NEXTJS

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

3) UNDERSTANDING LAYOUT IN NEXTJS

A layout is UI that is shared between multiple routes. On navigation, layouts preserve state, remain interactive, and do not re-render. Layouts can also be nested.
You can define a layout by default exporting a React component from a layout.js file. The component should accept a children prop that will be populated with a child layout (if it exists) or a page during rendering.

See docs here: https://nextjs.org/docs/app/building-your-application/routing/pages-and-layouts#layouts

For example, the layout will be shared with the /dashboard and /dashboard/settings pages:
<img width="633" alt="Screenshot 2024-03-22 at 7 53 28 AM" src="https://github.com/meetjn/Web-Dev-Notes/assets/141674944/1a5577df-5a67-4441-b171-f9c8e6481c1a">

3.1) Root Layout (Required) 

<img width="157" alt="Screenshot 2024-03-22 at 8 26 29 AM" src="https://github.com/meetjn/Web-Dev-Notes/assets/141674944/bd615819-08e5-4eb3-9332-f613ed0e81bf">

The root layout is defined at the top level of the app directory and applies to all routes. This layout is required and must contain html and body tags, allowing you to modify the initial HTML returned from the server.
This will be present in the root layout file and will shown throughout the web pages. 
You can acceess this in the root app directory above pages.tsx file. 

<img width="643" alt="Screenshot 2024-03-22 at 8 29 43 AM" src="https://github.com/meetjn/Web-Dev-Notes/assets/141674944/57288b35-b0e7-4bd7-93ed-d29732bfafe9">



Always remember to render it as under the children component. 

3.2) Nesting Layouts

By default, layouts in the folder hierarchy are nested, which means they wrap child layouts via their children prop. You can nest layouts by adding layout.js inside specific route segments (folders).

For example, to create a layout for the /dashboard route, add a new layout.js file inside the dashboard folder:

If you were to combine the two layouts above, the root layout (app/layout.js) would wrap the dashboard layout (app/dashboard/layout.js), which would wrap route segments inside app/dashboard/*.

The two layouts would be nested as such:

<img width="643" alt="Screenshot 2024-03-22 at 8 31 40 AM" src="https://github.com/meetjn/Web-Dev-Notes/assets/141674944/2c75abfe-b093-4dd6-878e-32e14fd65c4f">

3.3) Merging Routes

This is usefull when two file needs to have same layout, so to do this there are two approaches. 

1) Move both the signin and signup folder inside a auth folder where we have the layout
<img width="526" alt="Screenshot 2024-03-22 at 8 57 28 AM" src="https://github.com/meetjn/Web-Dev-Notes/assets/141674944/67ab5539-06cd-4121-806a-c869b1ff103a">

You can access the routes at 
http://localhost:3000/auth/signup and http://localhost:3000/auth/signin

2) if you do not want to change the route handler then you can use create a new folder with () around the name. 
This folder is ignored by the router.
<img width="685" alt="Screenshot 2024-03-22 at 8 58 54 AM" src="https://github.com/meetjn/Web-Dev-Notes/assets/141674944/5f618fb4-7480-4da1-9738-169210da142a">

You can access the routes at 
http://localhost:3000/signup and http://localhost:3000/signin
