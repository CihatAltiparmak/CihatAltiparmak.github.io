---
layout: default
---
# Default Layout

## Layout

_yay_

---
title: "json Modülü ve Kullanimi"
layout: post
ust: "yazılım"
---

Merhabalar, bu bölümde json modülünü şöyle bir inceleyeceğiz.

### Bir Karakter Dizisini Dict(Sözlük) ve List(Liste) ye Dönüştürmek

```python
import json

a = """
{
	"içecek" : "Ayran",
	"yemek" : "Kebab",
	"Garnitür": "Çoban salatası"
}
"""

print(type(a))

besinSozlugu = json.loads(a)
print(type(besinSozlugu))
for i in besinSozlugu:
    print(i, "--> ", besinSozlugu[i])

b = """
[
	"elma",
	"ayva",
	"kiraz"
]
""" 
print(type(b))
meyveListesi = json.loads(b)
print(type(meyveListesi))
for i in meyveListesi:
    print(i)
```
					

### Bir Dict(Sözlük) veya List(Liste) i String(Karakter Dizisi) e Dönüştürmek

```python
import json

a = {
	"içecek" : "Ayran",
	"yemek" : "Kebab",
	"Garnitür": "Çoban salatası"
}


print(type(a))

besinSozlugununStringHali = json.dumps(a)
print(type(besinSozlugununStringHali))
print(besinSozlugununStringHali)

b = [
	"elma",
	"ayva",
	"kiraz"
]
 
print(type(b))
meyveListesininStringHali = json.dumps(b)
print(type(meyveListesininStringHali))
print(meyveListesininStringHali)
```
					
					

### .json Uzantılı Dosyaları Kodlarımda Nasıl Kullanabilirim?

Önce deneme.json adlı bir dosya oluşturup bu dosyaya aşagıdakileri yazalım.

deneme.json

```python
{
	"içecek" : "Ayran",
	"yemek" : "Kebab",
	"Garnitür": "Çoban salatası"
}
```
					
					

Sonra aynı dizinde denemeJson.py adlı dosya oluşturup şunları yazalım.

denemeJson.py

```python
import json

with open("deneme.json") as f:
    alinanVeri = f.read()

eldeEdilenVeri = json.loads(alinanVeri)
for i in eldeEdilenVeri:
	print(i, "---> ", eldeEdilenVeri)
```
					

Gelin Alıştırma Olarak Girdiğiniz Verileri Kaydedip Gösteren Bir Fonksiyon Yazalım

```python
import json
import os

if not os.path.exists("settings.json"):
    with open("settings.json", "w") as f:
        print("settings.json dosyasını bulamadık.Bu yüzden yenisini oluşturuyorum.")
        f.write("{}")

with open("deneme.json") as f:
    alinan_veri = f.read()

def ayarlariEldeEt(veri):
    eldeEdilenVeri = json.loads(veri)
    return eldeEdilenVeri

def ayarlariDegistir(veri, ayarBolumu, yeniDeger):
    eldeEdilen = ayarlariEldeEt(veri)
    eldeEdilen[ayarBolumu] = yeniDeger
    with open("settings.json", "w") as f:
        kaydedilecekVeri = json.dumps(eldeEdilen)
        f.write(kaydedilecekVeri)
```		
					
Sonraki yazılarda görüşmek üzere ...


[back](../)
