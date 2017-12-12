# Tactile broker

Tactile Broker will render a json structure of well formatted pages and components, given a set of page and component implementations. Tactile Broker also enhances the json data structure with parent and child pointers among others. It uses mustache as a templating language.

## Usage

Access a property off of the current json object:
```mustache
{{someProperty}}
```

The path to the current json object:
```mustache
{{path}}
```

Access the parent json object:
```mustache
{{parent.path}}
```

Retrieve the current page:
```mustache
{{page.title}}
```

Retrieve the parent of the current page:
```mustache
{{page.parent.title}}
```

Access the home page:
```mustache
{{page.home.title}}
```

Access the children of the current page:
```mustache
{{#page.children}}
    <div>{{title}}</div>
{{/page.children}}
```

Access the siblings of the current page:
```mustache
{{#page.siblings}}
    <div>{{title}}</div>
{{/page.siblings}}
```

Access the children of the current pages parent page:
```mustache
{{#page.parent.children}}
    <div>{{title}}</div>
{{/page.parent.children}}
```

Access the home pages children:
```mustache
{{#page.home.children}}
    <div>{{title}}</div>
{{/page.home.children}}
```

Access the home pages siblings:
```mustache
{{#page.home.siblings}}
    <div>{{title}}</div>
{{/page.home.siblings}}
```

Render the "header" json object. This will be a child of the current json object.
It's compType will be used to determine how it will be rendered.
```mustache
{{render "header"}}
```

Render the current json object as the component type given in the second parameter. That is, render the current json object as a "footer".
```mustache
{{render false "footer"}}
```

Render the current object based upon the component type listed in the "compType" property.
```mustache
{{render false compType}}
```
