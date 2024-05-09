# So, you want to create a store?
It's easy, let's go

### In Nuxt2
- Create a folder called ```store``` in the root of the project
  - Inside this folder you will create your stores
- Create a new JSON file, name it whatever you want
  - In my case, I will create ```sharedData.json```
- In this json file, init it as a normal json, with ```{}``` and whatever you wants to store in it, for example:
  - ```{ userName: '', userEmail: '' }```
- If you want, you can already fill it with initial data, but I will let it empty
- Now create a ```index.js``` inside the ```store``` folder
  - In this file, we will fill the store with the initial data, that depends in some kind of EndPoint or whathever
- Start by importing all the stores you want to fill with initial data, in my case:
  - ```import sharedData from './sharedData.json'```
- Then create a function to fill data in this json file
  - ```
    const getData = async () => {
      fetch('myEndPointUrl')
        .then(response => response.json())
        .then(response => {
            sharedData.userName = response.userName;
            sharedData.userEmail = response.userEmail;
        })
    }
    ```
- To finish, we need to call this function somewhere, so we create a kind of "init" function:
  - ```
    (() => {
      getData();
    })();
    ```
- This will work with no problem, but it will keep giving you some errors on your dev console (Not the browser one), to avoid this you can validate is ```__filename``` exists. In the end you will have something like:
  - ```
    (() => {
      if (!__filename) return;

      getData();
    })();
    ```
  - To explain a little better. ```__filename``` is a node native variable, that returns the name of the file currently being runned. The nuxt server doesn't run the index.js file, so it won't have the ```__filename```. But the browsers it runs, so ```__filename``` starts existing
