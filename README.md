## IBM Watson Text-To-Speech PHP Library

Convert written text into natural-sounding audio in a variety of languages and voices.  
This package use [IBM Watson Text To Speech](https://www.ibm.com/watson/services/text-to-speech/) service.

### Using the Library
#### Installation

Intall library in PHP project using composer
```
composer require tbetool/ibm-watson-tts
```

#### Using Library
After installing the library, create `WatsonTts` object
```
$watson = new WatsonTts(
    'watson_username', 
    'watson_password', 
    'watson_url'
);
```
Watson `username, password, url` can be obtained by creating an instance of service. For more detail follow [Getting Started Guide](https://console.bluemix.net/docs/services/text-to-speech/getting-started.html#gettingStarted).

#### Setting output path
Set absolute path of the directory where to save the output. You don't need to provide a file name as it will be auto generated.
```
$path = '/aboslute/path/to/directory';

$watson->setOutputPath($path);
```

#### Convert Text to Speech
Pass text to convert to speech.
```
$file = $watson->tts('Hello World');
```
This will return the absolute path of the file created if text to speech conversion is successful, otherwise will throw Exception.

### Other callable methods
##### Set Audio Format
```
$watson->setAudioFormat('wav');
```
**allowed formats:** `wav`, `ogg`  
**Default:** `wav`
##### Set Language
```
$watson->setLanguage('en');
```
**allowed languages:** `en`  
**default:** `en`
##### Set Voice
```
$watson->setVoice('US_MichaelVoice');
``` 
**allowed voices:** `US_MichaelVoice`  
**default:** `US_MichaelVoice`

### Bug Reporting
If you found any bug, create an [issue]().

### Support and Contribution
Something is missing? 
* `Fork` the repositroy
* Make your contribution
* make a `pull request`

### Developer
* [Anuj Sharma](https://anujsh.gitlab.io)