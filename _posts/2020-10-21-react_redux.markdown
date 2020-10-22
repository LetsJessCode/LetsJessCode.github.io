---
layout: post
title:      "React / Redux"
date:       2020-10-22 01:19:19 +0000
permalink:  react_redux
---


Okay so! This is my final project, and boy let me tell you it was not a walk in the park!

For my final project, I decided to build a date night application.

The user is able to view other date nights, create a date night idea, and leave a comment under someone else's date idea. The inspiration was pulled from various mom bloggers and being able to have one area where people can share their date night ideas for other couples!

As I was creating the project I knew that I wanted to be able to have the comments as well as the comment form to render under each individual date night idea, and while it seemed like an obvious way to build that out, I found myself completely stumped on how to have that properly built out! 

But then it was a lot more obvious than I realized...."duh! just import  your comment form and comment list within a div on your Date Idea Show Component!

```
import React, { Component } from 'react'
import { connect } from 'react-redux'
import CommentForm from '../../containers/comments/CommentForm'
import CommentShow from '../comments/CommentShow'
```

  That's great! Now at least the comments and form are able to display onto the page, but then it became an issue of....when I tried to create a new comment, the idea ID was not attached to the form, because the form that is showing on the page, was just that a blanket comment form. But! If I was able to pass in that Date ID into the form then the comment created would be attached to  the comment form when created! 

```jsx
 <CommentForm id={this.props.idea.id} />

```

After that, I simply passed that id, in to my comment's state so that it would be preset within my form..

```jsx
state = {
        name: "",
        comment: "",
        idea_id: this.props.id
    }
```

Passing in that ID though very simple was overlooked and preventing me the ability to create and display a comment that was attached to that specific date! React / Redux has so many ins and outs and while I am still learning and understanding! I am super proud of myself for getting through this project and ultimately completing my project!
