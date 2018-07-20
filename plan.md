# Full stack review plan - Simulation 3

## Front-end

* Components 
    * Class comp
        * Auth
        * Dashboard 
        * Form 
        * Post 
    * Func comp
        * Nav

* Redux
    * Store
    * Reducer 
        * initial state
            * username 
            * profile 
            * userId
        * reducer function
        * Action creators
            * update user information
            * clear user information
        * Action type names (constants)
            * UPDATE_USER_INFO 
            * CLEAR_USER_INFO
    
* Index.js (in root directory) 
    * BrowserRouter
    * Provider 
        * store

* Files 
    * /src
        * App.js 
            - no state
            - no methods 
        * Nav.js 
            - no state
            - no methods
        * Dashboard.js 
            - state
            posts: []
            search: ''
            userposts: true
            - method 
            get all posts from database
            reset search
        * Posts.js 
            - state
            title: ''
            img: '' 
            content: '' 
            author: ''
            authorPicture: '' 
            - method 
            get post information 
        * Form.js 
            - state
            title: ''
            img: ''
            content: ''
            - method 
            handle change (3)
            submit new post 
        * routes.js 
            * / (Auth)
            * /dashboard (Dashboard)
            * /post/:postid (Post)
            * /new (Form)
        * /redux
            * store.js
            * reducer.js


## Back-end
 
* Routes 


    * /api/auth/register
        * POST
    Receive: req.body {
        username: 'example',
        password: 'password1'
    }
    Send: {
        username: 'example',
        profile: 'https://google.com/image.png'
        userId: 4
    }


    * /api/auth/login
        * POST 
    Receive: req.body {
        username: 'example',
        password: 'password1'
    }
    Send: {
        username: 'example',
        profile: 'https://google.com/image.png',
        userId: 4
    }


    * /api/posts/:userid
        * GET 
    Receive: req.params.userid 4 
    req.query {
        search: 'Example',
        userposts: true
    }
    Send: [
        {
            title: 'Title',
            author: 'example',
            authorPic: 'https://google.com/image.png'
        }
    ]


    * /api/post/:userid
        * POST
    Receive: req.params.userid 4 
    req.body {
        title: 'Title',
        img: 'https://google.com/cat.png',
        content: 'I am a blog post'
    }
    Send: status 200


    * /api/post/:postid 
        * GET 
    Receive: req.params.postid 76
    Send: {
        title: 'Title',
        img: 'https://google.com/cat.png',
        content: 'I am a blog post',
        author: 'example',
        authorPicture: 'https://google.com/image.png'
    }

    * /api/auth/logout
        * POST 
    req.session.destroy()


    * /auth/callback
    * auth 
        * Auth0 


* Files 
    * /server
        * index.js
        * controller.js 
    
## Database 

* tables 
    * users
        * id SERIAL PRIMARY KEY
        * auth0_id TEXT
        * username VARCHAR(20)
        * password VARCHAR(20)
        * profile_pic TEXT
    * posts
        * id SERIAL PRIMARY KEY
        * title VARCHAR(45)
        * img TEXT
        * content TEXT
        * author_id INTEGER REFERENCES users (id)
* files 
    * /db 
      * init.sql 
      * create_user.sql
      * read_user.sql
      * read_posts.sql
      * read_post.sql
      * create_post.sql



## NPM Packages
* axios 
* express 
* massive 
* body-parser
* dotenv 
* express-session
* redux 
* react-redux 
* react-router-dom 

## Third party 

* Auth0 
    * Application 
    * Social connections
* Github 
* Heroku 
* Postman
* Redux DevTools 
* React DevTools 
* SQL Tabs
* Chrome 
    * DevTools
        * Network tab