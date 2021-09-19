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
<a href='#Ödev 13'>ÖDEV 13: Burç Bulma Programı</a><br>
<a href='#Ödev 14'>ÖDEV 14: Uçak Bilet Fiyatı Hesaplama</a><br>
<a href='#Ödev 15'>ÖDEV 15: Çin Zodyağı Hesaplama</a><br>
<a href='#Ödev 16'>ÖDEV 16: Artık Yıl Hesaplama</a><br>
<a href='#Ödev 17'>ÖDEV 17: Girilen Sayıya Kadar Çift Sayıları Bulma</a><br>
<a href='#Ödev 18'>ÖDEV 18: Tek Sayıların Toplamını Bulan Program</a><br>
<a href='#Ödev 19'>ÖDEV 19: Girilen Sayının Kuvvetlerini Bulma</a><br>
<a href='#Ödev 20'>ÖDEV 20: Faktoriyel Hesaplama</a><br>
<a href='#Ödev 21'>ÖDEV 21: Üslü Sayı Hesaplama</a><br>
<a href='#Ödev 22'>ÖDEV 22: Armstrong Sayısı Bulma</a><br>
<a href='#Ödev 23'>ÖDEV 23: Harmonik Seri Bulma</a><br>
<a href='#Ödev 24'>ÖDEV 24: Yıldız İle Üçgen Yapımı</a><br>
<a href='#Ödev 25'>ÖDEV 25: ATM Projesi</a><br>
<a href='#Ödev 26'>ÖDEV 26: EBOB - EKOK Bulma</a><br>
<a href='#Ödev 27'>ÖDEV 27: Girilen Sayıdan Min ve Max Değeri Bulma</a><br>
<a href='#Ödev 28'>ÖDEV 28: Mükemmel Sayı Bulma</a><br>
<a href='#Ödev 29'>ÖDEV 29: Yıldızlar ile Ters Üçgen Yapımı</a><br><br><br>

## <p id = 'Ödev 1' > ÖDEV 1 - Not Ortalaması </p>

1. Java ile Matematik, Fizik, Kimya, Türkçe, Tarih, Müzik derslerinin sınav puanlarını kullanıcıdan alan ve ortalamalarını hesaplayıp ekrana bastırılan programı yazın.

    -> Aynı program içerisinde koşullu ifadeler kullanılarak, eğer kullanıcının ortalaması 60'dan büyük ise ekrana "Sınıfı Geçti" , küçük ise "Sınıfta Kaldı" yazsın.

Not : If ve Else kullanılmayacak...

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

1. Java ile kullanıcıdan alınan para değerinin KDV'li fiyatını ve KDV tutarını hesaplayıp ekrana bastıran programı yazın.

(Not : KDV tutarını 18% olarak alın)

- KDV'siz Fiyat = 10;
- KDV'li Fiyat = 11.8;
- KDV tutarı = 1.8;

    -> Eğer girilen tutar 0 ve 1000 TL arasında ise KDV oranı %18 , tutar 1000 TL'den büyük ise KDV oranını %8 olarak KDV tutarı hesaplayan programı yazınız.

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

1. Java ile kullanıcıdan dik kenarlarının uzunluğunu alan ve hipotenüsü hesaplayan programı yazın.

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

2. Üç kenar uzunluğunu kullanıcıdan aldığınız üçgenin alanını hesaplayan programı yazınız.

- FORMÜL: Üç𝑔𝑒𝑛𝑖𝑛 ç𝑒𝑣𝑟𝑒𝑠𝑖 = 2𝑢
- 𝑢 = (a+b+c) / 2
- Alan * Alan = 𝑢 * (𝑢 − 𝑎)* (𝑢 − 𝑏) * (𝑢 − 𝑐)

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

1. Java ile gidilen mesafeye (KM) göre taksimetre tutarını ekrana yazdıran programı yazın.

    -> Taksimetre KM başına 2.20 TL tutmaktadır.
    -> Minimum ödenecek tutar 20 TL'dir. 20 TL altında ki ücretlerde yine 20 TL alınacaktır.
    -> Taksimetre açılış ücreti 10 TL'dir.

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

