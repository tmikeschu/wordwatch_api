# Word Watch API

Word Watch tracks frequently used words. You can POST words to the database, and
GET the most used word to date.

## Base URL: https://wordwatch-api.herokuapp.com

|Verb|Path|Body|Response|
|---|---|---|---|
|`GET`|`/api/v1/top_word`||`"{\"value\":\"Mike\"}"`|
|`POST`|`/api/v1/words`|`{ word: { value: "sample" } }`|`{ message: "sample added!" }`|

*Note*: the word values are stored as `citext` types, so "Chair", "ChAiR", and
"chair" all count towards the count of "chair".

## Environment Setup

```shell
bundle install
rake db:{create,migrate}
rspec
rails s
```
