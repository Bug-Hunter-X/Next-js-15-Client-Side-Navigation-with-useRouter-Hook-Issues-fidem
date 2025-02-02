# Next.js 15 Client-Side Navigation Bug

This repository demonstrates a potential issue with client-side navigation in Next.js 15 when using the `useRouter` hook.  The application consists of two pages: a home page and an about page.  Navigating between the pages using links and buttons can lead to unexpected behavior such as hydration mismatches or incorrect routing, especially under certain conditions or with complex routing setups.

## Bug Description

The main issue is related to how the `useRouter` hook interacts with the client-side routing mechanism of Next.js 15.  In some scenarios, especially when dealing with dynamic routes or complex navigation flows, using `router.push()` might not always update the UI correctly or may lead to hydration issues.  These issues are more pronounced in larger applications.

## Reproduction Steps

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm run dev` to start the development server.
4. Navigate between the home page and the about page using the provided links and button.
5. Observe the behavior, noting any inconsistencies or errors related to the page content or the URL in the browser address bar.

## Potential Causes

The root cause is likely related to the way Next.js handles hydration, the process of transferring the client-side state to the server-rendered content.  Improper or untimely calls to `router.push()` could disrupt this process, leading to hydration mismatches and subsequent errors.

## Solution

See the `solution` branch for possible ways to resolve this, such as using `router.replace()` instead of `router.push()` or carefully managing the timing of navigation actions.