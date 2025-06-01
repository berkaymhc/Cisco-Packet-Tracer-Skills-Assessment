# Cisco-Packet-Tracer-Network-Labs

Bu depo, Cisco Packet Tracer kullanılarak tasarlanmış çeşitli ağ topolojileri üzerinde farklı ağ yapılandırma senaryolarını ve becerilerini sergileyen bir laboratuvar koleksiyonudur. Her bir lab, belirli ağ kavramlarını ve yapılandırma yöntemlerini (VLAN'ler, Trunking, Inter-VLAN Routing, Temel Anahtar ve Yönlendirici Yapılandırmaları, Spanning Tree Protocol vb.) pekiştirmek amacıyla tasarlanmıştır.

## İçerik

Bu depo, aşağıdaki bağımsız ağ lablarını içermektedir:

* **Lab1: Spanning Tree Protocol (STP) Uygulaması**
* **Lab2: Temel Switch ve VLAN Yapılandırması (SRWE Practice Pt Skills Assessment Part 2)**
* **Lab3: Inter-VLAN Routing (Router on a Stick ve Legacy)**

Her bir labın kendi `.pkt` dosyası bu deponun kök dizininde yer almaktadır.

## Labların Ortak Hedefleri ve Özellikleri

Genel olarak, bu lablar aşağıdaki becerileri geliştirmeyi ve doğrulamayı amaçlar:

* Cisco anahtarlarında (2960 serisi) VLAN oluşturma ve yönetimi.
* Access (Erişim) ve Trunk (Gövde) port yapılandırmaları.
* Anahtarlara ve yönlendiricilere IP adresi atama.
* VLAN içi ve VLAN'ler arası iletişimin (ping testleri) sağlanması.
* Yönlendiricilerde temel arayüz yapılandırmaları.
* Cisco Discovery Protocol (CDP) gibi yönetim protokollerinin kullanımı.
* Uzaktan yönetim (Telnet) yapılandırması ve testi.
* Ağ döngülerini önlemek için Spanning Tree Protocol (STP) yapılandırması ve analizi.

## Kurulum ve Kullanım

1.  Bu depoyu bilgisayarınıza klonlayın veya ZIP olarak indirin.
2.  İlgili `.pkt` dosyasını (örn: `stp_uygulama_2.pkt`, `Lab3_VLAN_Uygulamasi.pkt` veya `Lab4_IVR_Uygulamasi.pkt`) Cisco Packet Tracer yazılımı ile açın.
3.  Her labın ilgili bölümünde belirtilen talimatları ve hedefleri takip ederek cihazları yapılandırın.
4.  Yapılandırmalarınızı doğrulamak için belirtilen testleri gerçekleştirin.

## Gereksinimler

* Cisco Packet Tracer yazılımı (Tercihen en son sürüm).

## Lab Detayları

### Lab 1: Spanning Tree Protocol (STP) Uygulaması

**Dosya Adı:** `stp_uygulama_2.pkt`

Bu lab, ağdaki yedekli bağlantıların yönetimi ve döngülerin önlenmesi için Spanning Tree Protocol'ün (STP) temel prensiplerini ve yapılandırmalarını anlamaya odaklanır. Kök anahtar seçimi ve port durumları incelenir.

**Hedefler:**

* Ağdaki STP topolojisini gözlemleme ve analiz etme.
* Manuel olarak kök anahtarı (Root Bridge) belirleme.
* Manuel olarak ikincil kök anahtarı (Secondary Root Bridge) belirleme.
* STP'nin yedekli yolları nasıl engellediğini (Blocking State) ve port durumlarını (Root, Designated, Blocked) doğrulama.
* `show spanning-tree` komutunun çıktısını yorumlama.
* STP'nin ağdaki istikrarı nasıl sağladığını anlama.

### Lab 2 (Lab3): Temel Switch ve VLAN Yapılandırması

**Dosya Adı:** `Lab3_VLAN_Uygulamasi.pkt`

Bu lab, özellikle VLAN oluşturma, erişim portu ve trunk port yapılandırmaları, anahtarlara IP adresi atama ve temel yönetim (hostname, enable secret, Telnet) konularına odaklanır.

**Hedefler:**

* Sunucuların aynı VLAN içinde birbirine ping atabilmesi.
* Misafir laptop'larının aynı VLAN içinde birbirine ping atabilmesi.
* Bilgi İşlem bilgisayarlarının ve anahtarların aynı VLAN içinde birbirine ping atabilmesi.
* Farklı VLAN'ler arasında Layer 3 cihaz olmadan iletişim kurulamadığının doğrulanması (erişim olmamalıdır).
* `show cdp neighbors` komutunun çalıştırılması ve komşu cihazların not edilmesi.
* Bilgi İşlem bilgisayarından anahtarlara Telnet ile erişilebilmesi.

### Lab 3 (Lab4): Inter-VLAN Routing (Router on a Stick ve Legacy)

**Dosya Adı:** `Lab4_IVR_Uygulamasi.pkt`

Bu lab, iki yaygın Inter-VLAN Routing tekniğini (Router on a Stick ve Legacy Inter-VLAN Routing) pratik olarak uygulamayı ve karşılaştırmayı sağlar.

**Hedefler:**

* **Router on a Stick Bölümü:**
    * Anahtar yapılandırması sonrası aynı VLAN'deki PC5 ve PC6'nın birbirine ping atabilmesi.
    * Yönlendirici yapılandırması sonrası PC5'in farklı VLAN'deki PC7'ye ping ile erişebilmesi.
* **Legacy Inter-VLAN Routing Bölümü:**
    * PC1'in farklı bir VLAN'deki PC3'e ping ile erişebilmesi.

**Ek Notlar:**

* "Router on a Stick" topolojisinde, PC6 ve PC7'nin topoloji diyagramında aynı porta bağlı gibi görünmesine rağmen, fiziksel olarak farklı switch portlarına (örn: Fa0/1 ve Fa0/2) bağlanması gerekmektedir. Lütfen .pkt dosyasında bu düzenlemeyi yapınız.
* PC'lere (PC1, PC3, PC5, PC6, PC7) doğru IP adresi, alt ağ maskesi ve varsayılan ağ geçidi bilgilerini girdiğinizden emin olun.

## Katkıda Bulunma

Geri bildirimleriniz, hata düzeltmeleri veya yeni lab önerileriniz için lütfen bir "issue" açın veya "pull request" gönderin.

## Lisans

Tüm Hakları Saklıdır. (Veya isteğe bağlı olarak uygun bir açık kaynak lisansı seçebilirsiniz, örneğin MIT Lisansı.)
