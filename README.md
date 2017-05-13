# elasticsearch-logstash-kibana




To create an index say 'customer'

curl -XPUT http://localhost:9200/customer?pretty

To list all the indicies

curl -XGET http://localhost:9200/_cat/indices?v

health status index    uuid                   pri rep docs.count docs.deleted store.size pri.store.size
yellow open   customer Wgx6Y01vQEKtNBi6puh9fQ   5   1          0            0       650b           650b
yellow open   twitter  EfLFvAiuShm8tJ70h24vEA   5   1          1            0      4.9kb          4.9kb
Vinods-MacBook-Pro:~ vinodkottem$ 

create an document in customer index

Vinods-MacBook-Pro:~ vinodkottem$ curl -XPUT 'localhost:9200/customer/external/1?pretty&pretty' -H 'Content-Type: application/json' -d'
> {
>   "name": "John Doe"
> }
> '
{
  "_index" : "customer",
  "_type" : "external",
  "_id" : "1",
  "_version" : 1,
  "result" : "created",
  "_shards" : {
    "total" : 2,
    "successful" : 1,
    "failed" : 0
  },
  "created" : true
}
Vinods-MacBook-Pro:~ vinodkottem$ 

to deleet an index
curl -XDELETE 'localhost:9200/customer?pretty&pretty'
curl -XGET 'localhost:9200/_cat/indices?v&pretty'

