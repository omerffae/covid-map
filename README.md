# 🌍 COVID-19 Dünya Haritası

COVID-19 verilerini görselleştiren interaktif bir web uygulaması. Dünya haritası üzerinde ülke bazlı COVID-19 istatistiklerini gösterir ve detaylı analizler sunar.

## ✨ Özellikler

- 🌐 **İnteraktif Dünya Haritası**: React Simple Maps ile oluşturulmuş interaktif harita
- 📊 **Gerçek Zamanlı Veriler**: RapidAPI üzerinden güncel COVID-19 verileri
- 🏠 **Ana Sayfa**: Genel istatistikler ve dünya haritası görünümü
- 📋 **Detay Sayfası**: Ülke bazlı detaylı COVID-19 analizleri
- 🎨 **Modern UI**: Tailwind CSS ile tasarlanmış responsive arayüz
- 🔄 **State Yönetimi**: Redux Toolkit ile merkezi state yönetimi
- 🧪 **Test Kapsamı**: Jest ve React Testing Library ile kapsamlı testler
- 📱 **Responsive Tasarım**: Mobil ve masaüstü uyumlu

## 🛠️ Teknolojiler

### Frontend
- **React 18** - Modern React hooks ve functional components
- **Vite** - Hızlı build tool ve development server
- **Tailwind CSS** - Utility-first CSS framework
- **React Router DOM** - Client-side routing

### State Management
- **Redux Toolkit** - Modern Redux state yönetimi
- **React Redux** - React-Redux entegrasyonu
- **Redux Thunk** - Asenkron action'lar için

### Harita ve Veri Görselleştirme
- **React Simple Maps** - SVG tabanlı interaktif haritalar
- **Millify** - Büyük sayıları okunabilir formata çevirme

### API ve Veri
- **Axios** - HTTP client
- **RapidAPI** - COVID-19 veri API'leri

### Test ve Kalite
- **Jest** - Test framework
- **React Testing Library** - React component testleri
- **ESLint** - Kod kalitesi ve stil kontrolü

## 📦 Kurulum

### Gereksinimler
- Node.js (v16 veya üzeri)
- npm veya yarn

### Adımlar

1. **Projeyi klonlayın**
```bash
git clone https://github.com/omerffae/covid-map.git
cd covid_map
```

2. **Bağımlılıkları yükleyin**
```bash
npm install
```

3. **Geliştirme sunucusunu başlatın**
```bash
npm run dev
```

4. **Tarayıcıda açın**
```
http://localhost:5173
```

## 🚀 Kullanılabilir Scriptler

```bash
# Geliştirme sunucusu
npm run dev

# Production build
npm run build

# Build önizleme
npm run preview

# Test çalıştırma (watch mode)
npm test

# Linting
npm run lint
```

## 📁 Proje Yapısı

```
src/
├── components/          # Yeniden kullanılabilir bileşenler
│   ├── error/          # Hata bileşenleri
│   ├── header/         # Header bileşeni
│   └── loader/         # Yükleme bileşenleri
├── pages/              # Sayfa bileşenleri
│   ├── home/           # Ana sayfa
│   │   ├── hero.jsx    # Hero bölümü
│   │   ├── map.jsx     # Harita bileşeni
│   │   └── statistics.jsx # İstatistikler
│   └── detail/         # Detay sayfası
│       ├── card.jsx    # Ülke kartı
│       ├── content.jsx # İçerik
│       └── head.jsx    # Başlık
├── redux/              # Redux store ve slice'lar
│   ├── actions.js      # Action creators
│   ├── covidSlice.js   # COVID veri slice'ı
│   └── store.js        # Redux store
├── utils/              # Yardımcı fonksiyonlar
│   ├── api.js          # API çağrıları
│   └── constants.js    # Sabitler
└── __test__/           # Test dosyaları
```

## 🔌 API Entegrasyonu

### Kullanılan API'ler

1. **COVID-19 Statistics API**
   - Endpoint: `https://rapidapi.com/axisbits-axisbits-default/api/covid-19-statistics`
   - Kullanım: Genel dünya istatistikleri

2. **COVID-193 API**
   - Endpoint: `https://rapidapi.com/api-sports/api/covid-193`
   - Kullanım: Ülke bazlı detay veriler

