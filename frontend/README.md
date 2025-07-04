# pax-avize frontend

There are two users of this app: operators and cashiers.
The operator does his business at `<root_url>/operator`, where he can submit new orders (ro: "avize")
and view previous ones, possibly editing them.
The chashier page can be accessed simply at `<root_url>`. However, the cashier would really
want to use the electron-built desktop app, which allows him to drag-and-drop an into the
cash-in software SAGA C. (Integration with other similar software is in principle possible)
This has to be a desktop app, because browsers do not allow elements from the web content to be
drag-and-dropped as files.

The electron app is also in this folder, as it simply packages the root page, and does some additional handling to treat the drag-and-drop
as a native file drag-and-drop, as in when one drags a file from a file explorer to another window.
## Project setup
```
npm install
```

### Compile and hot-reload for development (browser version)
Since this app is using a backend, you should point the frontend to the backend url by creating a file `.env.development`, for instance with the following content:
```
VUE_APP_BASE_URL=http://localhost:8082
```

Then run 
```
npm run serve
```

### Compiles and minifies for production (browser version)
```
npm run build
```
(the resulting files, which can be served from any http server, is placed in the `dist` folder)
### Lints and fixes files
```
npm run lint
```

### Run electron app for development
```
npm run electron:serve
```

### Build electron windows executable
```
npm run electron:build -- --win
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
