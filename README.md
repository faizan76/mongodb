# mongodb
MongoDb Notes
yay -S mongodb-bin
//if any Error installing do...
gpg --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 --recv 27EDEAF22F3ABCEB50DB9A125CC908FDB71E12C2
sudo pacman -Syy
yay -S mongodb-bin
//After installing the package. Start/Enable the mongodb.service daemon.
systemctl enable --now mongodb
systemctl start --now mongodb
Test it:
mongo

//Create Default Database directory for our Mongodb Files.
sudo mkdir -p /data/db
//Recheck directory permissions
sudo chown -R `id -un` /data/db

//start mongo demon
mongod
//run mongo shell
mongo

//Create new db
use my-blog

//Create Collection and insert Documents(json Objects)
db.articles.insert([
{
name: 'd1'
},{
name: 'd2'
},{
name: 'd3'
}
])

//See Docs in collection
db.articles.find({})
//also
db.articles.find({}).pretty()
//drop a collection
db.articles.drop()

//find specific docs
db.articles.find({name: 'd2'})

//findOne
db.articles.findOne({name:'learn-node'})
