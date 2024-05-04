# Global snippets 
	
Each snippet is defined under a snippet name:
  
* scope
* prefix
* body
* description. 
	
Add `comma` separated ids of the languages where the snippet is applicable in 
the scope field. 

If `scope` is left empty or omitted, the snippet gets applied to all languages. 

The `prefix` is what is used to trigger the snippet and the body will be 
expanded and inserted. 

Possible variables are: 

* `$1` for cursor location
* `$2` for tab stops
* `$0` for the final cursor position
* `${1:label}`, `${2:another}` for placeholders

Placeholders with the same ids are connected.

For more variables, visit the [VS Code User Guide](https://code.visualstudio.com/docs/editor/userdefinedsnippets#_variables)

Example:

```json
// json file config
"Print to console": {
    "scope": "javascript,typescript",
    "prefix": "log",
    "body": [
        "console.log('${1:label}');",
        "$2"	
    ],
    "description": "Log output to console"
}
```

```javascript
// javascript file code
console.log('label');

```
