# boilerplates
Storage for code boilerplates.

# Starting codes for nodeJS, expressJS, bodyParserJS, ejs, mongooseJS
<pre>
//jshint esversion:6

//---- Modules ----//
const express = require("express");
const bodyParser = require("body-parser");
const ejs = require("ejs");
const mongoose = require('mongoose');

const app = express();
app.set('view engine', 'ejs');

app.use(bodyParser.urlencoded({ extended: true }));
app.use(express.static("public")); //

//TODO

//---- Server Connection ----//
app.listen(3000, function () {
    console.log("Server started on port 3000");
}); //
</pre>

# MongoDB-Moongoose
<pre>
//---- MongoDB-Moongoose Connection DB, Schema & Model ----//
mongoose.set('strictQuery', false);
mongoose.connect('mongodb://127.0.0.1:27017/wikiDB');

const articleSchema = new mongoose.Schema({
    title: String,
    content: String
});

const Article = new mongoose.model('article', articleSchema); //
</pre>

# Get Route
<pre>
//--- Get Route ----//
app.get("/articles", function (req, res) {
    Article.find({}, function (err, foundDocs) {
        if (!err) {
            res.send(foundDocs);
        } else {
            res.send(err);
        }
    });
})//
</pre>

