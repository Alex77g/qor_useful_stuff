# Some stuff to make it easier to handle qor

## Install

you also need to have NodeJS installed, then install 'gulp' globally with npm and do npm install (in application root directory). 

Then pull go dependencies ( ```console go get -u ./... ``` from application root directory) -- this part may take a while and gives no feedback until error or done, so you can throw a ```console -v ``` switch in there (```console go get -u -v ./... ``` if you want feedback while it works).

Do not forget to edit the database connection information (edit ```console qor-example/config/config.go```).

Then run with ```console go run main.go``` or ```console go run -v main.go``` if you want some verbose output.

I recall having to piece all of this together myself (except for the ```console go get ./...``` part, that is actually there if you click the wiki link for the qor-example repo). 


## FAQ

### Images 404 error

install gvm (Go Version Manager)  
https://github.com/moovweb/gvm  

```console
gvm install go1.10.2
```    
you have to activate the version 1.10.2 in gvm
```console
gvm use go1.10.2
``` 
Linux:  
an then you have a new go directory ~/.gvm/...... linux for example  

Windows:  
I had originally go root c:\go  
GVM go root c:\users\myusername\go  

So you needed to copy over the qor-example\public\system to the new Go location.  

