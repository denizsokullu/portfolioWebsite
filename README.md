# Muse Connections Customization

An intelligent server that acts as an intermediary between an endpoint device and another server from which a user is requesting a service - a proxy. Using this proxy, you can intercept the response sent to a IBM Connections user and retheme, customize the DOM in various ways.

## Getting Started

This repository is for test purposes and it contains the scripts people inject to their view of IBM Connections sandbox server.


The way Connections knows that there is a script in this repository and it has to execute is via a JSON file that is added to the Organizations Extensions page.(https://your-domain-name-goes-here/appregistry/#displayApps)

### Formatting the JSON file
Below is a boilerplate for a JSON Muse extension file.
```json
{
  "extensions": [
    {
      "application": "application-name",
      "payload": {
        "match": {
          "user-email": "your-email",
          "user-name": "your-name-as-it-is-on-Connections",
          "url": "will-be-explained-in-a-later-section"
        },
        "include-files": [
          "the-list-of-.js-files-you-want-to-include",
          "script1.js",
          "script2.js"
        ]
      },
      "name": "unique-name-for-this-extension-app",
      "type": "will-be-explained-in-a-later-section-with-url"
    }
  ],
  "name": "unique-name-for-your-whole-extension",
  "description": "description-goes-here",
  "services": [
    "Muse"
  ],
  "title": "title-that-isn't-needed-that-much",
  "app_id": "will-be-explained-in-a-later-section-with-url"
}
```
And here is an example usage where there is only one extension added.
```json
{
  "extensions": [
    {
      "application": "DPCHelloWorld",
      "payload": {
        "match": {
          "user-name": "Darren Cacy",
          "user-email": "darren.cacy@ibm.com",
          "url": "homepage"
        },
        "include-files": [
          "dcacy/HelloWorld.js"
        ]
      },
      "name": "DPC Hello World",
      "id": "ab7a762f-0ddd-43c6-a9b9-cfeaad0624ce",
      "type": "com.ibm.homepage"
    }
  ],
  "name": "DPCHelloWorld",
  "description": "Darren test",
  "services": [
    "Muse"
  ],
  "id": "9449783f-5ce1-43a1-bbdc-a75aaf86e35f",
  "title": "DPC Hello World Customizations",
  "app_id": "ibm.connections.homepage.dpc.helloworld"
}

```
* #### extensions.application, extensions.name, name, title
As long as these are descriptive to some level about the extension and different than the other extensions, it is fine.

* #### user-name and user-email
Only one of the user-name and user-email fields are enough to "match" to a request.

* #### id, extensions.id
You may be wondering about the id fields that got added. Those are uniquely created to tag this extension. Once you upload the JSON file on the applcations extension page, the id's get assigned automatically.

* #### url
To make the injections more specific, there is an url field which you can specify which section of connections it applies to.
	* "com.ibm.homepage"
	* "com.ibm.communities"
	* "com.ibm.files"
	* "com.ibm.meetings"
	* ADD MORE HERE


* #### type, app_\id
For type, the url and this field have to be matching. So for example:
```json
{
	"url": "homepage",
    "type": "com.ibm.homepage"
}
```
For app\_id, usually add your user-name and your extension name/title on the end of ibm.connections."your-url". For example:
```json
{
	"app_id": "ibm.connections.homepage.dpc.helloworld"
}
```


* #### include-files
This array includes the .js files that you want the Muse server execute before the client receives it. For directory, the base directory is the github repo base directory. Since this is a shared repo under i1, create a folder with your name, and place the scripts within that folder. The current repo link is https://github.ibm.com/i1/20433629.

### JS file content format

There is not much to restrict in here except make sure that you check that the DOM is ready before executing your script else your script may run into addressing undefined elements in the DOM.



