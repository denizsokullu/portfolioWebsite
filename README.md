# Muse Connections Customization

An intelligent server that acts as an intermediary between an endpoint device and another server from which a user is requesting a service - a proxy. Using this proxy, you can intercept the response sent to a IBM Connections user and retheme, customize the DOM in various ways.

## Getting Started

This repository is for test purposes and it contains the scripts people inject to their view of IBM Connections sandbox server.


The way Connections knows that there is a script in this repository and it has to execute is via a JSON file that is added to the Organizations Extensions page.(https://your-domain-name-goes-here/appregistry/#displayApps)

###Formatting the JSON file
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
    "Muse" //This specifies the usage of the Muse service.
  ],
  "title": "title-that-isn't-needed-that-much",
  "app_id": "will-be-explained-in-a-later-section-with-url"
}
```
And here is an example usage scenario where there is only one extension added.

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
    "Muse" //This specifies the usage of the Muse service.
  ],
  "title": "title-that-isn't-needed-that-much",
  "app_id": "will-be-explained-in-a-later-section-with-url"
}
```


### Prerequisites


```
Give examples
```

### Installing

A step by step series of examples that tell you have to get a development env running

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone who's code was used
* Inspiration
* etc


