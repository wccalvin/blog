---
title: "Making a blog using hugo"
date: 2018-10-26T05:02:24-04:00
draft: true
menu: "main"
weight: 1
---
# Creating a blog is fun and effortless with hugo

## Lesson 1: Getting Started

### Install
```
brew install hugo
```

### Create new site
```
hugo new site blog
cd blog/
```

### Create new content
```
hugo new _index.md
```

### Creat a basic index.html in the layouts
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Making a blog using hugo</title>
</head>
<body>
    {{ .Content }}
</body>
</html>
```

### Start the hugo server
```
hugo server -D
```

### Build hugo site
```
hugo -D
```
