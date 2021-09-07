# Java101-Patika Ödevleri

<a href='#Ödev 1'>ÖDEV 1: Not Ortalaması</a><br>
<a href='#Ödev 2'>ÖDEV 2: KDV Hesaplaması</a><br>
<a href='#Ödev 3'>ÖDEV 3: Üçgenin Hipotenüsü ve Alanı</a><br>
<a href='#Ödev 4'>ÖDEV 4: Taksimetre Programı</a><br>
<a href='#Ödev 5'>ÖDEV 5: Dairenin Alanını ve Çevresini Hesaplayan Program</a><br>
<a href='#Ödev 6'>ÖDEV 6: Vücut Kitle İndeksi</a><br>
<a href='#Ödev 7'>ÖDEV 7: Manav Kasa Programı</a><br>
<a href='#Ödev 8'>ÖDEV 8: Basit Hesap Makinesi</a><br>
<a href='#Ödev 9'>ÖDEV 9: Kullanıcı Girişi</a><br>
<a href='#Ödev 10'>ÖDEV 10: Sınıf Geçme Durumu</a><br>
<a href='#Ödev 11'>ÖDEV 11: Hava Sıcaklığına Göre Etkinlik Planlama</a><br>
<a href='#Ödev 12'>ÖDEV 12: Sayıları Küçükten Büyüğe Sıralama</a><br>
<a href='#Ödev 13'>ÖDEV 13: Burç Bulma Programı</a><br><br><br>

## <p id = 'Ödev 1' > ÖDEV 1 - Not Ortalaması </p>

### 1. Java ile Matematik, Fizik, Kimya, Türkçe, Tarih, Müzik derslerinin sınav puanlarını kullanıcıdan alan ve ortalamalarını hesaplayıp ekrana bastırılan programı yazın.

### -> Aynı program içerisinde koşullu ifadeler kullanılarak, eğer kullanıcının ortalaması 60'dan büyük ise ekrana "Sınıfı Geçti" , küçük ise "Sınıfta Kaldı" yazsın.

### <u> Not : If ve Else kullanılmayacak...

### :red_square: CEVAP

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

### :red_square: CEVAP

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

### :red_square: CEVAP

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

### :red_square: CEVAP

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

### :red_square: CEVAP

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

### :red_square: CEVAP

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

### :red_square: CEVAP

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

### :red_square: CEVAP

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

## <p id = 'Ödev 7' > ÖDEV 7 - Manav Kasa Programı </p>

### 1. Java ile kullanıcıların manavdan almış oldukları ürünlerin kilogram değerlerine göre toplam tutarını ekrana yazdıran programı yazın.

### -> Meyveler ve KG Fiyatları
### . Armut : 2,14 TL
### . Elma : 3,67 TL
### . Domates : 1,11 TL
### . Muz: 0,95 TL
### . Patlıcan : 5,00 TL

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        double armut;
        double elma;
        double domates;
        double muz;
        double patlican;

        Scanner scanner = new Scanner((System.in));

        System.out.print("Armut kaç kilo?: ");
        armut = scanner.nextDouble();

        System.out.print("Elma kaç kilo?: ");
        elma = scanner.nextDouble();

        System.out.print("Domates kaç kilo?: ");
        domates = scanner.nextDouble();

        System.out.print("Muz kaç kilo?: ");
        muz = scanner.nextDouble();

        System.out.print("Patlıcan kaç kilo?: ");
        patlican = scanner.nextDouble();

        double toplamTutar = (armut * 2.14) + (elma * 3.67) + (domates * 1.11) + (muz * 0.95) + (patlican * 5);

        System.out.println("Toplam tutar: " + toplamTutar);

    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 8' > ÖDEV 8 - Basit Hesap Makinesi </p>

### 1. Java ile kullanıcıların manavdan almış oldukları ürünlerin kilogram değerlerine göre toplam tutarını ekrana yazdıran programı yazın.