1. Java ile yarı çapını kullanıcıdan aldığınız dairenin alanını ve çevresini hesaplayan programı yazın.

- Alan Formülü : π * r * r;
- Çevre Formülü : 2 * π * r;

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

2. Yarıçapı r, merkez açısısının ölçüsü 𝛼 olan daire diliminin alanı bulan programı yazınız.

- 𝜋 sayısını = 3.14 alınız.
- Formül : (𝜋 * (r*r) * 𝛼) / 360

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

1. Java ile kullanıcıdan boy ve kilo değerlerini alıp bir değişkene atayın. Aşağıda ki formüle göre kullanıcının "Vücut Kitle İndeks" değerini hesaplayıp ekrana yazdırın.

- FORMÜL: Kilo (kg) / Boy(m) * Boy(m)

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

1. Java ile kullanıcıların manavdan almış oldukları ürünlerin kilogram değerlerine göre toplam tutarını ekrana yazdıran programı yazın.

    -> Meyveler ve KG Fiyatları
- Armut : 2,14 TL
- Elma : 3,67 TL
- Domates : 1,11 TL
- Muz: 0,95 TL
- Patlıcan : 5,00 TL

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

1. Java ile kullanıcıların manavdan almış oldukları ürünlerin kilogram değerlerine göre toplam tutarını ekrana yazdıran programı yazın.

    -> Videodaki hesap makinesini switch-case kullanarak yapınız.

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

1. Java koşullu ifadeler ile kullanıcı adı ve şifreyi kontrol eden program yapımı.

    -> Eğer şifre yanlış ise kullanıcıya şifresini sıfırlayıp sıfırlamayacağını sorun, eğer kullanıcı sıfırlamak isterse yeni girdiği şifrenin hatalı girdiği ve unuttuğu şifre ile aynı olmaması gerektiğini kontrol edip , şifreler aynı ise ekrana "Şifre oluşturulamadı, lütfen başka şifre giriniz." sorun yoksa "Şifre oluşturuldu" yazan programı yazınız.

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

1. Java koşullu ifadeler ile kullanıcının not durumuna göre sınıfı geçme durumunu hesaplayan program yapımı.

Dersler: Matematik, Fizik, Türkçe, Kimya, Müzik
Geçme Notu: 55

    -> Eğer girilen ders notları 0 veya 100 arasında değil ise ortalamaya katılmasın.

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

1. Java koşullu ifadeler ile hava sıcaklığına göre etkinlik öneren program yapımı.

    -> Koşullar :
- Sıcaklık 5'dan küçük ise "Kayak" yapmayı öner.
- Sıcaklık 5 ve 15 arasında ise "Sinema" etkinliğini öner.
- Sıcaklık 15 ve 25 arasında ise "Piknik" etkinliğini öner.
- Sıcaklık 25'ten büyük ise "Yüzme" etkinliğini öner.

    -> Aynı örnek üzerinden if koşulları başka hangi şekilde oluşturulabilirdi farklı çözüm yolları bulunuz.

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

1. Java koşullu ifadeler ile girilen 3 sayıyı büyükten küçüğe sıralayan program yapımı.

    -> Girilen 3 sayıyı "küçükten büyüğe" sıralayan programı yazınız.

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

1. Java koşullu ifadeler ile kullanıcının burcunu bulan program yapımı.

- Koç Burcu : 21 Mart - 20 Nisan
- Boğa Burcu : 21 Nisan - 21 Mayıs
- İkizler Burcu : 22 Mayıs - 22 Haziran
- Yengeç Burcu : 23 Haziran - 22 Temmuz
- Aslan Burcu : 23 Temmuz - 22 Ağustos
- Başak Burcu : 23 Ağustos - 22 Eylül
- Terazi Burcu : 23 Eylül - 22 Ekim
- Akrep Burcu : 23 Ekim - 21 Kasım
- Yay Burcu : 22 Kasım - 21 Aralık
- Oğlak Burcu : 22 Aralık - 21 Ocak
- Kova Burcu : 22 Ocak - 19 Şubat
- Balık Burcu : 20 Şubat - 20 Mart

    -> Aynı örneği switch-case kullanmadan yapınız.

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

