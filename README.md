# clingojs
========

A wrapper module for the Clingo program.

## Basic Usage
==============

```javascript
var Clingo = require('clingo');

var clingo = new Clingo();

clingo.config({ // Sets the basic configuration for this clingo instance
	maxModels: 0 // Return all models
});

clingo.solve({
	inputFiles: ['/path/to/some/file']
})
	.on('model', function(model) {
		// Here 'model' is an Array of strings representing the atoms of the model
		// e.g. ['example(0)', 'example(1)']
	})
	.on('end', function() {
		// This function gets called after all models have been received
	});
```