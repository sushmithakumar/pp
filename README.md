Memory Issue: ERROR: Failed to upload report - 500: An error has occurred. Please contact your administrator

Caused by: com.mysql.jdbc.PacketTooBigException: Packet for query is too large (5412578 > 4194304). You can change this value on the server by setting the max_allowed_packet' variable.

Resolution: This requires to increase max_allowed_packet from 4MB, so changed it to 32MB.
Steps:
              1)Create my.cnf with below content

cat my.cnf
[mysqld]
max_allowed_packet=32M

              2)Create configmap from file my.cnf
              kubectl create configmap sonar-mysql-cnf --from-file my.cnf