## <p id = 'Ödev 14' > ÖDEV 14 - Uçak Bilet Fiyatı Hesaplama </p>

1. Java ile mesafeye ve şartlara göre uçak bileti fiyatı hesaplayan programı yapın. Kullanıcıdan Mesafe (KM), yaşı ve yolculuk tipi (Tek Yön, Gidiş-Dönüş) bilgilerini alın. Mesafe başına ücret 0,10 TL / km olarak alın. İlk olarak uçuşun toplam fiyatını hesaplayın ve sonrasında ki koşullara göre müşteriye aşağıdaki indirimleri uygulayın ;

    -> Kullanıcıdan alınan değerler geçerli (mesafe ve yaş değerleri pozitif sayı, yolculuk tipi ise 1 veya 2) olmalıdır. Aksi takdirde kullanıcıya "Hatalı Veri Girdiniz !" şeklinde bir uyarı verilmelidir.

- Kişi 12 yaşından küçükse bilet fiyatı üzerinden %50 indirim uygulanır.

- Kişi 12-24 yaşları arasında ise bilet fiyatı üzerinden %10 indirim uygulanır.

- Kişi 65 yaşından büyük ise bilet fiyatı üzerinden %30 indirim uygulanır.

- Kişi "Yolculuk Tipini" gidiş dönüş seçmiş ise bilet fiyatı üzerinden %20 indirim uygulanır.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        double mesafeBasiUcret = 0.10;
        int mesafe, yas;
        int tip;

        Scanner scanner = new Scanner(System.in);

        System.out.print("Lütfen yaşınızı girin: ");
        yas = scanner.nextInt();

        System.out.print("Gideceğiniz mesafeyi km cinsinden girin: ");
        mesafe = scanner.nextInt();

        System.out.println("Yolculuk tipini seçin: 1=> Tek yön, 2=> Gidiş-dönüş");
        tip = scanner.nextInt();

        double normalTutar = mesafe * mesafeBasiUcret;

        double yasIndirimi12 = normalTutar * 0.5;
        double yasIndirimi1224 = normalTutar * 0.1;
        double yasIndirimi65 = normalTutar * 0.3;

        double indirimliTutar1 = normalTutar - yasIndirimi12;
        double indirimliTutar2 = normalTutar - yasIndirimi1224;
        double indirimliTutar3 = normalTutar - yasIndirimi65;

        double gidisDonusIndirim1 = indirimliTutar1 * 0.2;
        double gidisDonusIndirim2 = indirimliTutar2 * 0.2;
        double gidisDonusIndirim3 = indirimliTutar3 * 0.2;

        double toplamTutar1 = 2 * (indirimliTutar1 - gidisDonusIndirim1);
        double toplamTutar2 = 2 * (indirimliTutar2 - gidisDonusIndirim2);
        double toplamTutar3 = 2 * (indirimliTutar3 - gidisDonusIndirim3);

        switch (tip){
            case 1:
                if (yas<12){
                    System.out.println("Toplam Tutar: " + toplamTutar1);
                }else  if (yas >=12 && yas <=24){
                    System.out.println("Toplam Tutar: " + toplamTutar2);
                }else if (yas>24 && yas<65){
                    System.out.println("Toplam Tutar: " + normalTutar);
                }else {
                    System.out.println("Toplam Tutar: " + toplamTutar3);
                }
                break;

            case 2:
                if (yas<12){
                    System.out.println("Toplam Tutar: " + toplamTutar1);
                }else if (yas>=12 && yas<=24){
                    System.out.println("Toplam Tutar: " + toplamTutar2);
                }else if (yas>24 && yas<65){
                    System.out.println("Toplam Tutar: " + normalTutar * 2);
                }else {
                    System.out.println("Toplam Tutar: " + toplamTutar3);
                }
                break;

            default:
                System.out.println("Hatalı seçim yaptınız!");
        }

    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 15' > ÖDEV 15 - Çin Zodyağı Hesaplama </p>

1. Çin zodyağı hesaplanırken kişinin doğum yılının 12 ile bölümünde kalana göre bulunur.

