---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - php
  - python
  - javascript

<!-- toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a> -->

includes:
  - errors

search: true

code_clipboard: true
---

# Giriş

Bu API belgesinde Mynet-Chartbeat API'ının detaylarına yer verilmiştir. API'a ait uçnokta(lar), CPM dağılımlarını, ilgili haberlerin klik davranışlarını ve bulundukları pozisyonlar için kaçıncı yüzdelik dilim içerisinde olduğu bilgilerini içermektedir. 

Sağ taraftaki koyu renkli bölgede kod örneklerini bulabilirsiniz. Birden fazla programlama dilinde kod örneği verilmiş ise, istediğiniz programlama dilindeki örneğe geçiş yapabilirsiniz.


# Authentication

API'ya istek yapabilmek için, HTTP Header'ları içerisine özel bir key:value ikilisi eklemelisiniz. Bu ikilide key: 'Authorization' ve value:'mynetcb-api-user-aD7yH5' olmalıdır. 

```shell
# Örneğin shell üzerinden bir request yaparken, Authorization Header'ını şu şekilde gönderebilirsiniz:
curl "https://URL" \
  -H "Authorization: mynetcb-api-user-aD7yH5"
```



# /api

## CPM Dağılımı ve Yüzdelik Dilim Bilgisi

Bu versiyonda uygulama tek uçnokta üzerinden tüm veriyi tek seferde sunabilmektedir. /api uçnoktasına çeşitli programlama dilleri ve kütüphanelerle istek yapılabilir. Örnek kodlar yan taraftadır. 

```python
import requests

URL = "https://mynetcb.com/api"

headers = {
    ...
    'Authorization': 'mynetcb-api-user-aD7yH5',
    ...
}

response = requests.get(URL, headers=headers)
```


```shell
# With shell, you can just pass the correct header with each request
curl "https://mynetcb.com/api" \
  -H "mynetcb-api-user-aD7yH5"
```

```php

include('vendor/rmccue/requests/library/Requests.php');
Requests::register_autoloader();

$url = "https://mynetcb.com/api";

$headers = array(
    ...
    'Authorization' => 'mynetcb-api-user-aD7yH5',
    ...
);
$response = Requests::get($url, $headers);

```

```javascript
/*/
/*/ nodejs-fetch
/*/
var fetch = require('node-fetch');

var url = 'https://mynetcb.com/api';



fetch(url, {
    headers: {
        ...
        'Authorization': 'mynetcb-api-user-aD7yH5',
        ...
    }
});

```

```javascript
/*/
/*/ nodejs-request
/*/
var request = require('request');

var headers = {
    ...
    'Authorization': 'mynetcb-api-user-aD7yH5',
    ...
};

var options = {
    url: 'https://mynetcb.com/api',
    headers: headers
};

function callback(error, response, body) {
    if (!error && response.statusCode == 200) {
        console.log(body);
    }
}

request(options, callback);

```


> Yukarıdaki request, aşağıdaki gibi bir JSON objesi dönmektedir: 

```json
{
  "links": [
    {
      "href": "https://www.mynet.com/video",
      "cpm_distribution": null,
      "clicks": 0,
      "percentile": null
    },
    {
      "href": "https://www.mynet.com/izmir-den-kahreden-haber-30-saat-sonra-enkazdan-cikarilan-kisinin-oldugu-belirlendi-110106634879",
      "cpm_distribution": [
        2.5537455,
        3.712115,
        4.3025595,
        4.7143155,
        5.0615945,
        5.332733,
        5.545604,
        5.782559,
        5.971346,
        6.2183995,
        6.451467,
        6.690745,
        6.9339105,
        7.1910625,
        7.5305655,
        8.0145745,
        8.876965,
        9.961567,
        11.729063
      ],
      "clicks": 6.2525465741,
      "percentile": 53
    },
    {
      "href": "https://www.mynet.com/muge-anli-izmir-deki-depremzedeler-icin-mobil-asevi-gonderdi-303575-mymagazin",
      "cpm_distribution": [
        1.9912775,
        2.626986,
        3.119844,
        3.5861165,
        3.999218,
        4.3758115,
        4.72582,
        5.0393195,
        5.3163115,
        5.5536135,
        5.7413035,
        5.9289925,
        6.153191,
        6.4123055,
        6.689674,
        7.024987,
        7.467856,
        8.066679,
        8.9262085
      ],
      "clicks": 3.9695597904,
      "percentile": 21
    },
    ...
    
  ]
}
```



### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Bu uçnokta, bu versiyonda herhangi bir query string parametresi gerektirmemektedir. 

<aside class="success">
Hatırlatma - Authorization Header'ı gönderilmelidir. 
</aside>

