
* GET /words/?query&page_size&cursor
```
result -> {
  words: Word[]
  next_cursor: integer
  previous_cursor: integer
}
```
```
Word -> {
  id: ULID (regexp)
  value: string
  language: Language
  translate: [Language]:string
}
```

```
Language -> string with regexp isocode
```
(see cursor pagination used; see https://developer.twitter.com/en/docs/pagination)

* GET /words/[id]/ 
  * id as ULID
  * returns Word
* POST /words/ to add new word
  * body: Word (id field ignored)
* PUT /words/[id]/ to update word
  * body: Word (id field ignored)
* DELETE /words/[id]/ to delete word


* design flow-id to track request - https://opensource.zalando.com/restful-api-guidelines/#233