- Doğum Tarihi %12 = 0 ➜ Maymun
- Doğum Tarihi %12 = 1 ➜ Horoz
- Doğum Tarihi %12 = 2 ➜ Köpek
- Doğum Tarihi %12 = 3 ➜ Domuz
- Doğum Tarihi %12 = 4 ➜ Fare
- Doğum Tarihi %12 = 5 ➜ Öküz
- Doğum Tarihi %12 = 6 ➜ Kaplan
- Doğum Tarihi %12 = 7 ➜ Tavşan
- Doğum Tarihi %12 = 8 ➜ Ejderha
- Doğum Tarihi %12 = 9 ➜ Yılan
- Doğum Tarihi %12 = 10 ➜ At
- Doğum Tarihi %12 = 11 ➜ Koyun

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        System.out.print("Lütfen doğum yılınızı girin: ");
        int year = scanner.nextInt();

        double hesap = year%12;

        if (hesap==0){
            System.out.println("Çin zodyağı burcunuz: Maymun");
        }
        if (hesap==1){
            System.out.println("Çin zodyağı burcunuz: Horoz");
        }
        if (hesap==2){
            System.out.println("Çin zodyağı burcunuz: Köpek");
        }
        if (hesap==3){
            System.out.println("Çin zodyağı burcunuz: Domuz");
        }
        if (hesap==4){
            System.out.println("Çin zodyağı burcunuz: Fare");
        }
        if (hesap==5){
            System.out.println("Çin zodyağı burcunuz: Öküz");
        }
        if (hesap==6){
            System.out.println("Çin zodyağı burcunuz: Kaplan");
        }
        if (hesap==7){
            System.out.println("Çin zodyağı burcunuz: Tavşan");
        }
        if (hesap==8){
            System.out.println("Çin zodyağı burcunuz: Ejderha");
        }
        if (hesap==9){
            System.out.println("Çin zodyağı burcunuz: Yılan");
        }
        if (hesap==10){
            System.out.println("Çin zodyağı burcunuz: At");
        }
        if (hesap==11){
            System.out.println("Çin zodyağı burcunuz: Koyun");
        }
    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 16' > ÖDEV 16 - Artık Yıl Hesaplama </p>

1. Java ile kullanıcının girdiği yılın artık olup olmadığını bulan programı yazınız.

:question: Artık yıl nedir?
    -> Artık yıl, Miladî takvimde 365 yerine 366 günü olan yıl. Bu fazladan gün (artık gün), normalde 28 gün olan şubat ayına 29 Şubat’ın eklenmesi ile elde edilir.

:question: Artık yıl nasıl hesaplanır?
    -> Genel bir kural olarak, artık yıllar 4 rakamının katı olan yıllardır:
- 1988, 1992, 1996, 2000, 2004, 2008, 2012, 2016, 2020, 2024 gibi.

    -> 100'ün katı olan yıllardan sadece 400'e kalansız olarak bölünebilenler artık yıldır:
- Örneğin 1200, 1600, 2000 yılları artık yıldır ancak 1700, 1800 ve 1900 artık yıl değildir.

    -> Sadece 400'e tam olarak bölünebilenlerin artık yıl kabul edilmesinin nedeni, bir astronomik yılın 365,25 gün değil, yaklaşık olarak 365,242 gün olmasından kaynaklanan hatayı gidermektir.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        int yil;

        Scanner scanner = new Scanner(System.in);

        System.out.print("Lütfen yıl giriniz: ");
        yil = scanner.nextInt();

        double hesap1 = yil%4;
        double hesap2 = yil%100;
        double hesap3 = yil%400;

        if (hesap1 == 0){
            if (hesap2 == 0){
                if (hesap3 == 0){
                    System.out.println(yil + " artık yıldır");
                }else {
                    System.out.println(yil + " artık yıl değildir");
                }
            }else {
                if (hesap1 == 0) {
                    System.out.println(yil + " artık yıldır");
                }else {
                    System.out.println(yil + " artık yıl değildir");
                }
            }
        }else {
            System.out.println(yil + " artık yıl değildir");
        }

    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 17' > ÖDEV 17 - Girilen Sayıya Kadar Çift Sayıları Bulma </p>

