# Freeradius
Set the ip-range which will connect to the server and the server-secret in [clients.conf](https://github.com/marcelmaatkamp/docker-compose-applications/blob/master/freeradius/clients.conf), set the user/password combination in [users](https://github.com/marcelmaatkamp/docker-compose-applications/blob/master/freeradius/users). 

## Start the server
```
$ docker-compose up -d freeradius
```

## Start a test radius connection
```
$ docker-compose up freeradius-test
```
The docker-compose.yml contains a container called 'freeradius-test' which will send a auth-request to the server which after succes will print
```
freeradius-test_1  | Sending Access-Request of id 95 to 172.25.0.100 port 1812
freeradius-test_1  | 	User-Name = "testing"
freeradius-test_1  | 	User-Password = "password"
freeradius-test_1  | 	NAS-IP-Address = 172.25.0.101
freeradius-test_1  | 	NAS-Port = 0
freeradius-test_1  | 	Message-Authenticator = 0x00000000000000000000000000000000
freeradius-test_1  | rad_recv: Access-Accept packet from host 172.25.0.100 port 1812, id=95, length=20
```
