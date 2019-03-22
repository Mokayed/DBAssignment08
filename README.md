<h1 align="center">DBAssignment08</h1>

<h2>Slave user</h2>
 login in to that slave user
 <p>IP-Adresse: 159.65.199.41/<p>
 <p>Username: amsSlaveDroplet</p>
  <p>Passworld: P@ssword1 </p>
 
 <h2>Master user</h2>
 
 
 
 <p>If you want to connect/create a new slave user use the following command</p>
'''sql

CHANGE MASTER TO MASTER_HOST='104.248.150.20',
MASTER_USER='slave',
MASTER_PASSWORD='P@ssword1',
MASTER_LOG_FILE='mysql-bin.000001',
MASTER_LOG_POS=154;

'''
