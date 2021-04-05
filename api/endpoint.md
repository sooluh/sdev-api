---
description: Daftar semua endpoint atau fitur yang tersedia dan bisa digunakan saat ini.
---

# Endpoint

{% api-method method="get" host="https://api.sdev.web.id" path="/language/detect" %}
{% api-method-summary %}
Deteksi Bahasa
{% endapi-method-summary %}

{% api-method-description %}
_Endpoint_ ini digunakan untuk mendeteksi bahasa dari suatu teks disertai dengan kepercayaan.
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
Teks yang akan di deteksi bahasanya.
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

```javascript
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

```javascript
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

```javascript
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

```javascript
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

```javascript
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

```javascript
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

{% api-method method="get" host="https://api.sdev.web.id" path="/language/translate" %}
{% api-method-summary %}
Terjemahan
{% endapi-method-summary %}

{% api-method-description %}
_Endpoint_ ini digunakan untuk menerjemahkan teks dari satu bahasa ke bahasa lainnya.
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
Teks yang akan di terjemahkan.
{% endapi-method-parameter %}

{% api-method-parameter name="from" type="string" required=false %}
Kode bahasa dari teks yang dikirimkan.  
Gunakan **auto** jika ingin menggunakan deteksi bahasa.
{% endapi-method-parameter %}

{% api-method-parameter name="to" type="string" required=true %}
Kode bahasa terjemahan yang di inginkan.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
Kode bahasa bisa kamu lihat pada halaman [Didukung](https://docs.sdev.web.id/api/supported#language).
{% endhint %}

{% api-method method="get" host="https://api.sdev.web.id" path="/drakor" %}
{% api-method-summary %}
Pencarian Drama Korea
{% endapi-method-summary %}

{% api-method-description %}
_Endpoint_ ini digunakan untuk mencari drama korea dan mendapatkan detail lengkap dari drama korea tersebut.
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
{% api-method-parameter name="keyword" type="string" required=true %}
Kata kunci drama korea yang ingin dicari.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.sddev.web.id" path="/gameid" %}
{% api-method-summary %}
Cek ID Game
{% endapi-method-summary %}

{% api-method-description %}
_Endpoint_ ini digunakan untuk mengecek nickname dan ketersediaan akun dari beberapa game online.
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
{% api-method-parameter name="game" type="integer" required=true %}
Kode game.
{% endapi-method-parameter %}

{% api-method-parameter name="id" type="string" required=true %}
ID game dari akun yang ingin dicek.  
Tidak dibutuhkan untuk game **Dragon Nest**.
{% endapi-method-parameter %}

{% api-method-parameter name="server" type="string" required=false %}
Dibutuhkan untuk game **Mobile Legends: Bang Bang**, **Ragnarok Mobile**, **Bleach Mobile 3D**, **Era of Celestials**, dan **Dragon Nest**.
{% endapi-method-parameter %}

{% api-method-parameter name="role" type="string" required=false %}
Dibutuhkan untuk game **Bleach Mobile 3D**, **Era of Celestials**, dan **Dragon Nest**.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Kode Server - Ragnarok Mobile

| Nilai | Nama Server |
| :--- | :--- |
| 1 | Eternal Love |
| 2 | Midnight Party |
| 3 | Memory of Faith |

{% api-method method="get" host="https://api.sdev.web.id" path="/onecak" %}
{% api-method-summary %}
Onecak Shuffle
{% endapi-method-summary %}

{% api-method-description %}
_Endpoint_ ini digunakan untuk mendapatkan meme secara acak dari situs 1cak.com
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="authorization" type="string" required=true %}
**Bearer &lt;APIKEY&gt;**  
  
Metode otentikasi yang kami gunakan adalah Bearer.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.sdev.web.id" path="/kodepos" %}
{% api-method-summary %}
Pencarian Kodepos
{% endapi-method-summary %}

{% api-method-description %}
_Endpoint_ ini digunakan untuk mencari kode pos \(Indonesia\) berdasarkan kata kunci, nama provinsi, nama kota, nama kabupaten, nama kecamatan, nama kelurahan, nama desa, maupun nama daerah.
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
{% api-method-parameter name="keyword" type="string" required=true %}
Kata kunci kode pos yang ingin dicari.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