1. Java döngüler ile kullanıcının girdiği sayıya kadar çift olan sayıları bulan programı yazıyoruz.

    -> Java döngüler ile 0'dan girilen sayıya kadar olan sayılardan 3 ve 4'e tam bölünen sayıların ortalamasını hesaplayan programı yazınız.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);
        // ÇİFT SAYILARI BULMA
        int sayi;
        System.out.print("Bir sayı girin: ");
        sayi = scanner.nextInt();

        for (int i=1; i<=sayi; i++){
            if (i%2==0){
                System.out.println(i);
            }
        }

        // 3'e ve 4'e TAM BÖLÜNEN SAYILARIN ORTALAMASINI BULMA
        int sayi;
        int ortalama, toplam=0, bolen=0;
        System.out.print("Bir sayı girin: ");
        sayi = scanner.nextInt();

        for (int i=1; i<=sayi; i++){
            if (i%3==0 && i%4==0){
                System.out.println("3'e ve 4'e tam bölünen sayı/sayılar: " + i);
                toplam = toplam + i;
                bolen++;
            }
        }
            ortalama = toplam/bolen;
            System.out.println("Ortalama: " + ortalama);
    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 18' > ÖDEV 18 - Tek Sayıların Toplamını Bulan Program </p>

1. Java döngüler ile negatif bir değer girilene kadar kullanıcıdan girişleri kabul eden ve girilen değerlerden tek sayıları toplayıp ekrana basan programı yazıyoruz.

2. Java döngüler ile tek bir sayı girilene kadar kullanıcıdan girişleri kabul eden ve girilen değerlerden çift ve 4'ün katları olan sayıları toplayıp ekrana basan programı yazıyoruz.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);
        int sayi;
        int toplam=0;

        // TEK SAYILARIN TOPLAMINI BULMA
        do {
            System.out.print("Bir sayı girin: ");
            sayi = scanner.nextInt();
            if (sayi%2==1){
                toplam = toplam + sayi;
            }

        }while (sayi>0);
        System.out.println("Toplam: " + toplam);
    }
}
        // ÇİFT ve 4'ün KATI OLAN SAYILARIN TOPLAMINI BULMA
        do {
            System.out.print("Bir sayı girin: ");
            sayi = scanner.nextInt();
            if (sayi%4==0 && sayi%2==0){
                toplam = toplam + sayi;
            }

        }while (sayi%2==0);
        System.out.println("Toplam: " + toplam);
    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 19' > ÖDEV 19 - Girilen Sayının Kuvvetlerini Bulma </p>

1. Java döngüler ile girilen sayıya kadar olan 2'nin kuvvetlerini ekrana yazdıran programı yazıyoruz.

2. Java döngüler ile girilen sayıya kadar olan 4 ve 5'in kuvvetlerini ekrana yazdıran programı yazıyoruz.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);
        int sayi;
        int us1=0, us2=0, us3=0;

        // 2'nin KATLARINI BULMA
        System.out.print("Bir sayı girin: ");
        sayi = scanner.nextInt();

        for (int i=1; i<=sayi; i *=2){
            System.out.println(2 + "^" + us1 + "= " + i);
            us1++;
        }
    }
}

        // 4 ve 5'in KATLARINI BULMA
        for (int i=1; i<=sayi; i *=4){
            System.out.println(4 + "^" + us2 + "= " + i);
            us2++;
        }
        for (int i=1; i<=sayi; i *=5){
            System.out.println(5 + "^" + us3 + "= " + i);
            us3++;
        }
    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 20' > ÖDEV 20 - Faktoriyel Hesaplama </p>

1. Java ile faktöriyel hesaplayan program yazıyoruz.

2. N elemanlı bir kümenin elemanları ile oluşturulacak r elemanlı farklı grupların sayısı n’in r’li kombinasyonu olarak adlandırılır. N’in r’li kombinasyonu C(n,r) şeklinde gösterilir.

    -> Java ile kombinasyon hesaplayan program yazınız.

