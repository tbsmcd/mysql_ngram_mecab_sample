# MySQL + ngram/mecab Sample.

## Usage

### Launch the docker container.
```zsh
$ docker-compose up
```

### Access from a Web browser.

[PhpMyAdmin](http://localhost:8080/)

### Try executing a select statement

```sql
SELECT *, MATCH(name) AGAINST('第2保育園' IN NATURAL LANGUAGE MODE) as score
FROM nursery_mecab
ORDER BY score DESC;
```

<img width="919" alt="スクリーンショット 2022-04-14 16 19 37" src="https://user-images.githubusercontent.com/174922/163334451-dafc25b2-d222-4f89-b46a-d422f34dca31.png">


```sql
SELECT *, MATCH(name) AGAINST('第2保育園' IN NATURAL LANGUAGE MODE) as score 
FROM nursery_ngram
ORDER BY score DESC;
```

<img width="1159" alt="スクリーンショット 2022-04-14 16 20 18" src="https://user-images.githubusercontent.com/174922/163334469-4afde020-e6f3-43f8-9c63-b1300f747be4.png">


```sql
SELECT *, MATCH(name_kana, name) AGAINST('太陽の子 さちが丘保育園' IN NATURAL LANGUAGE MODE) as score
FROM nursery_mecab
ORDER BY score DESC;
```

<img width="1038" alt="スクリーンショット 2022-04-15 12 07 37" src="https://user-images.githubusercontent.com/174922/163511962-84f186c2-b76c-4362-bf71-bd5f07060680.png">