### -> Videodaki hesap makinesini switch-case kullanarak yapınız.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        int a,b,select;

        Scanner scanner = new Scanner(System.in);

        System.out.print("Birinci sayıyı girin: ");
        a = scanner.nextInt();

        System.out.print("İkinci sayıyı girin: ");
        b = scanner.nextInt();

        System.out.println("1- Topla\n2- Çıkar\n3- Çarp\n4- Böl");
        System.out.print("İşlem tipini seçin:");
        select = scanner.nextInt();

        switch (select){
            case 1:
                System.out.println("Sonuç: " + (a + b));
                break;
            case 2:
                System.out.println("Sonuç: " + (a - b));
                break;
            case 3:
                System.out.println("Sonuç: " + (a * b));
                break;
            case 4:
                if (b != 0) {
                    System.out.println("Sonuç: " + (a / b));
                    break;
                }else {
                    System.out.println("Bir sayı 0'a bölünemez!!!");
                    break;
                }
            default:
                System.out.println("Hatalı seçim yaptınız!");
        }

    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 9' > ÖDEV 9 - Kullanıcı Girişi </p>

### 1. Java koşullu ifadeler ile kullanıcı adı ve şifreyi kontrol eden program yapımı.

### -> Eğer şifre yanlış ise kullanıcıya şifresini sıfırlayıp sıfırlamayacağını sorun, eğer kullanıcı sıfırlamak isterse yeni girdiği şifrenin hatalı girdiği ve unuttuğu şifre ile aynı olmaması gerektiğini kontrol edip , şifreler aynı ise ekrana "Şifre oluşturulamadı, lütfen başka şifre giriniz." sorun yoksa "Şifre oluşturuldu" yazan programı yazınız.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        String userName, password;
        String changePassword;

        Scanner scanner = new Scanner(System.in);

        System.out.print("Kullanıcı adınızı girin: ");
        userName = scanner.nextLine();

        System.out.print("Şifrenizi girin: ");
        password = scanner.nextLine();

        if (userName.equals("patika") && password.equals("java123")){
            System.out.println("Giriş başarılı");
        }
        else{
            System.out.println("Kullanıcı adı ya da şifre hatalı.");
            System.out.println("Şifrenizi sıfırlamak ister misiniz? E/H");
            changePassword = scanner.nextLine();
                if (changePassword.equals("E")){
                    System.out.print("Lütfen yeni şifrenizi girin: ");
                    changePassword = scanner.nextLine();
                        if (changePassword.equals(password) || changePassword.equals("java123")){
                            System.out.println("Yeni şifreniz eski şifrenizden farklı olmalıdır!");
                        }else {
                            System.out.println("Şifreniz başarılı bir şekilde değiştirilmiştir.");
                        }
                }else if (changePassword.equals("H")){
                    System.out.println("Şifre değişikliği işlemi iptal edildi");
                }else {
                    System.out.println("Hatalı tuşlama yaptınız!");
                }
        }

    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 10' > ÖDEV 10 - Sınıf Geçme Durumu </p>

### 1. Java koşullu ifadeler ile kullanıcının not durumuna göre sınıfı geçme durumunu hesaplayan program yapımı.
### Dersler: Matematik, Fizik, Türkçe, Kimya, Müzik
### Geçme Notu: 55

### -> Eğer girilen ders notları 0 veya 100 arasında değil ise ortalamaya katılmasın.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        int mat, fiz, tur, kim, muz;
        int dersler = 5;

        Scanner scanner = new Scanner(System.in);

        System.out.print("Matematik notunuzu girin: ");
        mat = scanner.nextInt();

        System.out.print("Fizik notunuzu girin: ");
        fiz = scanner.nextInt();

        System.out.print("Türkçe notunuzu girin: ");
        tur = scanner.nextInt();

        System.out.print("Kimya notunuzu girin: ");
        kim = scanner.nextInt();

        System.out.print("Müzik notunuzu girin: ");
        muz = scanner.nextInt();

        if (mat<0 || mat>100){
            mat=0;
            dersler--;
        }
        if (fiz<0 || fiz>100){
            fiz=0;
            dersler--;
        }
        if (tur<0 || tur>100){
            tur=0;
            dersler--;
        }
        if (kim<0 || kim>100){
            kim=0;
            dersler--;
        }
        if (muz<0 || muz>100){
            muz=0;
            dersler--;
        }

        double avarage = (mat + fiz + tur + kim + muz) / dersler;

        if (avarage<55){
            System.out.println("Sınıfta kaldınız");

        }else {
            System.out.println("Tebrikler! Sınıfı geçtiniz");
        }

        System.out.println("Ortalamanız: " + avarage);

    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 11' > ÖDEV 11 - Hava Sıcaklığına Göre Etkinlik Planlama </p>

