# Python Sync To Async Decorator
# Example:
```
from time import sleep
from sync_to_async.sync_to_async import sync_to_async

from asgiref.sync import async_to_sync as async_api
from django.http import HttpResponse


@sync_to_async()
def time_consuming_function(t):
    sleep(t)


@async_api
async def start_task(request, t):
    await time_consuming_function(t)
    return HttpResponse('ok')

```
