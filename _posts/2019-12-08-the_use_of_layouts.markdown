---
layout: post
title:      "The Use of Layouts"
date:       2019-12-09 00:40:34 +0000
permalink:  the_use_of_layouts
---


Layouts provide a common look and feel between views of your application.  When you generate a new Rails app, a layout is automatically created by default within the `app/views` directory.  Within the `app/views/layouts` folder is a file created named `application.html.erb` which is where common components are added such as the header, body, footer, and navigation to make a complete view.

Yield is what Rails uses to decide where in the layout to render the content of the action view. If a yield is not placed in your layout, the layout itself will render fine, but any additional content coded within the action templates will not be correctly placed within the layout.

When a layout is rendered, it pulls the action's specific template into the correct place where the yield statement is added. For example:


```
<!-- app/views/layouts/application.html.erb -->
 
<!DOCTYPE html>
<html>
<head>
  <title>The Candy Store</title>
</head>
<body>
    <h1>Welcome To The Best Candy Store On Earth!</h1>
    <%= yield %>    
</body>
</html>
```

Luckily, Rails decides on which correct layout to be used for your request.  In the background, Rails will automatically search the controller and will see whether if there is a layout for that controller in its corresponding view. If it can't find a layout specific to your controller, it will use the default layout at `app/views/layouts/application.html.erb`. Most applications use the default layout for everything so there's really no need to have a layout for each controller unless the situation requires otherwise.
