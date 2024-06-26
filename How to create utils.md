# So, you want a utils file?
It's really simple to create one, let's see how:

### In Nuxt2
- Create a folder called ```utils``` in the root of the project
  - Inside this folder you will create your stores
- Create a new .js file, the name must explain what this utils contains
  - In my case, I will call it ``sanitize.js``
  - The util file MUST have JUST functions that make sense in this context, I won't create a `handleError` function inside my `sanitize.js`
    - You don't want to create a utils file just for a function? Unlucky you, you gonna do it =)
    - There is no problem in having just one function inside a utils file.
- In this file, write all the functions you want, for example:
  - ```
    const sanitizeCoinName = (coinName) => {
      return coinName.replaceAll(':', ' - ');
    }
    ```
  - You can make all the functions you want here, since it fits the "sanitize" context
- Nice, now we need to export it!
  - ```
    export {
      sanitizeCoinName
    }
    ```
- And done, you have a utils file! Now you just need to import wherever you want, you have two ways:
  - `import sanitize from '@/utils/sanitize.js`
  - `import { sanitizeCoinName } from  '@/utils/sanitize.js`
