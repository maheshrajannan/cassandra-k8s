Issues faced and their resolution.


❗  'hyperkit' driver reported an issue: the installed hyperkit version (0.20180403) is older than the minimum recommended version (0.20190201)
💡  Suggestion: Run 'brew upgrade hyperkit'
📘  Documentation: https://minikube.sigs.k8s.io/docs/reference/drivers/hyperkit/

minikube start --vm-driver=virtualbox

minikube start --memory 5120 --cpus=4 --vm-driver=virtualbox

sudo pip3 install clash

Maheshs-MBP-2:cassandra-k8s maheshrajannan$ cqlsh
  File "/usr/local/bin/cqlsh", line 121
    except ImportError, e:
                      ^
SyntaxError: invalid syntax
https://stackoverflow.com/questions/48219304/cassandra-cqlsh-line-145-except-importerror-e-syntaxerror-invalid-syntax?rq=1

sudo python2.7 -m pip install cqlsh

Maheshs-MBP-2:cassandra-k8s maheshrajannan$ cqlsh 192.168.99.106 32027
Connection error: ('Unable to connect to any servers', {'192.168.99.106:32027': ProtocolError("cql_version '3.3.1' is not supported by remote (w/ native protocol). Supported versions: [u'3.4.4']",)})
Maheshs-MBP-2:cassandra-k8s maheshrajannan$ 

Maheshs-MBP-2:cassandra-k8s maheshrajannan$ vi ~/.cassandra/cqlshrc
Maheshs-MBP-2:cassandra-k8s maheshrajannan$ cqlsh –cqlversion=3.4.4

Maheshs-MBP-2:cassandra-k8s maheshrajannan$ cqlsh 192.168.99.106 32027 –cqlversion=3.4.4
Connected to K8Demo at 192.168.99.106:32027.
[cqlsh 5.0.1 | Cassandra 3.11.2 | CQL spec 3.4.4 | Native protocol v4]
Use HELP for help.
cqlsh> 

https://github.com/kradio3/kubernetes-cassandra

https://github.com/kradio3/kubernetes-cassandra <— worked
https://towardsdatascience.com/when-to-use-cassandra-and-when-to-steer-clear-72b7f2cede76

BigData References

KAFKA

https://www.confluent.io/blog/apache-kafka-kubernetes-could-you-should-you/

https://kafka.apache.org/uses

https://www.baeldung.com/spring-kafka

https://www.baeldung.com/spring-data-cassandra-tutorial

https://www.confluent.io/blog/apache-kafka-kubernetes-could-you-should-you/

https://github.com/Yolean/kubernetes-kafka

Cassandra


https://medium.com/flant-com/running-cassandra-in-kubernetes-challenges-and-solutions-9082045a7d93

https://kubernetes.io/docs/tutorials/stateful-application/cassandra/

Install KAFKA KAT it is under git/kubernetes-kafka

https://towardsdatascience.com/when-to-use-cassandra-and-when-to-steer-clear-72b7f2cede76