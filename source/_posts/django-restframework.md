---
title: django-restframework
date: 2018-03-09 14:07:56
tags: framework
categories: Python
---
### 设置认证方案
* 使用该DEFAULT_AUTHENTICATION_CLASSES设置可以全局设置默认的认证方案。例如

```
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': (
        'rest_framework.authentication.BasicAuthentication',
        'rest_framework.authentication.SessionAuthentication',
    )
}

```

* 还可以使用APIView基于类的视图，在每个视图或每个视图集的基础上设置身份验证方案

```
from rest_framework.authentication import SessionAuthentication, BasicAuthentication
from rest_framework.permissions import IsAuthenticated
from rest_framework.response import Response
from rest_framework.views import APIView

class ExampleView(APIView):
    authentication_classes = (SessionAuthentication, BasicAuthentication)
    permission_classes = (IsAuthenticated,)

    def get(self, request, format=None):
        content = {
            'user': unicode(request.user),  # django.contrib.auth.User instance.
            'auth': unicode(request.auth),  # None
        }
        return Response(content)
        
```
