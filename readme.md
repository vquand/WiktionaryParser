### Wiktionary Parser
Forked from Suyash458's work.

A python project which parses word content from Wiktionary in an easy to use JSON format.
Right now, it parses etymologies, definitions, pronunciations, examples, audio links and related words.

#### JSON structure

```json
[{
    "pronunciations": {
        "text": ["pronunciation text"],
        "audio": ["pronunciation audio"]
    },
    "definitions": [{
        "relatedWords": [{
            "relationshipType": "word relationship type",
            "words": ["list of related words"]
        }],
        "text": ["list of definitions"],
        "partOfSpeech": "part of speech",
        "examples": ["list of examples"]
    }],
    "etymology": "etymology text",
}]
```

#### Installation

##### Using pip 
Not available as I forked this for personal - educating purpose.

##### From Source
* Clone the repo or download the zip
* `cd` to the folder
* run `pip install -r "requirements.txt"`

#### Usage

 - Import the WiktionaryParser class.
 - Initialize an object and use the `fetch("word")` method. This will strictly support "Tiếng Việt", so no Language input is required for my usage.
 - Include/exclude parts of speech to be parsed using `include_part_of_speech(part_of_speech)` and `exclude_part_of_speech(part_of_speech)`
 - Include/exclude relations to be parsed using `include_relation(relation)` and `exclude_relation(relation)`

#### Examples

```python
>>> from wiktionaryparser import WiktionaryParser
>>> parser = WiktionaryParser()
>>> word = parser.fetch('test')
>>> parser.exclude_part_of_speech('noun')
>>> parser.include_relation('alternative forms')
```

#### Requirements

 - requests==2.20.0
 - beautifulsoup4==4.4.0

#### Contributions

If you want to add features/improvement or report issues, feel free to send a pull request!
If it is for Vietnamese, you can send PR here.
If it is for the general version, please refer to Suyash458's work.

#### License

Wiktionary Parser is licensed under [MIT](LICENSE.txt).
