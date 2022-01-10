
<h1 align="center">
  <br>
  <a href="https://phish.azrael.gg?utm_src=Github"><img src="https://cdn.azrael.gg/uploads/branding/azrael_logo_primary.png" alt="Azrael" width="200"></a>
  <br>
  Azrael Anti-Phish
  <br>
</h1>

<h4 align="center">A powerful API system built to maintain a list of currently known phishing links.</h4>

  <a href="https://img.shields.io/maintenance/yes/2022">
    <img src="https://img.shields.io/maintenance/yes/2022">
  </a>
</p>

<p align="center">
  <a href="#key-features">Key Features</a> •
  <a href="#getting-started">Getting Started</a> •
  <a href="#how-to-use">How To Use</a> •
  <a href="#support">Support</a>
</p>

## Key Features

* Whitelist Only
  - Access to the API is only available via whitelisting, preventing the information from falling into the wrong hands
* Easy to Use
  - Our API automatically detects links in your request, no need to sort through the data to send just the link.
* 24/7 Support
  - We are here to help, reach out to our support team for assistance.

## Getting Started

To gain access to our API, you will need to join our [Discord](https://discord.gg/UZJcaVvnTa) server and reach out to our support team via the [Phisherman](https://discord.com/users/906697436553154680) and request access to the API.

If your request is approved, you will recieve a DM containing your API token.

## How To Use
### Required Headers
```
Authorization : Bearer Your Token Here
Content-Type : Supported: application/json and application/x-www-form-urlencoded
```
### Example Body
```
{ "data": "This message contains a link example.com but its not a phishing link" }
```

### Example Requests
#### Curl/Bash
```bash
#!/bin/bash

curl -X POST https://phish.azrael.gg/check -H "User-Agent: Azrael Interactive LLC (azrl.cc) / http 1.1" -H "Authorization: Bearer Your Token Here" -H "Content-Type: application/json" -d "{\"data\": \"example.com\"}"
```
#### Python
```python
import requests
from requests.structures import CaseInsensitiveDict

url = "https://phish.azrael.gg/check"

headers = CaseInsensitiveDict()
headers["User-Agent"] = "Azrael Interactive LLC (azrl.cc) / http 1.1"
headers["Authorization"] = "Bearer Your Token Here"
headers["Content-Type"] = "application/json"

data = '{"data": "example.com"}'


resp = requests.post(url, headers=headers, data=data)

print(resp.status_code)

```
#### JavaScript/AJAX
```javascript
var url = "https://phish.azrael.gg/check";

var xhr = new XMLHttpRequest();
xhr.open("POST", url);

xhr.setRequestHeader("User-Agent", "Azrael Interactive LLC (azrl.cc) / http 1.1");
xhr.setRequestHeader("Authorization", "Bearer Your Token Here");
xhr.setRequestHeader("Content-Type", "application/json");

xhr.onreadystatechange = function () {
   if (xhr.readyState === 4) {
      console.log(xhr.status);
      console.log(xhr.responseText);
   }};

var data = '{"data": "discord-nitroapp.ru.com example.com"}';

xhr.send(data);
```
#### C#/.NET
```csharp
var url = "https://phish.azrael.gg/check";

var httpRequest = (HttpWebRequest)WebRequest.Create(url);
httpRequest.Method = "POST";

httpRequest.Headers["User-Agent"] = "Azrael Interactive LLC (azrl.cc) / http 1.1";
httpRequest.Headers["Authorization"] = "Bearer Your Token Here";
httpRequest.ContentType = "application/json";

var data = "{\"data\": \" example.com\"}";

using (var streamWriter = new StreamWriter(httpRequest.GetRequestStream()))
{
   streamWriter.Write(data);
}

var httpResponse = (HttpWebResponse)httpRequest.GetResponse();
using (var streamReader = new StreamReader(httpResponse.GetResponseStream()))
{
   var result = streamReader.ReadToEnd();
}

Console.WriteLine(httpResponse.StatusCode);
```

### Response(s)
#### 400 Bad Request
```json
{
    "status": 400,
    "message": "Bad Request",
    "status_ext": {
        "1": "Additional Details"
    }
}
```
#### 401 Unauthorized
```json
{
    "status": 401,
    "message": "Unauthorized",
    "status_ext": {
        "1": "Additional Details"
    }
}
```
#### 403 Forbidden
```json
{
    "status": 403,
    "message": "Forbidden",
    "status_ext": {
        "1": "Additional Details"
    }
}
```
#### 200 OK (No Match)
```json
{
    "matched": false
}
```
#### 200 OK (Match Found)
```json
{
    {
    "matched": true,
    "phish": {
        "matches": 1,
        "links": ["example.com"]
    }
  }
}
```

## Support

<a href="https://discord.gg/UZJcaVvnTa" target="_blank"><img src="https://cdn.azrael.gg/assets/remote/img/market/azrael_join_us_banner.png" alt="Join Us"></a>

---

> [azrael.gg](https://azrael.gg) &nbsp;&middot;&nbsp;
> GitHub [@Azrael-Interactive](https://github.com/Azrael-Interactive) &nbsp;&middot;&nbsp;
> Twitter [@AzraelAPI](https://twitter.com/AzraelAPI) &nbsp;&middot;&nbsp;
> Instagram [@AzraelAPI](https://www.instagram.com/azraelapi/)

