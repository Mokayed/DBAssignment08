<h1 align="center">DBAssignment08</h1>

<h1>Users</h1>

<h2>Slave user</h2>
 <p>IP-Adresse: 159.65.199.41<p>
 <p>Username: amsSlaveDroplet</p>
  <p>Passworld: look on peergrade</p>
 
 <h2>Master user</h2>
 
 <p>IP-Adresse: 104.248.150.20<p>
 <p>Username: hvn</p>
  <p>Passworld: look on peergrade</p>
 
 <h1>Setup if needed</h1>
 <p>If you want to connect/create a new slave user use the following command  <g-emoji class="g-emoji" alias="checkered_flag" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f3c1.png">🏁</g-emoji</p>
 
```sql

CHANGE MASTER TO MASTER_HOST='104.248.150.20',
MASTER_USER='slave',
MASTER_PASSWORD='P@ssword1',
MASTER_LOG_FILE='mysql-bin.000001',
MASTER_LOG_POS=154;

```
