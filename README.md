## IBM Watson Text-To-Speech PHP Library

Convert written text into natural-sounding audio in a variety of languages and voices.  
This package use [IBM Watson Text To Speech](https://www.ibm.com/watson/services/text-to-speech/) service.

---
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

---
### Exception handling

Every function throws an Exception in case of any error/issue. Bind the code block within `try-catch` block to catch any exception occurred.

_Ex:_
```
try {
    $watson->setAudioFormat('mp3');
} catch (Exception $exception) {
    echo $exception->getMessage();
}
```
will throw and exception `Not a valid audio format. Allowed formats: wav, ogg` as `mp3` audio format is not supported as of now

---
### Other callable methods

##### Set Audio Format
```
$watson->setAudioFormat('wav');
```
_allowed formats:_ `wav`, `ogg`  
_default:_ `wav`
##### Set Language
```
$watson->setLanguage('en-US');
```
_allowed languages:_ [See List](#supported-language-and-voice-list)  
_default:_ `en-US`
##### Set Voice
```
$watson->setVoice('MichaelVoice');
``` 
_allowed voices:_ [See List](#supported-language-and-voice-list)  
_default:_ `MichaelVoice`

---
### Supported language and voice list
list of supported language and voice strings

Name | language | voice | gender | description
--- | --- | --- | --- | ---
es-LA_SofiaVoice | **es-LA** | **SofiaVoice** | female | Sofia: Latin American Spanish (español latinoamericano) female voice.
pt-BR_IsabelaVoice | **pt-BR** | **IsabelaVoice** | female | Isabela: Brazilian Portuguese (português brasileiro) female voice.
en-GB_KateVoice | **en-GB** | **KateVoice** | female | Kate: British English female voice.
de-DE_BirgitVoice | **de-DE** | **BirgitVoice** | female | Birgit: Standard German of Germany (Standarddeutsch) female voice.
en-US_AllisonVoice | **en-US** | **AllisonVoice** | female | Allison: American English female voice.
fr-FR_ReneeVoice | **fr-FR** | **ReneeVoice** | female | Renee: French (français) female voice.
it-IT_FrancescaVoice | **it-IT** | **FrancescaVoice** | female | Francesca: Italian (italiano) female voice.
es-ES_LauraVoice | **es-ES** | **LauraVoice** | female | Laura: Castilian Spanish (español castellano) female voice.
ja-JP_EmiVoice | **ja-JP** | **EmiVoice** | female | Emi: Japanese (日本語) female voice.
es-ES_EnriqueVoice | **es-ES** | **EnriqueVoice** | male | Enrique: Castilian Spanish (español castellano) male voice.
de-DE_DieterVoice | **de-DE** | **DieterVoice** | male | Dieter: Standard German of Germany (Standarddeutsch) male voice.
en-US_LisaVoice | **en-US** | **LisaVoice** | female | Lisa: American English female voice.
en-US_MichaelVoice | **en-US** | **MichaelVoice** | male | Michael: American English male voice.
es-US_SofiaVoice | **es-US** | **SofiaVoice** | female | Sofia: North American Spanish (español norteamericano) female voice.

---
### Bug Reporting

If you found any bug, create an [issue](https://github.com/TBETool/ibm-watson-tts-php/issues/new).

---
### Support and Contribution

Something is missing? 
* `Fork` the repositroy
* Make your contribution
* make a `pull request`

---
### Developer
* [Anuj Sharma](https://anujsh.gitlab.io)
