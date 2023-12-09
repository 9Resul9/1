#include <stdio.h>
#include <stdlib.h>
#include <ctype.h>	//isalpha ve tolower fonksiyonları için kütüphane

int main()
{
FILE *dosyainput;	//dosya atama komutları
FILE *dosyaoutput;	//dosya atama komutları
	
int secim;
baslangic: 
printf("*********************************");	
printf("Lutfen islem secin\n1. Sifre olusturma\n2. Sifre cozme\nSeciminiz --> ");	//kullanıcının seçim yapması için değişkeni alan komut
scanf("%d",&secim);

int anahtar=3;
switch(secim)	//kullanıcıya şifre çözme ve şifre oluşturma için 2 seçenek sunan switch-case komutu
{
	case 1:	//ŞİFRE OLUŞTURAN KISIM
	{	
		dosyainput=fopen("C:\\Users\\RESUL\\OneDrive\\Masaüstü\\input 1.txt","r");	//dosya konumları
		dosyaoutput=fopen("C:\\Users\\RESUL\\OneDrive\\Masaüstü\\output 1.txt","w");	//dosya konumları
		int karakter;
	
		printf("\nSifreniz:\n"); 
		do
		{
			karakter=getc(dosyainput);	//karakter değişkenini dosya içindeki karakterlere eşitleyen komut
			
			karakter==32 ? printf(".") , fputs(".",dosyaoutput) : "" ;	//metnin içindeki boşlukları farklı değerlendirmesi için  (32 boşluğun değeri)
			karakter==10 ? printf(":") , fputs(":",dosyaoutput) : "" ; 	//metnin içindeki alt satırları(\n) değerlendirmesi için  (10 ast satırın(\n) değeri)	
			
			if(isalpha(karakter))	//karakterin alfabede olup olmadığını kontrol eden blok
			{
				karakter=tolower(karakter);	//karakterleri küçük yapan komut
				karakter-='a';				// Örnek: b(98) -= a(97) -->1	(karakteri b varsayalım)
				karakter+=anahtar;		// 1 += 28 -->29  (anahtarı 28 varsayalım)
				karakter%=26;				// 29 %= 26 -->3
				karakter+='a';				// 3 += a(97) -->d(100)
				printf("%c",karakter); 		// karakter=d(100) 
				putc(karakter,dosyaoutput);	//dosyaya yazdırma komutu
			}
		}
		while(karakter!=EOF);	//bütün karakterlerin okunmasını sağlayan do-while bloğu
		printf("\n\nSifreniz output 1 dosyasina kaydedildi\n\n"); 
		
		fclose(dosyainput);		//dosyaları kapatan komut
		fclose(dosyaoutput);	//dosyaları kapatan komut
		goto baslangic;
	}
	break;
	case 2: //ŞİFRE ÇÖZEN KISIM
	{
		dosyaoutput=fopen("C:\\Users\\RESUL\\OneDrive\\Masaüstü\\output 1.txt","r");	//dosya konumları
		dosyainput=fopen("C:\\Users\\RESUL\\OneDrive\\Masaüstü\\input 1.txt","w");	//dosya konumları
		int karakter;
		
		printf("\nMetniniz:\n");
		do
		{
			karakter=getc(dosyaoutput);		//karakter değişkenini dosya içindeki karakterlere eşitleyen komut
			
			karakter=='.' ? printf(" ") , fputs(" ",dosyainput) : "" ;		//metnin içindeki boşlukları farklı değerlendirmesi için
			karakter==':' ? printf("\n") , fputs("\n",dosyainput) : "" ;	//metnin içindeki alt satırları(\n) değerlendirmesi için
			
			if(isalpha(karakter))	//karakterin alfabede olup olmadığını kontrol eden blok
			{
											//Örnek: karakter=d(100) anahtar=27 varsayalım
				anahtar%=26;				// 27 = 27%26 -->1
				karakter-='a';				// 100 -= a(97) -->3
				karakter+=(26-anahtar);		// 3 += (26-1) -->28
				karakter%=26;				// 28 %= 26 -->2
				karakter+='a';				// 2 += a(97) -->b(98)
				printf("%c",karakter); 		// karakter=b(98)
				putc(karakter,dosyainput);	// dosyaya yazdırma komutu
			}
		}
		while(karakter!=EOF);	//bütün karakterlerin okunmasını sağlayan do-while bloğu
		printf("\n\nMetniniz input 1 dosyasina kaydedildi\n\n"); 
		
		fclose(dosyainput);		//dosyaları kapatan komut
		fclose(dosyaoutput);	//dosyaları kapatan komut
		goto baslangic;

	}
	break;
	default:
		printf("gecersiz deger");	//seçim aşamasında farklı bir cevap için yanıt
	break; 	
}
	return 0;
}
