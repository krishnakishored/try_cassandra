## Build the app using cmake
@ ~/coding/cpp-coding/try_cassandra
* `$ cmake -S . -B build`
* `$ cmake --build build` 

@ app/CMakeLists.txt



## Cassandra Docker Cheat Sheet
Common commands used when working with Cassandra and Docker:
========= Status =========  
#### Active containers  
$> docker ps  
#### Container Utilization  
$> docker stats  
#### Container Details  
$> docker inspect cppcassandra  
#### NodeTool Status  
$> docker exec -it cppcassandra nodetool status  

========== Logs ==========  
#### Server Logs  
$> docker logs cppcassandra  
#### System Out  
$> docker exec -it cppcassandra cat /var/log/cassandra/system.log  
#### Studio Logs  
$> docker logs my-studio  

==== Start/Stop/Remove ====  
#### Start Container  
$> docker start cppcassandra  
#### Stop Container  
$> docker stop cppcassandra  
#### Remove Container  
$> docker remove cppcassandra  

======= Additional =======    
#### Contaier IPAddress    
&> docker inspect cppcassandra | grep IPAddress  
#### CQL (Requires IPAddress from above)  
$> docker exec -it cppcassandra cqlsh [IPAddress]  
#### Bash  
$> docker exec -it cppcassandra bash  