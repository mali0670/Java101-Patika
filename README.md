# Java101-Patika Ödevleri

<a href='#Ödev 1'>ÖDEV 1: Not Ortalaması</a><br>
<a href='#Ödev 2'>ÖDEV 2: KDV Hesaplaması</a><br>
<a href='#Ödev 3'>ÖDEV 3: Üçgenin Hipotenüsü ve Alanı</a><br>
<a href='#Ödev 4'>ÖDEV 4: Taksimetre Programı</a><br>
<a href='#Ödev 5'>ÖDEV 5: Dairenin Alanını ve Çevresini Hesaplayan Program</a>
<a href='#Ödev 6'>ÖDEV 6: Vücut Kitle İndeksi</a><br><br><br>

## <p id = 'Ödev 1' > ÖDEV 1 - Not Ortalaması </p>

### 1. Java ile Matematik, Fizik, Kimya, Türkçe, Tarih, Müzik derslerinin sınav puanlarını kullanıcıdan alan ve ortalamalarını hesaplayıp ekrana bastırılan programı yazın.

### -> Aynı program içerisinde koşullu ifadeler kullanılarak, eğer kullanıcının ortalaması 60'dan büyük ise ekrana "Sınıfı Geçti" , küçük ise "Sınıfta Kaldı" yazsın.

### <u> Not : If ve Else kullanılmayacak...

### :green_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner((System.in));

        System.out.print("Matematik notunuzu girin: ");
        int mat = scanner.nextInt();

        System.out.print("Fizik notunuzu girin: ");
        int fiz = scanner.nextInt();

        System.out.print("Kimya notunuzu girin: ");
        int kim = scanner.nextInt();

        System.out.print("Türkçe notunuzu girin: ");
        int tur = scanner.nextInt();

        System.out.print("Tarih notunuzu girin: ");
        int tar = scanner.nextInt();

        System.out.print("Müzik notunuzu girin: ");
        int muz = scanner.nextInt();

        int toplam = (mat + fiz + kim + tur + tar + muz);
        double ortalama = toplam / 6.0;
        System.out.println("Toplam notunuz: " + toplam + "\nOrtalamanız: " + ortalama);

        boolean durum = ortalama >= 60;
        System.out.println("Sınıfı geçme durumunuz: " + (durum == true ? "Geçti" : "Kaldı"));
    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 2' > ÖDEV 2 - KDV Hesaplaması </p>

### 1. Java ile kullanıcıdan alınan para değerinin KDV'li fiyatını ve KDV tutarını hesaplayıp ekrana bastıran programı yazın.

(Not : KDV tutarını 18% olarak alın)

KDV'siz Fiyat = 10;

KDV'li Fiyat = 11.8;

KDV tutarı = 1.8;

### -> Eğer girilen tutar 0 ve 1000 TL arasında ise KDV oranı %18 , tutar 1000 TL'den büyük ise KDV oranını %8 olarak KDV tutarı hesaplayan programı yazınız.

### :green_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner((System.in));

        double kdv1 = 0.18;
        double kdv2 = 0.08;

        System.out.print("Ürünün KDV'siz fiyatını girin:");
        double anapara = scanner.nextDouble();

        boolean kosul = anapara>=0 && anapara<=1000;

        double kdv = (kosul) ? kdv1 : kdv2;
        double kdvliFiyat = (anapara * kdv) + anapara;

        System.out.println("Ürünün KDV'siz fiyatı: " + anapara + " TL" + "\nKDV tutarı: " + kdv + " TL" +
                            "\nÜrünün KDV'li fiyatı: " + kdvliFiyat + " TL");

    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 3' > ÖDEV 3 - Üçgenin Hipotenüsü ve Alanı </p>

### 1. Java ile kullanıcıdan dik kenarlarının uzunluğunu alan ve hipotenüsü hesaplayan programı yazın.

