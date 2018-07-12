Creating context processors in django

settings.py

```python
TEMPLATES = [{
    'BACKEND': 'django.template.backends.django.DjangoTemplates',        
    'DIRS': [],
    'APP_DIRS': True,
    'OPTIONS': {
        'context_processors': [                
            ...
            'youapp.context_processors.yourcontextname_context_processor',
        ],
    },
}]
```

Create one file called context_processors.py in your app folder

context_processors.py 

```python
def yourcontextname_context_processor(request):
    ... # Your logic        
    data = {
        'something': "something",
        'another_thing': "another_thing",
        'array_of_thing': ["thing", "thing", "thing", ],
    }
    return data
```

In your template the variables can be accesed

```html
{{ something }}
{{ another_thing }}
{% for thing in array_of_thing %}
    {{ thing }}
{% endfor %}
```
