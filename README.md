# cassandra-k8s
cassandra-k8s


https://kubernetes.io/docs/tutorials/stateful-application/cassandra/

 kubectl expose deployment hello-world --type=LoadBalancer --name=my-service

  kubectl expose deployment hello-world --type=LoadBalancer --name=my-service

Maheshs-MBP-2:cassandra-k8s maheshrajannan$ minikube service cassandra --url
http://192.168.99.106:32027
Maheshs-MBP-2:cassandra-k8s maheshrajannan$ 


CREATE KEYSPACE cycling
  WITH REPLICATION = { 
   'class' : 'SimpleStrategy', 
   'replication_factor' : 1 
  };

CREATE KEYSPACE cycling WITH REPLICATION = { 'class' : 'SimpleStrategy','replication_factor' : 1 };

WORKED

https://docs.datastax.com/en/cql-oss/3.3/cql/cql_reference/cqlCreateKeyspace.html

WORKED

CREATE KEYSPACE IF NOT EXISTS cycling WITH replication = {'class':'SimpleStrategy','replication_factor':1};

INFO: make sure you have semicolon at the end.


CREATE TABLE cycling.race_winners (race_name text, race_position int, cyclist_name FROZEN<fullname>, PRIMARY KEY (race_name, race_position));

did not work.

cqlsh> CREATE TABLE cycling.race_winners (race_name text, race_position int, cyclist_name FROZEN<fullname>, PRIMARY KEY (race_name, race_position));
InvalidRequest: Error from server: code=2200 [Invalid query] message="Unknown type cycling.fullname"

CREATE TABLE cycling.cyclist_category (
   category text, 
   points int, 
   id UUID, 
   lastname text, 
   PRIMARY KEY (category, points)) 
WITH CLUSTERING ORDER BY (points DESC);

ok. now what ?

Try this on gcloud ? Yes, that suits my career aspirations.



cqlsh> describe cycling.cyclist_category

CREATE TABLE cycling.cyclist_category (
    category text,
    points int,
    id uuid,
    lastname text,
    PRIMARY KEY (category, points)
) WITH CLUSTERING ORDER BY (points DESC)
    AND bloom_filter_fp_chance = 0.01
    AND caching = {'keys': 'ALL', 'rows_per_partition': 'NONE'}

cqlsh> describe tables;