### 1. Java koşullu ifadeler ile hava sıcaklığına göre etkinlik öneren program yapımı.

### -> Koşullar :
### . Sıcaklık 5'dan küçük ise "Kayak" yapmayı öner.
### . Sıcaklık 5 ve 15 arasında ise "Sinema" etkinliğini öner.
### . Sıcaklık 15 ve 25 arasında ise "Piknik" etkinliğini öner.
### . Sıcaklık 25'ten büyük ise "Yüzme" etkinliğini öner.

### -> Aynı örnek üzerinden if koşulları başka hangi şekilde oluşturulabilirdi farklı çözüm yolları bulunuz.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        int temp;

        Scanner scanner = new Scanner(System.in);

        System.out.println("IF İLE YAPIM:");

        System.out.print("Hava sıcaklığını girin: ");
        temp = scanner.nextInt();

        if (temp<5){
            System.out.println("Kayak yapabilirsiniz");
        }else if (temp>=5 && temp<=25){
            if (temp<=15){
                System.out.println("Sinemaya gidebilirsiniz");
            }if (temp>=10){
                System.out.println("Pikniğe gidebilirsiniz");
            }
        }else{
            System.out.println("Yüzmeye gidebilirsiniz");
        }

        System.out.println("BOOLEAN İLE YAPIM:");

        System.out.print("Sıcaklık değerini girin: ");
        temp = scanner.nextInt();

        String alt;

        boolean kosul1 = temp<5;
        boolean kosul2 = temp>=5 && temp<10;
        boolean kosul3 = temp<=15;
        boolean kosul4 = temp>=15 && temp<=25;
        boolean kosul5 = temp>25;

        alt = kosul1 ? "Kayak yapabilirsin":
              kosul2 ? "Sinemaya gidebilirsin":
              kosul3 ? "Pikniğe gidebilirsin" + "\tSinemaya gidebilirsin":
              kosul4 ? "Pikniğe gidebilirsin":
                       "Yüzmeye gidebilirsin";

        System.out.println(alt);

    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 12' > ÖDEV 12 - Sayıları Küçükten Büyüğe Sıralama </p>

### 1. Java koşullu ifadeler ile girilen 3 sayıyı büyükten küçüğe sıralayan program yapımı.

### -> Girilen 3 sayıyı "küçükten büyüğe" sıralayan programı yazınız.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        int a,b,c;

        Scanner scanner = new Scanner(System.in);

        System.out.print("Birinci sayıyı girin: ");
        a = scanner.nextInt();

        System.out.print("İkinci sayıyı girin: ");
        b = scanner.nextInt();

        System.out.print("Üçüncü sayıyı girin: ");
        c = scanner.nextInt();

        System.out.println("SAYILARI BÜYÜKTEN KÜÇÜĞE SIRALAMA:");

        if ((a > b) && (a > c)){
            if (b > c){
                System.out.println("a > b > c");
            }else {
                System.out.println("a > c > b");
            }
        }else if ((b > a) && (b > c)){
            if (a > c){
                System.out.println("b > a > c");
            }else {
                System.out.println("b > c > a");
            }
        }else {
            if (a > b){
                System.out.println("c > a > b");
            }else {
                System.out.println("c > b > a");
            }
        }

        System.out.println("SAYILARI KÜÇÜKTEN BÜYÜĞE SIRALAMA:");

        if ((a < b) && (a < c)){
            if (b < c){
                System.out.println("a < b < c");
            }else {
                System.out.println("a < c < b");
            }
        }else if ((b < a) && (b < c)){
            if (a < c){
                System.out.println("b < a < c");
            }else {
                System.out.println("b < c < a");
            }
        }else {
            if (a < b){
                System.out.println("c < a < b");
            }else {
                System.out.println("c < b < a");
            }
        }

    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 13' > ÖDEV 13 - Burç Bulma Programı </p>

