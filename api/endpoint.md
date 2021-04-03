---
description: Daftar semua endpoint atau fitur yang tersedia dan bisa digunakan saat ini.
---

# Endpoint

{% api-method method="get" host="https://api.sdev.web.id" path="/language/detect" %}
{% api-method-summary %}
Deteksi Bahasa
{% endapi-method-summary %}

{% api-method-description %}
_Endpoint_ ini digunakan untuk mendeteksi bahasa dari suatu teks disertai dengan kepercayaannya.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="authorization" type="string" required=true %}
**Bearer &lt;APIKEY&gt;**  
  
Metode otentikasi yang kami gunakan adalah Bearer.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="text" type="string" required=true %}
Teks yang akan dideteksi bahasanya.
{% endapi-method-parameter %}

{% api-method-parameter name="result" type="integer" required=false %}
Jumlah hasil bahasa yang akan dikembalikan.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Tanggapan yang akan dikembalikan jika permintaan sukses.
{% endapi-method-response-example-description %}

```
{
    "status": 200,
    "data": {
        "text": "Selamat datang di SDev API",
        "detected": [
            {
                "language": "indonesian",
                "confidence": 0.44833333333333336
            },
            {
                "language": "tagalog",
                "confidence": 0.3588461538461538
            },
            {
                "language": "cebuano",
                "confidence": 0.25897435897435894
            },
            ...
        ]
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Tanggapan yang akan dikembalikan jika data yang harus dikirimkan tidak lengkap.
{% endapi-method-response-example-description %}

```
{
    "status": 400,
    "messages": "Incoming request body does not contain a valid data.",
    "data": null
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Tanggapan yang akan dikembalikan jika APIKEY tidak valid.
{% endapi-method-response-example-description %}

```
{
  "status": 401,
  "messages": "Unknown API Key. Please check your API key and try again.",
  "data": null
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
Tanggapan yang akan dikembalikan jika APIKEY yang digunakan sedang ditangguhkan.
{% endapi-method-response-example-description %}

```
{
  "status": 403,
  "messages": "Your account has been temporarily suspended.",
  "data": null
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=429 %}
{% api-method-response-example-description %}
Tanggapan yang akan dikembalikan jika APIKEY yang digunakan sudah melebihi batas penggunaan harian.
{% endapi-method-response-example-description %}

```
{
  "status": 429,
  "messages": "Request for your API Key has exceeded the usage limit.",
  "data": null
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Tanggapan yang akan dikembalikan jika terjadi kesalahan pada server kami. Harap segera hubungi administrator jika Anda mendapatkan tanggapan seperti berikut.
{% endapi-method-response-example-description %}

```
{
  "status": 500,
  "messages": "SDev API has encountered an unexpected error and cannot fulfill your request.",
  "data": null
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

