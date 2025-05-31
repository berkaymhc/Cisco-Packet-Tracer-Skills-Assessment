# Cisco-Packet-Tracer-Skills-Assessment

Bu proje, Cisco Packet Tracer kullanılarak tasarlanmış bir ağ topolojisi üzerinde temel anahtar (Switch) yapılandırma becerilerini sergileyen ve test eden bir uygulama laboratuvarıdır. Bu laboratuvar, özellikle VLAN (Virtual Local Area Network) oluşturma, Erişim Portları (Access Ports) ve Trunk Portları yapılandırma, anahtarlara IP adresi atama ve temel yönetim (hostname, enable secret, Telnet) gibi konulara odaklanmaktadır.

## İçerik

Bu depoda aşağıdaki dosyalar bulunmaktadır:

* `Lab3_VLAN_Uygulamasi.pkt` dosyası: Cisco Packet Tracer topoloji dosyası. Bu dosyayı Cisco Packet Tracer yazılımı ile açabilirsiniz.

## Lab Hedefleri

Bu Packet Tracer labı, aşağıdaki ana hedeflere ulaşmayı amaçlamaktadır:

1.  **VLAN Oluşturma ve Yönetimi:**
    * Tüm anahtarlarda (SW1, SW2, SW3) `VLAN2 (SUNUCULAR)`, `VLAN3 (BILGI_ISLEM)` ve `VLAN4 (MISAFIR)` adında VLAN'lar oluşturulması.
2.  **Port Yapılandırması:**
    * Belirli portların (1-10, 11-20, 21-24) ilgili VLAN'lara "Access Port" olarak atanması.
    * Anahtarlar arası bağlantılar için ilgili portların "Trunk Port" olarak yapılandırılması.
3.  **IP Adresi Yönetimi:**
    * Anahtarların VLAN3 arayüzlerine IP adresleri atanması (`192.168.3.11/24`, `192.168.3.12/24`, `192.168.3.13/24`).
4.  **Temel Anahtar Yönetimi:**
    * Anahtarlarda hostname belirlenmesi (`SW1`, `SW2`, `SW3`).
    * `enable secret` şifresi (`cisco`) ve Telnet erişimi için `vty` şifresi (`cisco`) yapılandırması.

## Erişilebilirlik Testleri (Lab Başarı Kriterleri)

Yapılandırmalar tamamlandıktan sonra aşağıdaki erişilebilirlik testleri başarıyla gerçekleştirilmelidir:

* **A) VLAN İçi Sunucu Erişimi:** Sunucu1, aynı VLAN'deki Sunucu2 ve Sunucu3'e ping atabilmelidir.
* **B) VLAN İçi Misafir Cihaz Erişimi:** Misafir1, aynı VLAN'deki Misafir2, Misafir3 ve Misafir4'e ping atabilmelidir.
* **C) VLAN İçi Bilgi İşlem ve Anahtar Erişimi:** BilgiIslem1, aynı VLAN'deki diğer BilgiIslem bilgisayarlarına (BilgiIslem2, BilgiIslem3, BilgiIslem4) ve tüm anahtarlara (SW1, SW2, SW3) ping atabilmelidir.
* **D) VLAN'ler Arası Erişim Kontrolü:** Farklı VLAN'ler arasında doğrudan erişim (ping) olmamalıdır (Çünkü Layer 3 cihaz mevcut değildir).
* **E) CDP Komşuluk Kontrolü:** SW2 üzerinde `show cdp neighbors` komutu çalıştırılarak komşu cihazların (SW1, SW3) hangi portlardan bağlandığı doğrulanmalıdır.
* **F) Uzaktan Yönetim (Telnet):** BilgiIslem1'den tüm anahtarlara (SW1, SW2, SW3) Telnet ile erişilebilmelidir.

## Kurulum ve Kullanım

1.  Bu depoyu bilgisayarınıza klonlayın veya indirin.
2.  `Lab3_VLAN_Uygulamasi.pkt` dosyasını Cisco Packet Tracer yazılımı ile açın.
3.  Yukarıda belirtilen "Yapılacaklar" adımlarını takip ederek ağ cihazlarını yapılandırın.
4.  "Lab Hedefleri" bölümündeki testleri yaparak yapılandırmalarınızı doğrulayın.

## Gereksinimler

* Cisco Packet Tracer yazılımı (Tercihen en son sürüm).

## Katkıda Bulunma

Geri bildirimleriniz veya iyileştirme önerileriniz için issues açmaktan çekinmeyin.

## Lisans

Bu proje için herhangi bir açık kaynak lisansı belirtilebilir. (Örn: MIT, Apache 2.0 vb. Veya "Tüm Hakları Saklıdır" diyebilirsiniz.)
