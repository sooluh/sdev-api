---
description: Beberapa contoh request ke API di berbagai bahasa pemrograman.
---

# Contoh Request

## Request

{% tabs %}
{% tab title="Shell" %}
```text
curl --request GET \
  --url 'https://api.sdev.web.id/gameid/?game=1&id=2727579916' \
  --header 'authorization: Bearer <APIKEY>'
```
{% endtab %}

{% tab title="PHP" %}
```text
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.sdev.web.id/gameid/?game=1&id=2727579916",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "authorization: Bearer <APIKEY>"
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```
{% endtab %}

{% tab title="Ruby" %}
```text
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://api.sdev.web.id/gameid/?game=1&id=2727579916")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["authorization"] = 'Bearer <APIKEY>'

response = http.request(request)
puts response.read_body
```
{% endtab %}

{% tab title="Python" %}
```text
import http.client

conn = http.client.HTTPSConnection("api.sdev.web.id")

headers = { 'authorization': "Bearer <APIKEY>" }

conn.request("GET", "/gameid/?game=1&id=2727579916", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```
{% endtab %}

{% tab title="Go" %}
```text
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.sdev.web.id/gameid/?game=1&id=2727579916"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("authorization", "Bearer <APIKEY>")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
{% endtab %}

{% tab title="Node.js" %}
```text
var request = require("request");

var options = {
  method: 'GET',
  url: 'https://api.sdev.web.id/gameid/',
  qs: {game: '1', id: '2727579916'},
  headers: {authorization: 'Bearer <APIKEY>'}
};

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```
{% endtab %}

{% tab title="Java" %}
```text
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api.sdev.web.id/gameid/?game=1&id=2727579916")
  .get()
  .addHeader("authorization", "Bearer <APIKEY>")
  .build();

Response response = client.newCall(request).execute();
```
{% endtab %}

{% tab title="C\#" %}
```text
var client = new RestClient("https://api.sdev.web.id/gameid/?game=1&id=2727579916");
var request = new RestRequest(Method.GET);
request.AddHeader("authorization", "Bearer <APIKEY>");
IRestResponse response = client.Execute(request);
```
{% endtab %}
{% endtabs %}

## Response

