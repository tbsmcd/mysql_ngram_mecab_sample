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

<img width="919" alt="screen shot" src="https://user-images.githubusercontent.com/174922/163512248-ee92374d-3038-4119-86b9-b23320ed5202.png">


```sql
SELECT *, MATCH(name) AGAINST('第2保育園' IN NATURAL LANGUAGE MODE) as score 
FROM nursery_ngram
ORDER BY score DESC;
```

<img width="1159" alt="screen shot" src="https://user-images.githubusercontent.com/174922/163512282-ff069c06-aa29-4d36-b176-eb9e035077a0.png">



```sql
SELECT *, MATCH(name_kana, name) AGAINST('太陽の子 さちが丘保育園' IN NATURAL LANGUAGE MODE) as score
FROM nursery_mecab
ORDER BY score DESC;
```

<img width="1038" alt="screen shot" src="https://user-images.githubusercontent.com/174922/163511962-84f186c2-b76c-4362-bf71-bd5f07060680.png">