### Harita Verileri
- **TopoJSON**: Dünya haritası geometri verileri
- Kaynak: [World Atlas TopoJSON](https://github.com/topojson/world-atlas)

## 🧪 Test Yazımı

### Test Yapısı

Proje Jest ve React Testing Library kullanarak test yazımını destekler.

#### Test Methodları

**Sadece `describe` bloğu içinde kullanılabilen methodlar:**

- `beforeEach`: Her testin öncesinde çalışır
- `afterEach`: Her testin sonrasında çalışır
- `beforeAll`: Bütün testlerin öncesinde çalışır
- `afterAll`: Bütün testlerin sonrasında çalışır

#### Element Seçicileri

Element seçicileri 3 ana parçadan oluşur:

1. **Method Tipi:**
   - `get`: Element bulunamazsa hata fırlatır
   - `query`: Element bulunamazsa `null` döndürür
   - `find`: Asenkron elementler için kullanılır

2. **All İfadesi:**
   - Birden fazla element için `All` eki eklenir
   - Örnek: `getAllBy`, `queryAllBy`, `findAllBy`

3. **Sorgu Methodu:**
   - `ByRole`: ARIA role ile seçim
   - `ByLabelText`: Label text ile seçim
   - `ByPlaceholder`: Placeholder text ile seçim
   - `ByText`: Text içeriği ile seçim
   - `ByTitle`: Title attribute ile seçim
   - `ByTestId`: Test ID ile seçim
   - `ByAltText`: Alt text ile seçim
   - `ByDisplayValue`: Input değeri ile seçim

**Örnekler:**
```javascript
// Tek element
getByTestId('country-card')
queryByTestId('loading-spinner')
findByTestId('async-data')

// Çoklu element
getAllByTestId('country-item')
queryAllByTestId('statistic-card')
findAllByTestId('map-region')
```

### Test Yazım Yaklaşımları

#### TDD (Test Driven Development)
- **Red-Green-Refactor** döngüsü
- Önce başarısız testler yazılır
- Sonra testleri geçecek kod yazılır
- Son olarak kod refactor edilir

#### TAD (Test After Development)
- Geleneksel yaklaşım
- Kod tamamlandıktan sonra testler yazılır

### Test Çalıştırma

```bash
# Tüm testleri çalıştır
npm test

# Belirli test dosyasını çalıştır
npm test -- content.test.jsx

# Coverage raporu ile çalıştır
npm test -- --coverage
```

## 🎨 Stil ve Tasarım

### Tailwind CSS Kullanımı

Proje Tailwind CSS ile stillendirilmiştir. Özel konfigürasyon `tailwind.config.js` dosyasında bulunur.

### Responsive Tasarım

- **Mobile First** yaklaşımı
- Breakpoint'ler: `sm`, `md`, `lg`, `xl`, `2xl`
- Flexbox ve Grid layout kullanımı

## 🔧 Geliştirme

### Kod Standartları

- ESLint konfigürasyonu mevcuttur
- Prettier entegrasyonu önerilir
- Component'ler functional component olarak yazılır
- Hooks kullanımı teşvik edilir

### Yeni Özellik Ekleme

1. Redux slice'ı güncelleyin veya yeni slice oluşturun
2. Component'leri geliştirin
3. Test'leri yazın
4. API entegrasyonunu kontrol edin

## 🚀 Deployment

### Production Build

```bash
npm run build
```

Build sonrası `dist` klasörü oluşur ve statik dosyalar hazır hale gelir.

### Hosting Önerileri

- **Vercel**: Vite projeleri için optimize edilmiş
- **Netlify**: Kolay deployment ve CI/CD
- **GitHub Pages**: Ücretsiz hosting
- **Firebase Hosting**: Google'ın hosting servisi

## 🤝 Katkıda Bulunma

1. Fork yapın
2. Feature branch oluşturun (`git checkout -b feature/amazing-feature`)
3. Değişikliklerinizi commit edin (`git commit -m 'Add amazing feature'`)
4. Branch'inizi push edin (`git push origin feature/amazing-feature`)
5. Pull Request oluşturun

### Katkıda Bulunma Kuralları

- Kod standartlarına uyun
- Test'leri yazın
- README'yi güncelleyin
- Commit mesajlarını açıklayıcı yazın

- **Proje Linki**: [GitHub Repository](https://github.com/omerffae/covid-map.git)

## 🙏 Teşekkürler

- [RapidAPI](https://rapidapi.com/) - COVID-19 veri API'leri
- [React Simple Maps](https://www.react-simple-maps.io/) - Harita kütüphanesi
- [Tailwind CSS](https://tailwindcss.com/) - CSS framework
- [Vite](https://vitejs.dev/) - Build tool

---

⭐ Bu projeyi beğendiyseniz yıldız vermeyi unutmayın!