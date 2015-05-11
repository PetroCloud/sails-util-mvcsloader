# sails-hook-hookloader
Load the models, controllers, services from your Sails hooks into the main app

EXPERIMENTAL 

### USAGE
 Install it in your sails folder 
 
 ```
 npm install sails-hook-hookloader
 ```
 
 Then use it like this in your hook's index.js :
  
```
module.exports = function(sails) {
    return {    
      initialize: function(cb) {
        var hookLoader = require('sails-hook-hookloader')(sails);
        hookLoader.injectAll({
          controllers: __dirname+'/controllers', // Path to your hook's controllers
          models: __dirname+'/models', // Path to your hook's models
          services: __dirname+'/services' // Path to your hook's models
        }, function(err) {
          return cb();
        });
      }
    }
 }
```
### TODO

- Add support for loading :
    - Views