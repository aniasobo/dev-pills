# Rails `respond_to format.js` API

```
respond_to do |format|
  format.js # actually means: if the client ask for js -> return file.js
end
```

`.js` here specifies a mime-type that the controller method would send back as a response.

```
respond_to do |format|
  format.js
  format.yaml
end
```

that will mean that your controller will return `.yml` or `.js` depending on what the client-side is asking.

If you don't specify a block `{}` to pass in to `respond_to`, rails will try to render a default file from `app/views/[contoller name]/[controller method name].[html/js/...]`

With a block:

```
respond_to do |format|
  # that will mean to send a javascript code to client-side;
  format.js { render             
    # raw javascript to be executed on client-side
    "alert('Hello Rails');", 
    # send HTTP response code on header
    :status => 404, # page not found
    # load /app/views/your-controller/different_action.js.erb
    :action => "different_action",
    # send json file with @line_item variable as json
    :json => @line_item,
    :file => filename,
    :text => "OK",
    # the :location option to set the HTTP Location header
    :location => path_to_controller_method_url(argument)
  }

end
```

Sources:

* [API dock](https://apidock.com/rails/ActionController/MimeResponds/InstanceMethods/respond_to)
* [this Stack Overflow answer](https://stackoverflow.com/a/13545844)
