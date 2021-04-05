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
Teks yang harus di deteksi bahasanya.
{% endapi-method-parameter %}

{% api-method-parameter name="result" type="integer" required=false %}
Jumlah hasil bahasa yang harus dikembalikan.
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
Teks yang harus di terjemahkan.
{% endapi-method-parameter %}

{% api-method-parameter name="from" type="string" required=false %}
Kode bahasa dari teks yang harus diterjemahkan.  
Gunakan **auto** jika ingin menggunakan deteksi bahasa.
{% endapi-method-parameter %}

{% api-method-parameter name="to" type="string" required=true %}
Kode bahasa yang akan menjadi terjemahannya.
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
Kata kunci drama korea yang harus dicari.
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
Kode game yang harus dicek.
{% endapi-method-parameter %}

{% api-method-parameter name="id" type="string" required=true %}
ID game dari akun yang harus dicek.  
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
_Endpoint_ ini digunakan untuk mencari kode pos \(Indonesia\) berdasarkan nama daerah, nama kota, maupun nama kelurahan.
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
Kata kunci kode pos yang harus dicari.
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

{% api-method method="get" host="https://api.sdev.web.id" path="/provider" %}
{% api-method-summary %}
Deteksi Provider
{% endapi-method-summary %}

{% api-method-description %}
_Endpoint_ ini digunakan untuk mendeteksi provider kartu perdana berdasarkan nomor telepon.
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
{% api-method-parameter name="number" type="number" required=true %}
**628xxxxxxxxxx**  
  
Nomor telepon yang harus di deteksi nama provider nya.
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

{% api-method method="get" host="https://api.sdev.web.id" path="/covidarea" %}
{% api-method-summary %}
Cek Area COVID-19
{% endapi-method-summary %}

{% api-method-description %}
_Endpoint_ ini digunakan untuk mengecek zona terdampak COVID-19 berdasarkan latitude dan longitude.
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
{% api-method-parameter name="latitude" type="string" required=true %}
Koordinat garis lintang.
{% endapi-method-parameter %}

{% api-method-parameter name="longitude" type="string" required=true %}
Koordinat garis bujur.
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

{% api-method method="get" host="https://api.sdev.web.id" path="/subfinder" %}
{% api-method-summary %}
Pencarian Subdomain
{% endapi-method-summary %}

{% api-method-description %}
_Endpoint_ ini digunakan untuk mencari subdomain yang tersedia dari domain utama.
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
{% api-method-parameter name="domain" type="string" required=true %}
Domain yang harus dicari subdomain nya.
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

{% api-method method="get" host="https://api.sdev.web.id" path="/wikipedia" %}
{% api-method-summary %}
Wikipedia
{% endapi-method-summary %}

{% api-method-description %}
_Endpoint_ ini digunakan untuk mencari dan mendapatkan informasi lengkap berdasarkan kata kunci dari situs wikipedia.
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
Kata kunci yang harus dicari.
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

{% api-method method="get" host="https://api.sdev.web.id" path="/sslchecker" %}
{% api-method-summary %}
Cek Validasi SSL
{% endapi-method-summary %}

{% api-method-description %}
_Endpoint_ ini digunakan untuk mengecek detail validasi SSL berdasarkan nama domain atau _hostname_.
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
{% api-method-parameter name="domain" type="string" required=true %}
Domain yang harus dicek detail SSL nya.
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

{% api-method method="get" host="https://api.sdev.web.id" path="/linkpreview" %}
{% api-method-summary %}
Pratinjau Tautan
{% endapi-method-summary %}

{% api-method-description %}
_Endpoint_ ini digunakan untuk mendapatkan detail umum dari sebuah tautan.
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
{% api-method-parameter name="url" type="string" required=true %}
Tautan yang harus didapatkan detail nya.
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

{% api-method method="get" host="https://api.sdev.web.id" path="/jadwalsholat" %}
{% api-method-summary %}
Jadwal Sholat
{% endapi-method-summary %}

{% api-method-description %}
_Endpoint_ ini digunakan untuk mendapatkan jadwal ibadah umat muslim berdasarkan kota, tahun serta bulan.
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
{% api-method-parameter name="city" type="string" required=true %}
Nama kota.
{% endapi-method-parameter %}

{% api-method-parameter name="year" type="string" required=true %}
Tahun.
{% endapi-method-parameter %}

{% api-method-parameter name="month" type="string" required=true %}
Bulan.
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

{% hint style="info" %}
Nama kota bisa kamu lihat pada halaman [Didukung](https://docs.sdev.web.id/api/supported#cities).
{% endhint %}

