# gulp-delete-file

### Usage
Initially, install `gulp-delete-file` as a development dependency:


```
npm install --save gulp-pre-combo
```
Then, create task using `gulp-pre-combo`, which might look similar as below:

```
'use strict';
var gulp = require('gulp'),
	precombo = require('gulp-pre-combo');
gulp.task('pre-combo', function () {
	var repoinfo = require('../../repo-info.json');
	gulp.src('src/**/*.html')
		.pipe(precombo(repoinfo))
		.pipe(gulp.dest('build'));
})

```

Finally, fire gulp task:

```
gulp pre-combo

```

### HTML

```
	<!DOCTYPE HTML>
	<html lang="en">
	<head>
	    <meta charset="utf-8">
	    <title>abc</title>
	    <link rel="stylesheet" type="text/css" href="./index.css">
	    <link rel="stylesheet" type="text/css" href="./index2.css">
	</head>
	<body>
		<!--content-->
	<script src="./index.js"></script>
	<script src="./index2.js"></script>
	</body>
	</html>
```

### OUTPUT

```
	<!DOCTYPE HTML>
	<html lang="en">
	<head>
	    <meta charset="utf-8">
	    <title>abc</title>
	    <link rel="stylesheet" type="GROUPNAME/REPONAME/VERSION/PATH/TO/FILE/index.min.CSS">
	    <link rel="stylesheet" type="text/css" href="GROUPNAME/REPONAME/VERSION/PATH/TO/FILE/index2.min.CSS">
	</head>
	<body>
		<!--content-->
	<script src="GROUPNAME/REPONAME/VERSION/PATH/TO/FILE/index.min.js"></script>
	<script src="GROUPNAME/REPONAME/VERSION/PATH/TO/FILE/index2.min.js"></script>
	</body>
	</html>
```

