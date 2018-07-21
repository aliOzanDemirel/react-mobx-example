This project is a simple application that is created to learn React and MobX. 
Since the purpose was only the frontend there is no backend to this basic
admin tool.

##### How to run

Checkout and navigate to project and run `yarn|npm start` from terminal to start dev server.

##### How to enable SSL for local development environment:
* react-scripts -> start.js uses webpack-dev-server -> lib -> Server.js, update below part to use custom certificate that you also use for your backend server:
```javascript
if (options.https) {
    if (typeof options.https === 'boolean') {
        options.https = {
            key: fs.readFileSync('/SOME_LOCAL_PATH/localhost.key'),
            cert: fs.readFileSync('/SOME_LOCAL_PATH/localhost.crt'),
            ca: fs.readFileSync('/SOME_LOCAL_PATH/localhost.crt'),
            pfx: options.pfx,
            passphrase: options.pfxPassphrase,
            requestCert: options.requestCert || false
        };
    }
}
```
* Use `HTTPS=true yarn start` to start with https enabled.

##### How to create docker image and run a container with that image:
* docker build -t react-mobx-docker-app .
* docker run -it -p 3000:3000 --rm react-mobx-docker-app
