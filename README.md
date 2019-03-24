<h1 align="center">DBAssignment08</h1>

<p>This is a solution for the following databases assignment: https://github.com/datsoftlyngby/soft2019spring-databases/blob/master/assignments/assignment8.md </p>

<h1>Users <g-emoji class="g-emoji" alias="page_with_curl" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f4c3.png">📃</g-emoji></h1>

<h2>Slave user</h2>

<pre>
IP-Adresse: 159.65.199.41
</pre>
  
<pre>
Username: amsSlaveDroplet
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
 
 <h1>Setup a new salve user<g-emoji class="g-emoji" alias="checkered_flag" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f3c1.png">🏁</g-emoji></h1>
 
 <p>If you want to connect/create a new slave user, instead of "amsSlaveDroplet", use the following qurey to connect to our master database:</p>
 
```sql

CHANGE MASTER TO MASTER_HOST='104.248.150.20',
MASTER_USER='slave',
MASTER_PASSWORD='look on peergrade',
MASTER_LOG_FILE='mysql-bin.000001',
MASTER_LOG_POS=154;

```
<h2>You have to set up a mysql database on a droplet in singapore.</h2>
<h2>You have to equip that server with
the classicmodels database, and
a user with the right permissions to allow a slave to serve as a backup database</h2>
<h2>You have to set up a database somewhere in Europe (Frankfurt or Amsterdam) which is a replication slave of the Singapore database.</h2>
<h2>Make an insert in one of the tables in singapore, and see how long it takes for the tables in Europe to update.</h2>
<h2>Make a transaction of several updates on the Singapore database, and verify that no changes happens to the European database until after the commit of the transaction.</h2>

