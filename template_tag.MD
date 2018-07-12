With template tags you can make custom filters to you variables in template

Path: app/templatetags/string_templatetag.py

Django Docs: https://docs.djangoproject.com/pt-br/2.0/howto/custom-template-tags/

```python
from django import template

register = template.Library()

def remove_spaces(string):    
    return string.replace(string, ' ', '')
    
def remove_selected_char(string, char):    
    return string.replace(string, char, '')
```  
  
```html 
{% load string_templatetag %}

{{ "I have alot of spaces"|remove_spaces }}
{{ "@I fe@el d@ir@t@y"|remove_selected_char:"@" }}
```