### :green_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner((System.in));

        System.out.print("AB kenar uzunluğunu yazın: ");
        int kenar1 = scanner.nextInt();

        System.out.print("BC kenar uzunluğunu yazın: ");
        int kenar2 = scanner.nextInt();

        double hip = Math.sqrt((kenar1 * kenar1) + (kenar2 * kenar2));
        System.out.println("Hipotenüz uzunluğu: " + hip);

    }
}
```
</details>
<br>

### 2. Üç kenar uzunluğunu kullanıcıdan aldığınız üçgenin alanını hesaplayan programı yazınız.
### FORMÜL: Üç𝑔𝑒𝑛𝑖𝑛 ç𝑒𝑣𝑟𝑒𝑠𝑖 = 2𝑢
𝑢 = (a+b+c) / 2
Alan * Alan = 𝑢 * (𝑢 − 𝑎)* (𝑢 − 𝑏) * (𝑢 − 𝑐)

### :green_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner((System.in));

        System.out.print("AB kenar uzunluğunu yazın: ");
        int kenar1 = scanner.nextInt();

        System.out.print("BC kenar uzunluğunu yazın: ");
        int kenar2 = scanner.nextInt();

        System.out.print("AC kenar uzunluğunu yazın: ");
        int kenar3 = scanner.nextInt();

        double u = (kenar1 + kenar2 + kenar3)/2;
        double cevre = 2 * ((kenar1 + kenar2 + kenar3)/2);
        double alan = u * (u - kenar1) * (u - kenar2) * (u - kenar3);

        System.out.println("Üçgenin çevresi: " + cevre + "\nÜçgenin alanı: " + alan);

    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 4' > ÖDEV 4 - Taksimetre Programı </p>

### 1. Java ile gidilen mesafeye (KM) göre taksimetre tutarını ekrana yazdıran programı yazın.
### -> Taksimetre KM başına 2.20 TL tutmaktadır.
### -> Minimum ödenecek tutar 20 TL'dir. 20 TL altında ki ücretlerde yine 20 TL alınacaktır.
### -> Taksimetre açılış ücreti 10 TL'dir.

### :green_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        int km;
        double perKm = 2.20, startPrice = 10, total;
        Scanner scanner = new Scanner((System.in));

        System.out.print("Mesafeyi gidilen km cinsinden yazın: ");
        km=scanner.nextInt();

        total = (km * perKm);
        total += startPrice;

        boolean con = (total < 20);
        double check = (con) ? 20 : total;

        System.out.println("Toplam tutar: " + check);

    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 5' > ÖDEV 5 - Dairenin Alanını ve Çevresini Hesaplayan Program </p>

### 1. Java ile yarı çapını kullanıcıdan aldığınız dairenin alanını ve çevresini hesaplayan programı yazın.
### -> Alan Formülü : π * r * r;
### -> Çevre Formülü : 2 * π * r;

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner((System.in));

        float pi = 3.14f;

        System.out.print("Dairenin yarıçapını girin: ");
        int yariCap = scanner.nextInt();

        float cevre = 2 * pi * yariCap;
        float alan = pi * yariCap * yariCap;

        System.out.println("Dairenin çevresi: " + cevre + "\nDairenin alanı: " + alan);

    }
}
```
</details>
<br>

### 2. Yarıçapı r, merkez açısısının ölçüsü 𝛼 olan daire diliminin alanı bulan programı yazınız.
### -> 𝜋 sayısını = 3.14 alınız.
### -> Formül : (𝜋 * (r*r) * 𝛼) / 360

### :green_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner((System.in));

        float pi = 3.14f;

        System.out.print("Dairenin yarıçapını girin: ");
        int yariCap = scanner.nextInt();

        System.out.print("Merkez açısının ölçüsünü girin: ");
        int aci = scanner.nextInt();

        float dilim = (pi * (yariCap * yariCap) * aci) / 360;

        System.out.println("Daire diliminin alanı: " + dilim);

    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 6' > ÖDEV 6 - Vücut Kitle İndeksi </p>

### 1. Java ile kullanıcıdan boy ve kilo değerlerini alıp bir değişkene atayın. Aşağıda ki formüle göre kullanıcının "Vücut Kitle İndeks" değerini hesaplayıp ekrana yazdırın.
### -> FORMÜL: Kilo (kg) / Boy(m) * Boy(m)

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner((System.in));

        System.out.print("Lütfen boyunuzu (metre cinsinden) giriniz: ");
        double boy = scanner.nextDouble();

        System.out.print("Lütfen kilonuzu girin: ");
        int kilo = scanner.nextInt();

        double sonuc = kilo / (boy * boy);

        System.out.println("Vücut kitle endeksiniz: " + sonuc);

    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------