# boilerplates
Storage for code boilerplates.

# Starting codes for nodeJS, expressJS, bodyParserJS, ejs, mongooseJS
//jshint esversion:6

//---- Modules ----// <br>
const express = require("express"); <br>
const bodyParser = require("body-parser"); <br>
const ejs = require("ejs"); <br>
const mongoose = require('mongoose'); <br>

const app = express(); <br>
app.set('view engine', 'ejs'); <br>

app.use(bodyParser.urlencoded({extended: true})); <br>
app.use(express.static("public")); <br>
//

//TODO

//---- Server Connection ----// <br>
app.listen(3000, function() { <br>
&nbsp;&nbsp;&nbsp;&nbsp;console.log("Server started on port 3000"); <br>
}); <br>
//

# MongoDB-Mongoose
//---- MongoDB-Moongoose Connection DB, Schema & Model ----//<br>
mongoose.connect('mongodb://127.0.0.1:27017/wikiDB');

const articleSchema = new mongoose.Schema({ <br>
&nbsp;&nbsp;&nbsp;&nbsp;title: String, <br>
&nbsp;&nbsp;&nbsp;&nbsp;content: String <br>
});

const Article = new mongoose.model('article', articleSchema); <br>
//
