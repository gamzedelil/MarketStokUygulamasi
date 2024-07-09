# MarketStokUygulamasi

package MarketStokUygulamasi;
 
class StokUygulamasi {   // StokUygulamasi adında bir sınıf tanımlıyoruz.

// Stoktaki ürünlerin özelliklerini tanımlıyoruz. Bu özelliklere sadece StokUygulamasi sınıfının içinden erişilebilmesi için ‘private’ kullandık.
    private String urunAdi;
    private int gelenAdet;
    private int satilanAdet;
    private double gelisFiyati;
    private double satisFiyati;

// StokUygulamasi sınıfının kurucu metodunu tanımlıyoruz.
    public StokUygulamasi (String urunAdi, int gelenAdet, int satilanAdet, double gelisFiyati, double satisFiyati) { 

// Stoktaki ürünlerin özelliklerine vereceğimiz değerleri atıyoruz.
        this.urunAdi = urunAdi; 
        this.gelenAdet = gelenAdet; 
        this.satilanAdet = satilanAdet; 
        this.gelisFiyati = gelisFiyati; 
        this.satisFiyati = satisFiyati;
    }
    
// Stoktaki ürünlerin yüzdelik kar oranını hesaplayan metodu tanımlıyoruz.
    public double karOrani() {
        return ((satisFiyati - gelisFiyati) / gelisFiyati) * 100;
    }
 // Stoktaki ürünlerden elde edilen toplam kar miktarını hesaplayan metodu tanımlıyoruz. 
    public double urunFiyati() {
        return (gelenAdet - satilanAdet) * gelisFiyati;
    }
    // Stoktaki ürünlerin bilgilerinin tamamını ekrana yazdıran metodu tanımlıyoruz.
    public void stokBilgileri() {
        System.out.println("\nÜrün Adı: " + urunAdi);
        System.out.println("Giriş Adeti: " + gelenAdet);
        System.out.println("Satış Adeti: " + satilanAdet);
        System.out.println("Kar Oranı: %" + karOrani());
        System.out.println("Toplam Kar: " + urunFiyati());
    }
    // Ana programı yazdık.
    
    public static void main(String[] args) {
//  StokUygulamasi sınıfından dört farklı stok ürünü nesnesi oluşturuyoruz.
        StokUygulamasi urun1 = new StokUygulamasi("Makarna", 500, 320, 5, 18);
        StokUygulamasi urun2 = new StokUygulamasi("Pirinc", 700, 540, 25, 60);
        StokUygulamasi urun3 = new StokUygulamasi("Un", 850, 600, 50, 75);
        StokUygulamasi urun4 = new StokUygulamasi("Tuz", 350, 175, 10, 25);

// Stoktaki her ürünün bilgilerini ekrana yazdırıyoruz.
        urun1.stokBilgileri();
        urun2.stokBilgileri();
        urun3.stokBilgileri();
        urun4.stokBilgileri();
    }
}

