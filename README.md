# test4

sudo yum update
sudo yum install git
git clone URL

------for docker-----
sudo yum install docker
sudo systemctl status docker
sudo systemctl start docker
sudo systemctl enable docker
sudo docker image
ls
sudo docker build -t practice .
sodo docker run -d -p 8081:8081 practice
sudo docker ps
-----------------------------------------------------------------
******************docker*************************************************

FROM node:7
WORKDIR /app
COPY package.json /app
RUN npm install
COPY . /app
CMD node server.js
EXPOSE 8081

*****************experss****************************************

var express = require('express');
var app = express();
var path=require("path");
var fs=require("fs");


//server configuration
app.use(express.static(path.join(__dirname,'public')));

 app.get('/', function (req, res) {
   res.sendFile(path.join(___dirname + '/index.html'));
});
 

app.get('/hello', function (req, res) {
  console.log("CAlling rest api");
  var person={firstName:'Ravi',lastName:'Tambade',age:43};
  res.send(person);
});

 
var server = app.listen(8081, function () {

  var host = server.address().address
  var port = server.address().port

  console.log("Example app listening at http://localhost:8081", host, port)
})