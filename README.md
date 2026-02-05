In whatever file needs access to the database, include this:
const DATABASE = require('../utils/file_functions')

From there you have access to these:
DATABASE.getAllDAta()
DATABASE.getSingleItem(id)  
DATABASE.addData(data)  

//  id us common. A little tweeking with file_functions.js other values can be used as the key value
//  for finding a piece of data. A little cleverness and multiple key values could be used ass well.

//  It should also be fairly easy to customize whatever data checks you would like to.
//  The joi package is pretty cool for validating the data sent.

const schema = { name: Joi.string().min(3).required() }

if (joi.validate(data, schema) {
  //  run this code
}