FORMÜL: C(n,r) = n! / (r! * (n-r)!)

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);
        int sayi;
        int n;
        int r;
        int nf=1;
        int rf=1;
        int nr=1;
        int kom;
        int faktoriyel = 1;

        // Faktoriyel Hesaplama
        System.out.print("Bir sayı girin: ");
        sayi = scanner.nextInt();

        for (int i=1;i<=sayi;i++){
            faktoriyel = faktoriyel * i;

        }
        System.out.println(sayi + "!= " + faktoriyel);

        // Kombinasyon Hesaplama
        System.out.print("n değeri: ");
        n = scanner.nextInt();
        System.out.print("r değeri: ");
        r = scanner.nextInt();

        for (int a=1; a<=n; a++){
            nf = nf * a;
        }
        for (int b=1; b<=r; b++){
            rf = rf * b;
        }
        for (int c=1; c<=n-r; c++){
            nr = nr * c;
        }
        kom = nf/(rf * (nr));
        System.out.println("C(" + n + "," + r + ")= " + kom);
    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 21' > ÖDEV 21 - Üslü Sayı Hesaplama </p>

1. Java ile kullanıcının girdiği değerler ile üslü sayı hesaplayan programı yazıyoruz.

    -> Java ile kullanıcının girdiği değerler ile üslü sayı hesaplayan programı "For Döngüsü" kullanarak yapınız.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);
        int n,r;
        int total=1;
        System.out.print("Üssü alınacak sayı: ");
        n = scanner.nextInt();
        System.out.print("Kaçıncı üssü: ");
        r = scanner.nextInt();

        for (int i=1; i<=r; i++){
            total = total * n;
        }
        System.out.println(n + "^" + r + "= " + total);
    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 22' > ÖDEV 22 - Armstrong Sayısı Bulma </p>

1. Java döngüler ile sayının armstrong sayı olup olmadığını bulan programı yazıyoruz.

    -> Bir sayının basamak sayılarının toplamını hesaplayan program yazınız.

ÖRNEK: 1643 = 1 + 6 + 4 + 3 = 14

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);
        int sayi;

        // ARMSTRONG SAYISINI BULMA
        System.out.print("Sayıyı girin: ");
        sayi = scanner.nextInt();

        int geciciSayi=sayi;
        int basSayisi=0;
        int basDegeri;
        int basUst=1;
        int sonuc = 0;

        while (geciciSayi!=0){
            geciciSayi = geciciSayi / 10;
            basSayisi++;
        }

        geciciSayi = sayi;
        while (geciciSayi!=0){
            basDegeri = geciciSayi % 10;

            basUst=1;
            for (int i=1; i<=basSayisi; i++){
                basUst = basUst * basDegeri;
            }
            sonuc = sonuc + basUst;
            geciciSayi = geciciSayi / 10;
        }
        if (sonuc==sayi){
            System.out.println(sayi + " sayısı bir Armstrong sayısıdır.");
        }else {
            System.out.println(sayi + " sayısı bir Armstrong sayısı değildir.");
        }

        // BASAMAK SAYILARININ TOPLAMINI HESAPLAMA
        int sayi2;
        int basmkSay=0, hafizaSay;

        System.out.print("Sayıyı girin: ");
        sayi2 = scanner.nextInt();

        hafizaSay=sayi2;

        for (int a=0;sayi2!=0;a++){
            sayi2 = sayi2 / 10;
            basmkSay++;
        }

        sayi2=hafizaSay;
        int basmkMod, basmkDeger;
        int mod2=10, bolum2=1, sonuc2=0;

        for (int b=1; b<=basmkSay; b++){
            basmkMod = sayi2 % mod2;
            basmkDeger = basmkMod / bolum2;
            mod2 *= 10;
            bolum2 *= 10;

            sonuc2 = sonuc2 + basmkDeger;
        }
        System.out.println(sonuc2);
    }
}
    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 23' > ÖDEV 23 - Harmonik Seri Bulma </p>

1. Java ile girilen sayının harmonik serisini bulan program yazacağız.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);
        int sayi;
        double result=0;

        System.out.print("N sayısını girin: ");
        sayi = scanner.nextInt();

        for (double i=1;i<=sayi;i++){
            result = result + (1/i);
        }
        System.out.println(result);
    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 24' > ÖDEV 24 - Yıldız İle Üçgen Yapımı </p>

