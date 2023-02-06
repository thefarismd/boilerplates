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
console.log("Server started on port 3000"); <br>
});
//
