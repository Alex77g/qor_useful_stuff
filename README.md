# Some useful QOR stuff

## Install

you also need to have NodeJS installed, then install 'gulp' globally ``` npm install -g gulp ``` with npm and do ``` npm install ``` (in application root directory). 

Then pull go dependencies ( ``` go get -u ./... ``` from application root directory) -- this part may take a while and gives no feedback until error or done, so you can throw a ``` -v ``` switch in there (``` go get -u -v ./... ``` if you want feedback while it works).

Do not forget to edit the database connection information (edit ``` qor-example/config/config.go```).

Then run with ``` go run main.go``` or ``` go run -v main.go``` if you want some verbose output.

I recall having to piece all of this together myself (except for the ``` go get ./...``` part, that is actually there if you click the wiki link for the qor-example repo). 

## Debug Mode

enable debug on linux/mac with export ``` export DEBUG=true``` or windows set ``` DEBUG=true``` then run the app

## FAQ

### Images 404 error

install gvm (Go Version Manager)  
https://github.com/moovweb/gvm  

```
gvm install go1.10.2
```    
you have to activate the version 1.10.2 in gvm
```
gvm use go1.10.2
``` 
Linux:  
an then you have a new go directory ~/.gvm/...... linux for example  

Windows:  
I had originally go root c:\go  
GVM go root c:\users\myusername\go  

So you needed to copy over the qor-example\public\system to the new Go location.  

### VS Code Config
```
    // Verwendet IntelliSense zum Ermitteln möglicher Attribute.
    // Zeigen Sie auf vorhandene Attribute, um die zugehörigen Beschreibungen anzuzeigen.
    // Weitere Informationen finden Sie unter https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [

        {
            "name": "Launch",
            "type": "go",
            "request": "launch",
            "mode": "debug",
            "remotePath": "",
            "port": 2345,
            "host": "127.0.0.1",
            "program": "${workspaceRoot}",
            "env": {"DEBUG" : true}, //damit geneu gelistet wird, bei welcher codezeile der Abfrage ausgeführt wird
            "args": [],
            "showLog": true
        }
    ]
}
```
### Styles

build scss 
``` gulp sass ```

### Security

https://blog.rapid7.com/2016/07/13/quick-security-wins-in-golang/

### Docker 

#### Minimal:

```
FROM golang
ENV PORT 7000
EXPOSE 7000

WORKDIR /go/src/YOURPROJ
COPY . .

RUN go get

ENTRYPOINT go run main.go
```
