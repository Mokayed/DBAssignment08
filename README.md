<h1 align="center">DBAssignment08</h1>

<p>This is a solution for the following databases assignment: https://github.com/datsoftlyngby/soft2019spring-databases/blob/master/assignments/assignment8.md </p>

<h1>Users <g-emoji class="g-emoji" alias="page_with_curl" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f4c3.png">📃</g-emoji></h1>

<h3>Slave user</h3

<pre>
IP-Adresse: 159.65.199.41
</pre>
  
<pre>
Username: amsSlaveDroplet
</pre>
  
<pre>
Passworld: look on peergrade
</pre>
 
 <h3Master user</h3>
   
<pre>
IP-Adresse: 104.248.150.20
</pre>
 
<pre>
Username: hvn
</pre>
 
<pre>
 Passworld: look on peergrade
</pre>
 
 <h3Update timing for the tables in Europe </h3
 
 <pre>
 Time: more then 1 hour.
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


