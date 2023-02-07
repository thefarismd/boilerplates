# boilerplates
Storage for code boilerplates.

## Starting codes for nodeJS, expressJS, bodyParserJS, ejs, mongooseJS
```
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
```

## Connecting MongoDB-Moongoose
```
//---- MongoDB-Moongoose Connection DB, Schema & Model ----//
mongoose.set('strictQuery', false);
mongoose.connect('mongodb://127.0.0.1:27017/wikiDB');

const articleSchema = new mongoose.Schema({
    title: String,
    content: String
});

const Article = new mongoose.model('article', articleSchema); //
```

## Moongoose Snippets
```
Article.find({}, function (err, foundDocs) {
    if (!err) {
        res.send(foundDocs);
    } else {
        res.send(err);
    }
});

const newArticle = new Article ({
    title: req.body.title,
    content: req.body.content
});

newArticle.save(function(err){
    if(!err){
        res.send("Successful added a new article.");
    } else {
        res.send(err);
    };
});
```

## Get Route
```
//--- Get Route ----//
app.get("/articles", function (req, res) {

    //res.render("route", {contactContent: contactContent});
    //res.redirect(route);
    //res.send(String);
    
})//
```

## Post Route
```
//---- Post Route ----//
app.post("/articles", function (req, res) {

    //res.render("route", {contactContent: contactContent})
    //res.redirect(route)
    //res.send(String)
    
})//
```

## Chain Route Handlers Using Express
```
//---- Chain Route Handlers Using Express ----//
app.route("articles").get(callbackfunction).post(callbackfunction).delete(callbackfunction);
```
