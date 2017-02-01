## API ONU #CPBR10 • The Big Hackathon

### Stack of development
- Raspbarry pi 2 or 3
- Distincts devices of Raspberry
- Linux Ubuntu/Debian distribution
- Golang >= 1.7.3
- Docker >= 1.2
- MongoDB >= 3.X.X
- Nginx

## DATA JSON
For consult on **endpoints paginate** `../page`. **POST** the JSON.
```json
{
    "date_end": "2017-01-27", 
    "date_order": "desc", 
    "date_start": "2017-01-27", 
    "page": 0, 
    "page_size": 25
}
```

## API Endpoints

#### Paginate all devices by endpoints per date
```
POST - http://api.bighacka.com/devices/all/page
```

#### Paginate data by endpoints
```
POST - http://api.bighacka.com/cpbr10/temperatura/page
POST - http://api.bighacka.com/cpbr10/uv/page
POST - http://api.bighacka.com/cpbr10/CO2/page
POST - http://api.bighacka.com/cpbr10/chuva/page
POST - http://api.bighacka.com/cpbr10/cxagua/page
POST - http://api.bighacka.com/cpbr10/humidade/page
POST - http://api.bighacka.com/cpbr10/lixo/page
POST - http://api.bighacka.com/cpbr10/movimento/page
POST - http://api.bighacka.com/cpbr10/painelsolar/page
POST - http://api.bighacka.com/cpbr10/ruido/page
POST - http://api.bighacka.com/cpbr10/co2/page
POST - http://api.bighacka.com/cpbr10/cxag0/page
POST - http://api.bighacka.com/cpbr10/ctude/page
POST - http://api.bighacka.com/cpbr10/latitude/page
POST - http://api.bighacka.com/cpbr10/longitude/page
```

#### Get data by ID
```
GET - http://api.bighacka.com/cpbr10/temperatura/:{id}
GET - http://api.bighacka.com/cpbr10/uv/:{id}
GET - http://api.bighacka.com/cpbr10/CO2/:{id}
GET - http://api.bighacka.com/cpbr10/chuva/:{id}
GET - http://api.bighacka.com/cpbr10/cxagua/:{id}
GET - http://api.bighacka.com/cpbr10/humidade/:{id}
GET - http://api.bighacka.com/cpbr10/lixo/:{id}
GET - http://api.bighacka.com/cpbr10/movimento/:{id}
GET - http://api.bighacka.com/cpbr10/painelsolar/:{id}
GET - http://api.bighacka.com/cpbr10/ruido/:{id}
GET - http://api.bighacka.com/cpbr10/co2/:{id}
GET - http://api.bighacka.com/cpbr10/cxag0/:{id}
GET - http://api.bighacka.com/cpbr10/ctude/:{id}
GET - http://api.bighacka.com/cpbr10/latitude/:{id}
GET - http://api.bighacka.com/cpbr10/longitude/:{id}
```

#### Last upate from device (realtime)
```
GET - http://api.bighacka.com/cpbr10/temperatura/latest
GET - http://api.bighacka.com/cpbr10/uv/latest
GET - http://api.bighacka.com/cpbr10/CO2/latest
GET - http://api.bighacka.com/cpbr10/chuva/latest
GET - http://api.bighacka.com/cpbr10/cxagua/latest
GET - http://api.bighacka.com/cpbr10/humidade/latest
GET - http://api.bighacka.com/cpbr10/lixo/latest
GET - http://api.bighacka.com/cpbr10/movimento/latest
GET - http://api.bighacka.com/cpbr10/painelsolar/latest
GET - http://api.bighacka.com/cpbr10/ruido/latest
GET - http://api.bighacka.com/cpbr10/co2/latest
GET - http://api.bighacka.com/cpbr10/cxag0/latest
GET - http://api.bighacka.com/cpbr10/ctude/latest
GET - http://api.bighacka.com/cpbr10/latitude/latest
GET - http://api.bighacka.com/cpbr10/longitude/latest
```

#### Last upate from all device (realtime)
```
GET - http://api.bighacka.com/cpbr10/all/latest
```

#### Last upate from all device (realtime)
```
GET - http://api.bighacka.com/cpbr10/all/latest
```

#### Last upate of wifitracker by day/hour
```
POST - http://api.bighacka.com/cpbr10/wifitracker
```
Use by wifitracker **POST**.
```json
{
    "date_end": "2017-01-27", 
    "date_start": "2017-01-27" 
}
```

#### Example consult POST data on wifitracker
In this sample we use a framework to wraper a curl execution, called [HTTPie](https://httpie.org/).
```sh
$ http --verbose post http://api.bighacka.com/cpbr10/wifitracker date_start=2017-02-01 date_end=2017-02-01
```
And we got that info after request.
```
POST /cpbr10/wifitracker HTTP/1.1
Accept: application/json, */*
Accept-Encoding: gzip, deflate
Connection: keep-alive
Content-Length: 54
Content-Type: application/json
Host: api.bighacka.com
User-Agent: HTTPie/0.9.6

{
    "date_end": "2017-02-01", 
    "date_start": "2017-02-01"
}

HTTP/1.1 200 OK
Connection: keep-alive
Content-Encoding: gzip
Content-Length: 315
Content-Type: application/json; charset=utf-8
Date: Wed, 01 Feb 2017 15:14:38 GMT
Server: nginx/1.1.19
Vary: Origin

{
    "results": [
        {
            "day": 1, 
            "facs": 35, 
            "hour": 0, 
            "macs": 735, 
            "month": 2, 
            "powers": 36, 
            "total": 1089, 
            "year": 2017
        }, 
        {
            "day": 1, 
            "facs": 41, 
            "hour": 1, 
            "macs": 896, 
            "month": 2, 
            "powers": 41, 
            "total": 1484, 
            "year": 2017
        }, 
        {...}
}
```

The MIT License (MIT)

Copyright (c) 2017 INVIRON

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
