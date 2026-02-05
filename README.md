This is meant as a temporary database for developers who don't want to
bother with creating another database right away (mySql, mongoDB, etc).
The really cool thing about this is that by setting the CHANGE_DATABASE variable
to true causes the actuall data.json file to be changed. This works well when 
entering test data. Then, setting CHANGE_DATABASWE to false allows that data
to be refreshed every time the app is restarted.

In whatever file needs access to the database, include this:

      const DATABASE = require('../utils/file_functions')

From there you have access to these:

      DATABASE.getAllDAta()
      DATABASE.getSingleItem(id)  
      DATABASE.addData(data)  
      DATABASE.deleteItem(id)
      DATABASE.updateItem(id, data)

Using id as the key is common. A little tweeking with file_functions.js and other values can be used as the key value
for finding a piece of data. A little cleverness and multiple key values could be used ass well.

It should also be fairly easy to customize whatever data checks you would like to.
The joi package is pretty cool for validating the data sent.

const schema = { name: Joi.string().min(3).required() }

if (joi.validate(data, schema) {
  //  run this code
}
