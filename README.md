<h1>用LIFFPY建立LIFF網頁</h1>
<p>此文章為如何透過liffpy套件在LINEBOT上面新增LIFF網頁的範本，主要程式碼如下：</p>

```

from liffpy import (
    LineFrontendFramework as LIFF,
    ErrorResponse
)

liff_api = LIFF("你的Channel AcessToken")

try:
    now_LIFF_APP_number = len(liff_api.get())
except:
    now_LIFF_APP_number = 0

target_LIFF_APP_number = 10
print(target_LIFF_APP_number,now_LIFF_APP_number)
if now_LIFF_APP_number < target_LIFF_APP_number:
    for i in range(target_LIFF_APP_number - now_LIFF_APP_number):
        liff_api.add(view_type="full",view_url="https://www.google.com")


