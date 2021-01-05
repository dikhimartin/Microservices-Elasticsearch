# Elasticsearch + Kibana 7.10.1
A Distributed RESTful Search Engine

## Cara Menjalankan

```shell
cp .env.example .env
docker-compose up -d
```
<br/>

## Manage Kibana

### Server Running
```shell
http://127.0.0.1:5601
```
<br/>

## Manage Elasticsearch
### Server Running
```shell
http://127.0.0.1:9200
```

### Commands Cheat Sheet
```shell
http://127.0.0.1:9200/_cat
```
<br/>

### Create Index (Table)
```shell
PUT http://127.0.0.1:9200/{nama_index}
```
Referensi = https://www.elastic.co/guide/en/elasticsearch/reference/current/indices-create-index.html
<br/><br/>

### Insert Data  (Record)
```shell
PUT http://127.0.0.1:9200/{nama_index}/_doc/{id_document}
```
selanjutnya mendefinisikan field data sesuai dengan kebutuhan
```json
{
    "name_products" : "Produk 1",
    "stock"         : 1,
    "color"         : ["green","yellow","red"]
}
```
Referensi = https://www.elastic.co/guide/en/elasticsearch/reference/current/indices-create-index.html
<br/><br/>

### Edit Data  (Full Payload)
```shell
PUT http://127.0.0.1:9200/{nama_index}/_doc/{id_document}
```
Dengan menggunakan metode ini disarankan untuk melengkapi request JSON nya, karena nanti proses nya akan melakukan bulk update.
```json
{
    "name_products" : "Produk 1",
    "stock"         : 1,
    "color"         : ["green","yellow","red"]
}
```
<br/><br/>
### Edit Data  (Partial Field)
```shell
POST http://127.0.0.1:9200/{nama_index}/_update/{id_document}
```
Dengan menggunakan ini, data yang di ubah hanya request field yang di cantumkan saja di dalam JSON.
```json
{
    "doc" :{
        "name_products" : "Produk ",
    }
}
```
Referensi = https://www.elastic.co/guide/en/elasticsearch/reference/current/docs-update.html#update-api-example
<br/><br/>
### Delete Data  (Record)
```shell
DELETE http://127.0.0.1:9200/{nama_index}/_doc/{id_document}
```
Referensi = https://www.elastic.co/guide/en/elasticsearch/reference/current/docs-delete.html#docs-delete-api-example


<br/><br/>
### Documentation
https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html

### License
(c) 2019 Elasticsearch. Licensed under the Apache License, Version 2.0.