1. Java ile girilen sayının harmonik serisini bulan program yazacağız.

    -> Java'da döngüler kullanarak yıldızlar ile elmas yapınız.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);
        // YILDIZLAR İLE ÜÇGEN YAPIMI
        System.out.print("Basamak sayısını girin: ");
        int bas = scanner.nextInt();

        for (int i=1; i<=bas; i++){
            for (int j=1; j<=(bas-i); j++){
                System.out.print(" ");
            }
            for (int k=1; k<=(2*i)-1; k++){
                System.out.print("*");
            }
            System.out.println();
        }
        // YILDIZLAR İLE ELMAS YAPIMI
        for (int a=1; a<=bas; a++){
            for (int b=1; b<=a; b++){
                System.out.print(" ");
            }
            for (int c=1; c<=(2*bas)-(2*a)-1; c++){
                System.out.print("*");
            }
            System.out.println("");
        }
    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 25' > ÖDEV 25 - ATM Projesi </p>

1. Java döngüler ile kullanıcının banka hesabını yönetebildiği bir ATM projesi yapıyoruz.

    -> Aynı projedeki ATM işlemlerini "Switch-Case" kullanarak yapınız.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        int bakiye=2000;
        int hak = 3;
        int secim;
        String kullaniciAdi;
        String sifre;

        System.out.println("Patika Bankası'na Hoşgeldiniz:)");
        System.out.println("*********************************************");

        while (true){

            System.out.print("Lütfen kullanıcı adınızı girin: ");
            kullaniciAdi = scanner.nextLine();

            System.out.print("Lütfen şifrenizi girin: ");
            sifre = scanner.nextLine();

            if (kullaniciAdi.equals("patika") && sifre.equals("1234")){
                System.out.println("Giriş başarılı");

                System.out.println("*********************************************");
                System.out.println("Yapmak istediğiniz işlemi seçiniz:\n" +
                        "1- Para çekme,\n" +
                        "2- Para yatırma,\n" +
                        "3- Bakiye sorgulama\n" +
                        "4- Çıkış");
                secim = scanner.nextInt();

                System.out.println("*********************************************");

                    do {
                        switch (secim) {
                            case 1:
                                System.out.println("Çekmek istediğiniz tutarı girin: ");
                                int cekilenTutar = scanner.nextInt();
                                if (cekilenTutar>bakiye){
                                    System.out.println("Yetersiz bakiye");
                                }
                                else {
                                    bakiye = bakiye - cekilenTutar;
                                    System.out.println("Yeni bakiyeniz: " + bakiye);
                                }
                                System.out.println("Yapmak istediğiniz işlemi seçiniz:\n" +
                                        "1- Para çekme,\n" +
                                        "2- Para yatırma,\n" +
                                        "3- Bakiye sorgulama\n" +
                                        "4- Çıkış");
                                secim = scanner.nextInt();
                                break;

                            case 2:
                                System.out.println("Yatırmak istediğiniz tutarı girin: ");
                                int yatirilanTutar = scanner.nextInt();
                                bakiye = bakiye + yatirilanTutar;
                                System.out.println("Yeni bakiyeniz: " + bakiye);
                                System.out.println("Yapmak istediğiniz işlemi seçiniz:\n" +
                                        "1- Para çekme,\n" +
                                        "2- Para yatırma,\n" +
                                        "3- Bakiye sorgulama\n" +
                                        "4- Çıkış");
                                secim = scanner.nextInt();
                                break;

                            case 3:
                                System.out.println("Bakiyeniz: " + bakiye);
                                System.out.println("Yapmak istediğiniz işlemi seçiniz:\n" +
                                        "1- Para çekme,\n" +
                                        "2- Para yatırma,\n" +
                                        "3- Bakiye sorgulama\n" +
                                        "4- Çıkış");
                                secim = scanner.nextInt();
                                break;

                            case 4:
                                break;

                            default:
                                System.out.println("Hatalı seçim yaptınız!\n");
                                System.out.println("Yapmak istediğiniz işlemi seçiniz:\n" +
                                        "1- Para çekme,\n" +
                                        "2- Para yatırma,\n" +
                                        "3- Bakiye sorgulama\n" +
                                        "4- Çıkış");
                                secim = scanner.nextInt();
                        }
                    }
                    while (secim!=4);
                System.out.println("Çıkış başarılı");
                break;
            }
            else {
                System.out.println("Hatalı kullanıcı adı ya da şifre.");
                hak--;
                System.out.println("Kalan hakkınız: " + hak);
                if (hak==0){
                    System.out.println("Sistemden çıkılıyor...");
                    break;
                }
            }
        }
    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 26' > ÖDEV 26 - EBOB - EKOK Bulma </p>

