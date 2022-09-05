### Folder Description:

1.  **action-reducer**: This will contain a folder based on the reducer name, for example:

```
action-reducer/
  login/
    loginReducer.js
    loginConstants.js
    loginActions.js
```

Finally, it will also contain an `appReducer.js` where you can export all the reducers that you have created till now.

2.  **assets**: These consists of globally shared assest files.

```
assets/
  img
  audio
  video
  svg
```

3. **comp**: This is the heart of your code base. It will consist of all the components that you will be developing. 

4. **constants**: This folder will consist of all the constants that will be used in the app except reducer based and route based constants.

5. **helpers**: Any helper functions like a generic `toastifyHlp.js`, etc.

6. **hooks**: This contains any custom hooks that you create and use in your application.

7. **styles**: home for all css related files.

8. **utils**: This folder will contain routes, networks related and other constant files which is not suited in constants folder. 


### User Roles
1. **Admin**
2. **Teacher**
3. **Student**


### comp folder details
Folders are arranged by roles. User authendications are collected in Auth folder. General components are grouped in Common folder. UIComp contains all ui related files like Tab, DropDown etc.


### Important files in detail
* `utils/sendApiReq.js` is used to send api calls in our app through axios. This file exports a single function `sendApiReq` as default and exports `cookies`. It utilizes the axios instance and interceptors, so we can use every properties of axios directly. This function return the instance which is promise. Following are the default parameters, other properties can be passed directly. Use it within try-catch block. After successful api contract, we will get the data from this function

```js
isAuthendicated = true, // token will be passed default
headers = {} // additional headers
```

Example:
```js
  try {
    const resData = await	sendApiReq({
      method: '', // get | post | put | patch | delete (other methods of axios),
      url: '', // endpoint
      data: {}, // if needed
      baseUrl: '', // no-need to add, configured by default, but can be add to override the default
    })
    // you can destructure the resData

  } catch (error) {
    console.log(error)
  }
```


For detailed documentation of the codes and concepts, see `docs` folder in the root directory.