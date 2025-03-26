docker exec -it mongodb1 mongosh

rs.initiate({
  _id: "rs0",
  members: [
    { _id: 0, host: "mongodb1:27017" },
    { _id: 1, host: "mongodb2:27017" }
  ]
});

rs.status();

use('testdb')

db.customers.insertOne({ name: "Jane Doe2", email: "jane.doe@example.com" })

db.customers.find().pretty()