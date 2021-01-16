### Django Rest Framework

---

[toc]

#### 1. API Docs

---

##### 1.1 coreapi

---

![example picture](/home/rookie/Pictures/截图录屏_选择区域_20210107234153.png)

(1) settings

```django
REST_FRAMEWORK = {
    'DEFAULT_SCHEMA_CLASS': 'rest_framework.schemas.coreapi.AutoSchema',
}
```

(2) install

```sh
pip install coreapi pyyaml
```

(3) urls (根目录)

```django
from rest_framework.schemas import get_schema_view
from rest_framework.documentation import include_docs_urls

schema_view = get_schema_view(title='Pastebin API')

urlpatterns = [
    path('schema/', schema_view),
    path('docs/', include_docs_urls(title='My API title')),
]
```



#### 2. Models and Serializers

---