### 1. Java koşullu ifadeler ile kullanıcının burcunu bulan program yapımı.

### . Koç Burcu : 21 Mart - 20 Nisan
### . Boğa Burcu : 21 Nisan - 21 Mayıs
### . İkizler Burcu : 22 Mayıs - 22 Haziran
### . Yengeç Burcu : 23 Haziran - 22 Temmuz
### . Aslan Burcu : 23 Temmuz - 22 Ağustos
### . Başak Burcu : 23 Ağustos - 22 Eylül
### . Terazi Burcu : 23 Eylül - 22 Ekim
### . Akrep Burcu : 23 Ekim - 21 Kasım
### . Yay Burcu : 22 Kasım - 21 Aralık
### . Oğlak Burcu : 22 Aralık - 21 Ocak
### . Kova Burcu : 22 Ocak - 19 Şubat
### . Balık Burcu : 20 Şubat - 20 Mart

### -> Aynı örneği switch-case kullanmadan yapınız.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        int day,month;

        Scanner scanner = new Scanner(System.in);

        System.out.print("Doğduğunuz günü girin: ");
        day = scanner.nextInt();

        System.out.print("Doğduğunuz ayı girin: ");
        month = scanner.nextInt();

        System.out.println("SWITCH-CASE İLE YAPILIŞI:");

        switch (month){
            case 1:
                if (day >=1 && day <=31){
                    if (day <22){
                        System.out.println("Oğlak burcu");
                    }else {
                        System.out.println("Kova burcu");
                    }
                }else {
                    System.out.println("Geçersiz bir giriş yaptınız!");
                }
                break;
            case 2:
                if (day >=1 && day <=29){
                    if (day < 20){
                        System.out.println("Kova burcu");
                    }else {
                        System.out.println("Balık burcu");
                    }
                }else {
                    System.out.println("Geçersiz bir giriş yaptınız!");
                }
                break;
            case 3:
                if (day >=1 && day <=31){
                    if (day < 21){
                        System.out.println("Balık burcu");
                    }else {
                        System.out.println("Koç burcu");
                    }
                }else {
                    System.out.println("Geçersiz bir giriş yaptınız!");
                }
                break;
            case 4:
                if (day >=1 && day <=30){
                    if (day < 21){
                        System.out.println("Koç burcu");
                    }else {
                        System.out.println("Boğa burcu");
                    }
                }else {
                    System.out.println("Geçersiz bir giriş yaptınız!");
                }
                break;
            case 5:
                if (day >=1 && day <=31){
                    if (day < 22){
                        System.out.println("Boğa burcu");
                    }else {
                        System.out.println("İkizler burcu");
                    }
                }else {
                    System.out.println("Geçersiz bir giriş yaptınız!");
                }
                break;
            case 6:
                if (day >=1 && day <=30){
                    if (day < 23){
                        System.out.println("İkizler burcu");
                    }else {
                        System.out.println("Yengeç burcu");
                    }
                }else {
                    System.out.println("Geçersiz bir giriş yaptınız!");
                }
                break;
            case 7:
                if (day >=1 && day <31){
                    if (day < 23){
                        System.out.println("Yengeç burcu");
                    }else {
                        System.out.println("Aslan burcu");
                    }
                }else {
                    System.out.println("Geçersiz bir giriş yaptınız!");
                }
                break;
            case 8:
                if (day >=1 && day <=31){
                    if (day < 23){
                        System.out.println("Aslan burcu");
                    }else {
                        System.out.println("Başak burcu");
                    }
                }else {
                    System.out.println("Geçersiz bir giriş yaptınız!");
                }
                break;
            case 9:
                if (day >=1 && day <=30){
                    if (day < 23){
                        System.out.println("Başak burcu");
                    }else {
                        System.out.println("Terazi burcu");
                    }
                }else {
                    System.out.println("Geçersiz bir giriş yaptınız!");
                }
                break;
            case 10:
                if (day >=1 && day <=31){
                    if (day < 23){
                        System.out.println("Terazi burcu");
                    }else {
                        System.out.println("Akrep burcu");
                    }
                }else {
                    System.out.println("Geçersiz bir giriş yaptınız!");
                }
                break;
            case 11:
                if (day >=1 && day <=30){
                    if (day < 22){
                        System.out.println("Akrep burcu");
                    }else {
                        System.out.println("Yay burcu");
                    }
                }else {
                    System.out.println("Geçersiz bir giriş yaptınız!");
                }
                break;
            case 12:
                if (day >=1 && day <=31){
                    if (day < 22){
                        System.out.println("Yay burcu");
                    }else {
                        System.out.println("Oğlak burcu");
                    }
                }else {
                    System.out.println("Geçersiz bir giriş yaptınız!");
                }
                break;
        }

        System.out.println("IF İLE YAPILIŞI:");

        if (month == 1){
            if (day >= 1 && day <= 31){
                if (day < 22){
                    System.out.println("Oğlak burcu");
                }else {
                    System.out.println("Kova burcu");
                }
            }else {
                System.out.println("Geçersiz bir giriş yaptınız!");
            }
        }
        if (month == 2){
            if (day >= 1 && day <=29){
                if (day < 20){
                    System.out.println("Kova burcu");
                }else {
                    System.out.println("Balık burcu");
                }
            }else {
                System.out.println("Geçersiz bir giriş yaptınız!");
            }
        }
        if (month == 3){
            if (day >= 1 && day <= 31){
                if (day < 31){
                    System.out.println("Balık burcu");
                }else {
                    System.out.println("Koç burcu");
                }
            }else {
                System.out.println("Geçersiz bir giriş yaptınız!");
            }
        }
        if (month == 4){
            if (day >= 1 && day <= 30){
                if (day < 21){
                    System.out.println("Koç burcu");
                }else {
                    System.out.println("Boğa burcu");
                }
            }else {
                System.out.println("Geçersiz bir giriş yaptınız!");
            }
        }
        if (month == 5){
            if (day >= 1 && day <= 31){
                if (day < 22){
                    System.out.println("Boğa burcu");
                }else {
                    System.out.println("İkizler burcu");
                }
            }else {
                System.out.println("Geçersiz bir giriş yaptınız!");
            }
        }
        if (month == 6){
            if (day >= 1 && day <= 30){
                if (day < 23){
                    System.out.println("İkizler burcu");
                }else {
                    System.out.println("Yengeç burcu");
                }
            }else {
                System.out.println("Geçersiz bir giriş yaptınız!");
            }
        }
        if (month == 7){
            if (day >= 1 && day <= 31){
                if (day < 23){
                    System.out.println("Yengeç burcu");
                }else {
                    System.out.println("Aslan burcu");
                }
            }else {
                System.out.println("Geçersiz bir giriş yaptınız!");
            }
        }
        if (month == 8){
            if (day >= 1 && day <= 31){
                if (day < 23){
                    System.out.println("Aslan burcu");
                }else {
                    System.out.println("Başak burcu");
                }
            }else {
                System.out.println("Geçersiz bir giriş yaptınız!");
            }
        }
        if (month == 9){
            if (day >= 1 && day <= 30){
                if (day < 23){
                    System.out.println("Başak burcu");
                }else {
                    System.out.println("Terazi burcu");
                }
            }else {
                System.out.println("Geçersiz bir giriş yaptınız!");
            }
        }
        if (month == 10){
            if (day >= 1 && day <= 31){
                if (day < 23){
                    System.out.println("Terazi burcu");
                }else {
                    System.out.println("Akrep burcu");
                }
            }else {
                System.out.println("Geçersiz bir giriş yaptınız!");
            }
        }
        if (month == 11){
            if (day >= 1 && day <= 30){
                if (day < 22){
                    System.out.println("Akrep burcu");
                }else {
                    System.out.println("Yay burcu");
                }
            }else {
                System.out.println("Geçersiz bir giriş yaptınız!");
            }
        }
        if (month == 12){
            if (day >= 1 && day <= 31){
                if (day < 22){
                    System.out.println("Yay burcu");
                }else {
                    System.out.println("Oğlak burcu");
                }
            }else {
                System.out.println("Geçersiz bir giriş yaptınız!");
            }
        }

    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------