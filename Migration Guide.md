# Migrating from Nuxt2 (Vue2) to Nuxt3 (Vue3)

### A small recommendation

- Check out how Vue3 or even Nuxt3 works, try to create a small test app with it, to get along with the new functionalities
- I also recommend to check into TypeScrpit, just the basics are enough

## Step 1 - Getting rid of unnecessary things

#### Libraries and what-not

- This is a good time to clean our project.
- Check ALL the dependecies you have in the project, are they really necessary?
- If they aren't, get rid of them
- If they are necessary, but easily replaceable, get rid of it and create a .js file to replace it
- A good example is [this](https://www.npmjs.com/package/is-odd) package. Can be usefull but a simple .js file can do the work.

#### Necessary or usefull libraries

- Now that we have just necessaries libraries left, are they compatible with Vue3?
- If no, we will need to find a replacement, or create our own
- This is also a good way to get rid of deprecated libs, that are not maintaned anymore

## Step 2 - Clean the config files

- It is normal no have a lot of congi files in our project, but some of them will change the syntax
- So, let's clean it, do we really need all the configs there?
- If I remove line 34, it will stop working?
- Is that config really helping me to do something?

## Step 3 - The "Scout Way"

- Now that we got rid of everything unnecessary, we can start rewritting some code
- This can be time-demanding, so let's use the "scot way"
- Replace ALL your code with the new libraries you just wrote or updated
- ALL the new things you write, write in the new way (We also have a [guide](https://github.com/ToMattBan/a-guide-to-follow/blob/main/README.md) to follow)
- When comming back to a old file, CLEAN it and REWRITE what needs to be rewritted
- You can do it with time, or when you have some free time.

## Step 4 - Starting the Nuxt3 project

#### Creating a new project

- The official docs shows how to turn your Nuxt2 into a Nuxt3 project, but I don't like it
- Instead, let's take the chance to get it clean!
- So, let's create a NEW Nuxt3 project. `npx nuxi@latest init`
- Great! Now create a "page" folder, and put `app.vue` inside it, renaming it to `index.vue`
- Rewrite the config files as needed, you can have the docs help to see where every thing needs to go

#### Testing stuff

- Now that we have a new project, let's start testing some real stuff before bringing it the code
- Creates a new page, or uses the index.vue to test things like api calls and auth.

## Step 5 - Start moving things

#### Where do my files go?

- The directory structure didn't changed much, to be honest, just the `static` folder that turned into `public`
- For this guide, we also will rename `plugin` folder to `composables`

#### And what about my stores? And my utils?

- Well, you can just read the updated stores guide [here](https://github.com/ToMattBan/a-guide-to-follow/blob/main/How%20create%20and%20use%20stores.md)
- Lucky you we also have a updated utils guide [here](https://github.com/ToMattBan/a-guide-to-follow/blob/main/How%20to%20create%20utils.md)
- Just a heads up: Utils just deals with static data, composables deals with reactive data!
- This is a good time to addapt everything to use TypeScript!
