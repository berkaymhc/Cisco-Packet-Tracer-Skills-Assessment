# Cisco-Packet-Tracer-Network-Labs

Bu depo, Cisco Packet Tracer kullanılarak tasarlanmış çeşitli ağ topolojileri üzerinde farklı ağ yapılandırma senaryolarını ve becerilerini sergileyen bir laboratuvar koleksiyonudur. Her bir lab, belirli ağ kavramlarını ve yapılandırma yöntemlerini (VLAN'ler, Trunking, Inter-VLAN Routing, Temel Anahtar ve Yönlendirici Yapılandırmaları, Spanning Tree Protocol vb.) pekiştirmek amacıyla tasarlanmıştır.

## STP Protokol Karşılaştırması

| Protokol          | Hız   | VLAN Desteği      | Uyumluluk             | Üretici |
| :---------------- | :---- | :---------------- | :-------------------- | :------ |
| STP (802.1D)      | Yavaş | Hayır             | Tüm cihazlar          | IEEE    |
| PVST              | Yavaş | Evet (Her VLAN)   | Cisco cihazlar        | Cisco   |
| PVST+             | Yavaş | Evet              | IEEE cihazlarla uyumlu | Cisco   |
| RSTP (802.1w)     | Hızlı | Hayır             | 802.1D ile uyumlu     | IEEE    |
| Rapid PVST+       | Hızlı | Evet              | Cisco cihazlar        | Cisco   |
| MSTP (802.1s)     | Hızlı | Evet (Gruplanmış VLAN) | 802.1w uyumlu         | IEEE    |

## İçerik

Bu depo, aşağıdaki bağımsız ağ lablarını içermektedir:

* **Lab1: Spanning Tree Protocol (STP) Uygulaması**
* **Lab2: Temel Switch ve VLAN Yapılandırması (SRWE Practice Pt Skills Assessment Part 2)**
* **Lab3: Inter-VLAN Routing (Router on a Stick ve Legacy)**
* **Lab4: STP Çoklu VLAN Uygulaması**
* **Lab5: STP Yol Seçimi ve STP Security**

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
2.  İlgili `.pkt` dosyasını (örn: `Lab1_STP_Uygulamasi/Lab1_STP_Uygulamasi.pkt`, `Lab2_VLAN_Uygulamasi/Lab2_VLAN_Uygulamasi.pkt` veya `Lab3_IVR_Uygulamasi/Lab3_IVR_Uygulamasi.pkt`) Cisco Packet Tracer yazılımı ile açın.
3.  Her labın ilgili bölümünde belirtilen talimatları ve hedefleri takip ederek cihazları yapılandırın.
4.  Yapılandırmalarınızı doğrulamak için belirtilen testleri gerçekleştirin.

## Gereksinimler

* Cisco Packet Tracer yazılımı (Tercihen en son sürüm).

## Lab Detayları

### Lab 1: Spanning Tree Protocol (STP) Uygulaması

**Dosya Adı:** `Lab1_STP_Uygulamasi/Lab1_STP_Uygulamasi.pkt`

Bu lab, ağdaki yedekli bağlantıların yönetimi ve döngülerin önlenmesi için Spanning Tree Protocol'ün (STP) temel prensiplerini ve yapılandırmalarını anlamaya odaklanır. Kök anahtar seçimi ve port durumları incelenir.

**Hedefler:**

* Ağdaki STP topolojisini gözlemleme ve analiz etme.
* Manuel olarak kök anahtarı (Root Bridge) belirleme.
* Manuel olarak ikincil kök anahtarı (Secondary Root Bridge) belirleme.
* STP'nin yedekli yolları nasıl engellediğini (Blocking State) ve port durumlarını (Root, Designated, Blocked) doğrulama.
* `show spanning-tree` komutunun çıktısını yorumlama.
* STP'nin ağdaki istikrarı nasıl sağladığını anlama.

### Lab 2 (Lab3): Temel Switch ve VLAN Yapılandırması

**Dosya Adı:** `Lab2_VLAN_Uygulamasi/Lab2_VLAN_Uygulamasi.pkt`

Bu lab, özellikle VLAN oluşturma, erişim portu ve trunk port yapılandırmaları, anahtarlara IP adresi atama ve temel yönetim (hostname, enable secret, Telnet) konularına odaklanır.

**Hedefler:**

* Sunucuların aynı VLAN içinde birbirine ping atabilmesi.
* Misafir laptop'larının aynı VLAN içinde birbirine ping atabilmesi.
* Bilgi İşlem bilgisayarlarının ve anahtarların aynı VLAN içinde birbirine ping atabilmesi.
* Farklı VLAN'ler arasında Layer 3 cihaz olmadan iletişim kurulamadığının doğrulanması (erişim olmamalıdır).
* `show cdp neighbors` komutunun çalıştırılması ve komşu cihazların not edilmesi.
* Bilgi İşlem bilgisayarından anahtarlara Telnet ile erişilebilmesi.

### Lab 3 (Lab4): Inter-VLAN Routing (Router on a Stick ve Legacy)

**Dosya Adı:** `Lab3_IVR_Uygulamasi/Lab3_IVR_Uygulamasi.pkt`

Bu lab, iki yaygın Inter-VLAN Routing tekniğini (Router on a Stick ve Legacy Inter-VLAN Routing) pratik olarak uygulamayı ve karşılaştırmayı sağlar.

**Hedefler:**

* **Router on a Stick Bölümü:**
    * Anahtar yapılandırması sonrası aynı VLAN'deki PC5 ve PC6'nın birbirine ping atabilmesi.
    * Yönlendirici yapılandırması sonrası PC5'in farklı VLAN'deki PC7'ye ping ile erişebilmesi.
* **Legacy Inter-VLAN Routing Bölümü:**
    * PC1'in farklı bir VLAN'deki PC3'e ping ile erişebilmesi.
    
### Lab 4: STP Çoklu VLAN Uygulaması

**Dosya Adı:** `Lab4_STP_MultiVLAN_Uygulamasi/stp_çoklu_vlan_uygulama.pkt`

*Not: Bu Packet Tracer dosyası, tekli VLAN STP ve çoklu VLAN STP senaryoları dahil olmak üzere farklı STP topolojilerini içermektedir.*

Bu lab, farklı VLAN'ler için Spanning Tree Protocol (STP) davranışını ve her VLAN için ayrı kök anahtarları belirlemeyi pratik olarak uygulamayı amaçlar. PVST+ (Per-VLAN Spanning Tree Plus) mantığını ve ağdaki yedekli yolların her VLAN bazında nasıl yönetildiğini anlamayı sağlar.

**Hedefler:**

* Her bir VLAN (VLAN 1, VLAN 10, VLAN 20) için ayrı kök anahtarları (Root Bridge) belirleme ve doğrulama.
* VLAN'ler arası STP davranışını gözlemleme ve farklı VLAN'ler için farklı ağ yollarının nasıl aktif olduğunu anlama.
* Trunk port yapılandırmasının STP üzerindeki etkisini gözlemleme ve `show interfaces trunk` çıktısını anlama.
* Belirlenen kök anahtarlara göre anahtar port rollerini (Root, Designated, Alternate/Blocked) analiz etme.
* Topolojideki yedekli yolların STP tarafından her VLAN için nasıl yönetildiğini (engellendiğini) doğrulama.
* Ping testleri ile VLAN içi iletişimi doğrulama ve STP tarafından engellenen yolları veya VLAN'ler arası iletişimi gözlemleme.

### Lab 5: STP Yol Seçimi ve STP Security

**Dosya Adı:** `Lab5_STP_Path_Selection_and_Security/stp_path_selection_and_security.pkt`

Bu lab, Spanning Tree Protocol (STP) yol seçimi mekanizmalarını derinlemesine incelemeyi ve ağdaki STP güvenlik özelliklerinin (örneğin, BPDU Guard, PortFast) yapılandırılması ve etkilerini anlamayı amaçlar. Ağdaki potansiyel döngüleri önlerken aynı zamanda ağın güvenliğini sağlamanın önemini vurgular.

**Hedefler:**

* STP'nin yol seçimi kriterlerini (Root Bridge seçimi, Root Port seçimi, Designated Port seçimi) anlama ve farklı senaryolarda bu seçimlerin nasıl yapıldığını gözlemleme.
* Port maliyetleri ve port öncelikleri gibi parametrelerin STP yol seçimi üzerindeki etkilerini manipüle etme.
* STP güvenlik özelliklerinden BPDU Guard ve PortFast'ı yapılandırma ve test etme.
* BPDU Guard'ın yetkisiz BPDU'ları nasıl algıladığını ve portları nasıl devre dışı bıraktığını gözlemleme.
* PortFast'ın portları hızla forwarding durumuna getirme yeteneğini ve bunun potansiyel risklerini anlama.
* `show spanning-tree` ve `show running-config` gibi komutlarla STP yapılandırmasını ve durumunu doğrulama.

**Ek Notlar:**

* "Router on a Stick" topolojisinde, PC6 ve PC7'nin topoloji diyagramında aynı porta bağlı gibi görünmesine rağmen, fiziksel olarak farklı switch portlarına (örn: Fa0/1 ve Fa0/2) bağlanması gerekmektedir. Lütfen .pkt dosyasında bu düzenlemeyi yapınız.
* PC'lere (PC1, PC3, PC5, PC6, PC7) doğru IP adresi, alt ağ maskesi ve varsayılan ağ geçidi bilgilerini girdiğinizden emin olun.

## Katkıda Bulunma

Geri bildirimleriniz, hata düzeltmeleri veya yeni lab önerileriniz için lütfen bir "issue" açın veya "pull request" gönderin.

## Lisans

Tüm Hakları Saklıdır. (Veya isteğe bağlı olarak uygun bir açık kaynak lisansı seçebilirsiniz, örneğin MIT Lisansı.)