<h1 align="center">DBAssignment08</h1>

<p>This is a solution for the following databases assignment: https://github.com/datsoftlyngby/soft2019spring-databases/blob/master/assignments/assignment8.md </p>

<h1>Users <g-emoji class="g-emoji" alias="page_with_curl" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f4c3.png">📃</g-emoji></h1>

<h2>Slave user</h2>

<pre><code>
 <IP-Adresse: 159.65.199.41
  </code></pre>
  
 <pre><code>
 Username: amsSlaveDroplet
  </code></pre>
  
 <pre><code>
  <p>Passworld: look on peergrade</p>
 </code></pre>
 
 <h2>Master user</h2>
   
 <pre><code>
 IP-Adresse: 104.248.150.20<p>
 </code></pre>
 
 <pre><code>
 <p>Username: hvn
 </code></pre>
 
 <pre><code>
  <p>Passworld: look on peergrade
 </code></pre>
 
 <h1>Setup if needed <g-emoji class="g-emoji" alias="checkered_flag" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f3c1.png">🏁</g-emoji></h1>
 <p>If you want to connect/create a new slave user use the following command  </p>
 
```sql

CHANGE MASTER TO MASTER_HOST='104.248.150.20',
MASTER_USER='slave',
MASTER_PASSWORD='P@ssword1',
MASTER_LOG_FILE='mysql-bin.000001',
MASTER_LOG_POS=154;

```
<pre><code>Amount of operations to enqueue last item of 10000 was 14

</code></pre>
