# Temel GNU/Linux Komutları

## cd komutu

Bulunulan dizini değiştirmek için kullanılır.

```text
$ cd ./klasörüm
```

## pwd komutu

Hangi dizinde bulunduğumuzu gösterir.

```text
$ pwd
/home/kaanksc/Desktop
```

## cat komutu

Bir dosyanın içeriğini görmek için kullanılır.

```text
$ cat dosya.txt
Merhaba Dünya
```

## ls komutu

Bulunulan dizindeki içeriği görmek için kullanılır.

```text
$ ls
deneme.txt  örnek.txt
```

Gizli Dosyaları görmek için `ls -a` kullanabilirsiniz.

## mv komutu

Dosya ve klasörleri taşımak ve yeniden isimlerdirmek için kullanılır.

### Taşıma örneği

```text
mv ./kaan.txt /home/kaanksc/Documents/
```

Yukarıda kaan.txt dosyasını /home/kaanksc/Documents/ klasörüne taşıdık.

### Yeniden İsimlendirme Örneği

```text
mv deneme.txt deneme2.txt
```

## cp komutu

Dizin ve dosyaları kopyalamak için kullanılır.

```text
cp deneme.txt /home/kaanksc/Documents
```

Yukarıda `deneme.txt` dosyasını `/home/kaanksc/Documents` dizinine kopyalamış olduk.

## touch komutu

Boş dosya oluşturmak için kullanılır.

```text
touch kaan.txt
```

`kaan` isminde bir `txt` dosyası oluşturduk.

## mkdir komutu

Dizin oluşturmak için kullanılır.

```text
mkdir klasörüm
```

## rm komutu

Dosya ve dizini silmek için kullanılır. Kullanırken dikkatli olmanızı öneririm.

### Dosya Silme

```text
rm dosya.txt
```

### Dizin Silme

```text
rmdir klasör
```

### İçinde Dosya Olan Bir Dizini Silme

```text
rm -rf klasör
```

## grep komutu

Belirli bir dosya içerisindeki metinde arama yapar.

```text
grep "merhaba" örnek.txt
```

## kill komutu

Bir işlemi sonlandırmak için kullanılır. İş veya İşlem numarı olmalıdır.

```text
kill 1126528
```

## man komutu

Terminal komutlarının yardım sayfalarına ulaşabilirsiniz.

```text
man ls
```

Detaylı bir şekilde ls komutunun kullanımını anlatır.

Temelde kullanacağımız komutlar bu şekildedir. Daha fazla komut bulmak için arama motorlarında `Linux komutları` olarak aratabilirsiniz.