1. Java ile iki sayının EBOB ve EKOK değerlerini bulan program yazıyoruz.

FORMÜL: EKOK = (n1*n2) / EBOB

    -> Java ile iki sayının EBOB ve EKOK değerlerini "While Döngüsü" kullanarak yazınız.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        int sayi1;
        int sayi2;
        int ebob =1;
        int ekok=1;
        int a=1;

        System.out.print("Birinci sayı: ");
        sayi1 = scanner.nextInt();
        System.out.print("İkinci sayı: ");
        sayi2 = scanner.nextInt();

        while (a<=sayi1){
            if (sayi1%a==0 && sayi2%a==0){
                ebob=a;
            }
            a++;
        }
        System.out.println("EBOB: " + ebob);

        int b=1;
        while (b<=sayi1){
            if ((sayi1 * sayi2) % b == 0){
                ekok = (sayi1 * sayi2)/ebob;
            }
            b++;
        }
        System.out.println("EKOK: " + ekok);
    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 27' > ÖDEV 27 - Girilen Sayıdan Min ve Max Değeri Bulma </p>

1. Java ile klavyeden girilen N tane sayma sayısından en büyük ve en küçük sayıları bulan ve bu sayıları ekrana yazan programı yazın.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        int sayi;
        int kucukSayi=0;
        int buyukSayi=0;

        System.out.print("Kaç tane sayı gireceksin? ");
        int kacSayi = scanner.nextInt();

        for (int i=1;i<=kacSayi;i++){
            System.out.print(i + ". sayıyı gir: ");
            sayi = scanner.nextInt();

            if(sayi==1){
                kucukSayi=sayi;
                buyukSayi=sayi;
            }

            if (sayi>buyukSayi){
                buyukSayi=sayi;
            }
            if (sayi<kucukSayi){
                kucukSayi=sayi;
            }
        }
        System.out.println("En büyük sayı: " + buyukSayi);
        System.out.println("En küçük sayı: " + kucukSayi);

    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 28' > ÖDEV 28 - Mükemmel Sayı Bulma </p>

1. Klavyeden girilen bir sayının mükemmel sayı olup/olmadığını bulan ve sayı mükemmel sayı ise ekrana “mükemmel sayıdır.” değilse “mükemmel sayı değildir.” ifadelerini ekrana yazan programı Java dilinde yazınız.

    -> Mükemmel Sayı Nedir?: Bir sayının kendisi hariç pozitif tam sayı çarpanları (kalansız bölen sayıların) toplamı kendisine eşit olan sayıya mükemmel sayı denir.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        int i=1;
        int toplam=0;

        System.out.print("Bir sayı girin: ");
        int sayi = scanner.nextInt();

        while (i<sayi){
            if (sayi%i==0){
                toplam = toplam + i;
            }
            i++;
        }
        if (toplam==sayi){
            System.out.println(sayi + " mükemmel sayıdır.");
        }
        else {
            System.out.println(sayi + " mükemmel sayı değildir.");
        }

    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------

## <p id = 'Ödev 29' > ÖDEV 29 - Yıldızlar ile Ters Üçgen Yapımı </p>

1. Java ile basamak sayısının kullanıcıdan alınan ve döngüler kullanılarak, yıldızlar(*) ile ekrana ters üçgen çizen programı yazın.

### :red_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        System.out.print("Basamak sayısını girin: ");
        int basamak = scanner.nextInt();

        for (int a=1;a<=basamak;a++){
            for (int b=1;b<=a;b++){
                System.out.print(" ");
            }
            for (int c=1;c<=((2*basamak)-(2*a)+1);c++){
                System.out.print("*");
            }
            System.out.println("");
        }

    }
}
```
</details>
<br>

----------------------------------------------------------------------------------------------------