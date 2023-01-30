# React Deployment

![image](https://user-images.githubusercontent.com/78524327/215464874-f01f8fe2-deee-4a2a-b479-e6870accea3b.png)
![image](https://user-images.githubusercontent.com/78524327/215464923-d0f31eb7-8be2-4624-86bc-5bfe9f9cab72.png)
![image](https://user-images.githubusercontent.com/78524327/215465027-e99cc7b7-ccc7-4cb0-98b9-142ceba774e9.png)

## Lazy Loading

#### 1.When our app is deployed , all the imports are loaded into the when the app starts.
#### 2.This makes the loading of our app very slow , especially if there are lots of components and hence , lots of imports.
#### 3.Lazy Loading is about loading or importing some code components when they are required and not all at once.
 
 Here ,we have demonstrated applying lazy loading on the other routes loader and element/Component.
 ```javascript
 import { lazy, Suspense } from 'react';
 // import BlogPage, { loader as postsLoader } from './pages/Blog';
 const BlogPage = lazy( () => import('./pages/Blog')); 
 
 
 //Route definition changes.
 //1.Standard way in which loader is now dynamically imported.
 //2.The lazily loaded component/page must be wrapped within a suspense element , as it takes time to load.
 
 { index: true, 
            element:
            <Suspense fallback={<p>Loading ... </p>}>
            <BlogPage />
            </Suspense>,
             loader:(metaData)=>import('./pages/Blog').then(module=>module.loader(metaData))
},

//Inside the import , the page path is given.
 
 ```
 
 ![image](https://user-images.githubusercontent.com/78524327/215467161-819209b9-3c3a-49c1-8914-5fbc31e60251.png)
 
 #### Firebase hosting was used for deployment here.Follow along with the vedio and the directions on the website.

 
 


