mongod --dbpath /home/linuxbrew/data/mongodb &

mongod --dbpath /home/linuxbrew/data/mongodb --shutdown

mongod --auth --dbpath /home/linuxbrew/data/mongodb &

mongod --auth --dbpath /home/linuxbrew/data/mongodb --shutdown

mongo --port 27017 -u "adminUser" -p "adminPass" --authenticationDatabase "admin"

mongo --port 27017
use admin
db.auth("adminUser", "adminPass")

创建管理员用户
use admin

db.createUser(
  {
    user: "adminUser",
    pwd: "adminPass",
    roles: [ { role: "userAdminAnyDatabase", db: "admin" } ]
  }
)

创建普通用户
use foo

db.createUser(
  {
    user: "simpleUser",
    pwd: "simplePass",
    roles: [ { role: "readWrite", db: "foo" },
             { role: "read", db: "bar" } ]
  }
)
