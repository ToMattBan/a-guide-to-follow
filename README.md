# A GUIDE TO FOLLOW

#### General thoughts
- This is a guide to be used with Vue
- Idealized to be used with Nuxt2, but can be used with others versions as well

</br>

# About names
### Everything
- Names must use camelCase
  - ```buttonColor``` instead of anything else
- Names must have no more than 3 words
  - ```crypoSelected``` instead of ```theLastCryptoThatTheUserSelected```

### Props
- Vue accept kebab-case when passing props, but all props should de camelCase
  - ```<component userName="" />``` instead of ```<component user-name="" />```

### Components
- Components must start with a capital letter
  - ```MyComponent``` instead of ```my-component``` or ```myComponent```
- Components must have at least two words
  - ```MainHeader``` instead of ```Header```
- It should start with the context
  - ```ClearSearchButton``` instead of ```ButtonToClearSearch```
- If the component is a modal it must end with "Modal"
  - ```MyComponentModal``` instead of ```my-component-modal``` or ```MyComponent```
 
### Utils
- The name of the util file must explain what kind of util functions the file have
  - `errors.js` instead of `utils.js`
- Don't know how to create a util file/function? [Read this and learn by yourself](https://github.com/ToMattBan/a-guide-to-follow/blob/main/How%20to%20create%20utils.md)
</br>

# About components
### Where to put them?
- Componentes that are not a page must be in the components folder
  - The component folder must be divided in what type that component is
  - For example, modals must be on ```/components/modals```
 
### What are they about?
- They should have just one use, no more, no less.
  - A button will always be a button. A successModal will always be just a successModal
- Ps.: Don't fear in create a component that just wrapp two or three other components, changing just the props.
 
### When?
- When your page have too much code and you want to split it
- When you are repeating a lot of code

### How to organize them?
- First `template` then `script` and end with `style`
- NEVER use logic on the template, instead, use a computed, a function, a watch, a ref, anything but to put the logic on template
- ALWAYS use `scoped` on your style, and if you need to style a extern component, put everything inside a container with an id and use this id in the styles, so the css won't change anything besides this component:
  ```<template> <div id="uniqueContainerID">{{ content }}</div>``` </br>
  ```<style lang="scss"> #uniqueContainerID { everyRuleInsideThisSelector } </style>```

</br>

# About how should I write this damn thing?
### Directives
- Always use shorthands!
  - `:src="imageSrc"` instead of `v-bind:src="imageSrc"`
  - `@click="clickHandler"` instead of `v-on:click="clickHandler"`

</br>

# Stores
### How to create a store and other things?
- [Read this and learn by yourself](https://github.com/ToMattBan/a-guide-to-follow/blob/main/How%20create%20stores.md)

</br>

# Props
### How create props?
- NEVER just declare props
- ALWAYS give context, at least, their type
- `props: { title: String }` 
  or
  ```
  props:{ 
    title: { 
      type: String, 
      required: true 
    }
  }
  ``` 
  instead of ```props: ['title']```

</br>

# Store or props?
### When use store?
- Your component is independent
- Your component use the data from the store, but the parent doesn't
- Pages, as they don't have props

### When use props?
- Your component have a parent that use the same data
  - So you will import the store in the parent and pass just the data the child component needs via props
