# factory

The Funkhaus component Factory - a proof of concept for an upcoming component marketplace

Explain what this repo is for. Mention James Lee.

## How to accept a Component Request
Component requests are made through Github Issues, [example](https://github.com/funkhaus/factory/issues/3). Review the request, ask questions and when ready make a proposal to build the component. If accepted, the Issue will be progressed to the Accepted state in the Project.

## How to develop once a Component Request has been accepted
Every issue is assigned to a Github Project and every Github Project has an associated `branch`. For example, we currently have a `funkhaus` project and in return also have a branch named `funkhaus`.

### Fork and Branch setup
1. Fork this repository
2. Checkout the Project branch
3. Create a new branch based on the Github Issue #. IE: `ISSUE-3`

### Storybook Development
We use storybook to develop and show off the components that have been created. If you are not familiar with storybook, checkout [storybook](https://storybook.js.org/). 

To get started:
1. `npm install`
2. `npm run storybook`
3. develop your new component in the `components` directory
- create a new directory with the Github issue # and place the component files in this directory.
- at a minimum the `${component}.vue` file and `${component}.stories.js` file should be here.

```
- components
- - ISSUE-3
- - - sample.vue
- - - sample.stories.js
```


## How to submit a finished Component for review
Once a Component Request has been accepted and developed, you can open Pull Request for review. When creating the Pull Request, please make the PR against the Project's Branch. IE: `funkhaus:funkhaus` from `uptownhr:ISSUE-3`

## How to get paid

Venmmo or PayPal

## Timeline

Most components should take between 2-4 hours to complete. So please don't accept a component unless you plan on finishing it within the next 48 hours. If more than 48 hours pass since starting on a component, you will be removed from the component and it's free for someone else to claim.

### Code styleguide and expectations

- No outside libraries without asking. Here is a whitelist of approved ones:
  - lodash: https://lodash.com/
    - ([Be sure to only import functions you need](https://github.com/funkhaus/fuxt/blob/master/components/WpImage.vue#L41))
  - vue-prlx: http://vue-prlx.surge.sh/
- Sorry, no Tailwind (yet).
- What about animations?
  - Almost all transitions you'll be asked to do can be completed with the Vue `<transition>` component and CSS or JS hooks.

Explain included Linting, Prettier config etc..

Encourage use of TODO, FIXME, NOTE, QUESTION etc. We use Atom and the [TODO-SHOW](https://atom.io/packages/todo-show) package.

### Fonts

How to give out fonts to Devs? Webfontloader in storybook?

### Funkhaus best practices

Explain this: https://docs.google.com/presentation/d/1xMqvylzoIwpEgwFEpXI8it_HGo7BUGrt8h65E0nvEQo/edit?usp=sharing

### Mock data

All our data generally comes our of WordPress using the WP-GQL. But we've setup some ways to access the data easily.

#### Option 1 - Import file

The file `db.json` found in the root of this repo can be downloaded, and used in your components like this:

```
<template>
    <example-component :prop-name="api.pages"/>
<template>

<script>
import mockApi from "~/assets/db.json"
export default {
    data() {
        return {
            api: mockApi
        }
    }
}
</script>
```

#### Option 2 - API endpoints

Alternatively, you can access this the mock API via Typicode's JSON server like so:

- https://my-json-server.typicode.com/funkhaus/factory/image
- https://my-json-server.typicode.com/funkhaus/factory/images
- https://my-json-server.typicode.com/funkhaus/factory/images/cG9zdDoyODk=
- https://my-json-server.typicode.com/funkhaus/factory/page
- https://my-json-server.typicode.com/funkhaus/factory/pages

These endpoints just map to the contents of `db.json`, so feel free to dig into that file to find what you need.

## Resources

Include some good things to read here.

1.  Code examples?
1.  CSS guides?
1.  Vue/Nuxt docs?

## TODO

- Finish this documentation
- Build out GitHub issue tags for things like difficulty level, budget, ready for code review etc.
- Have a “project specification” issue template that defines global things like css vars or maybe design files? In component requests, like to the project spec.
