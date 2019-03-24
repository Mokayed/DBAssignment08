<h1 align="center">DBAssignment08</h1>

<p>This is a solution for the following databases assignment: https://github.com/datsoftlyngby/soft2019spring-databases/blob/master/assignments/assignment8.md </p>

<h1>Users <g-emoji class="g-emoji" alias="page_with_curl" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f4c3.png">📃</g-emoji></h1>

<h2>Slave user</h2>

<pre>
IP-Adresse: 159.65.199.41
</pre>
  
<pre>
Username: slaveams
</pre>
  
<pre>
Passworld: look on peergrade
</pre>
 
 <h2>Master user</h2>
   
<pre>
IP-Adresse: 104.248.150.20
</pre>
 
<pre>
Username: hvn
</pre>
 
<pre>
 Passworld: look on peergrade
</pre>
 
 <h2>Update timing for the tables in Europe </h2>
 
 <pre>
 Time: 1:36 hour.
</pre>
 
<h2>You have to set up a mysql database on a droplet in singapore.</h2>

<p>We purchased a 1 gb server from digitalocean with the location of Singapore. After setting it up we then installed mysql 
  
following the instructions</p>

<h2>You have to equip that server with
the classicmodels database, and
a user with the right permissions to allow a slave to serve as a backup database</h2>

<p>We opened the classicmodels dump in workbench and executed it. Afterwards we then made the slave using this command: </p>

```sql
create user 'slave'@'%' identified by '###check peergrade###';

grant replication slave on *.* to 'slave'@'%';
```
<p>we also changed the mysqld.cnf file in order to make it all work. server-id		= 1, log_bin			= mysql-bin,
binlog_do_db		= classicmodels, bind-address		= 104.248.150.20</p>

<h2>You have to set up a database somewhere in Europe (Frankfurt or Amsterdam) which is a replication slave of the Singapore database.
</h2>

<p>We then purchased another droplet (for the slave server) in amsterdam, and also installed mysql on there.
We changed the mysqld.cnf file to server-id = 2 and bind-address = 159.65.199.41. Then we logged in with root and took a dump file we had made from the master server, then we made the connection to the slave:</p>
  
  ```sql
  CHANGE MASTER TO MASTER_HOST='104.248.150.20',
  MASTER_USER='slave',
  MASTER_PASSWORD='###check peergrade###'
  ```
  ```sql
  START SLAVE;
   ```

<h2>Make an insert in one of the tables in singapore, and see how long it takes for the tables in Europe to update.</h2>

<p>we inserted a new office and it took a long time to wait on the slave server</p>

<h2>Make a transaction of several updates on the Singapore database, and verify that no changes happens to the European database until after the commit of the transaction.</h2>

<p>We can verify that we did not see any update changes until we started using commit</p>

 <h1>Setup a new salve user<g-emoji class="g-emoji" alias="checkered_flag" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f3c1.png">🏁</g-emoji></h1>
 
 <p>If you want to connect/create a new slave user, instead of "amsSlaveDroplet", use the following qurey to connect to our master database:</p>
 
```sql

CHANGE MASTER TO MASTER_HOST='104.248.150.20',
MASTER_USER='slave',
MASTER_PASSWORD='look on peergrade',
MASTER_LOG_FILE='mysql-bin.000001',
MASTER_LOG_POS=154;

```
