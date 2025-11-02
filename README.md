# 🎨 Draw-to-Mint - AI NFT Sanat Uygulaması

<div align="center">

![Draw-to-Mint](https://img.shields.io/badge/Draw--to--Mint-NFT%20Art-blueviolet?style=for-the-badge)
![Next.js](https://img.shields.io/badge/Next.js-15.3.4-black?style=for-the-badge&logo=next.js)
![React](https://img.shields.io/badge/React-19.1.0-61DAFB?style=for-the-badge&logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5.8.3-3178C6?style=for-the-badge&logo=typescript)
![Base](https://img.shields.io/badge/Base-Blockchain-0052FF?style=for-the-badge&logo=coinbase)

**Çizimlerinizi AI ile sanata dönüştürün ve Base blockchain üzerinde NFT olarak basın!**

[Demo](https://your-demo-url.vercel.app) • [Farcaster](https://warpcast.com) • [Zora](https://zora.co)

</div>

---

## 📖 Proje Hakkında

**Draw-to-Mint**, kullanıcıların dijital bir canvas üzerinde özgürce çizim yapmasına, bu çizimleri **Flux AI** ile profesyonel sanata dönüştürmesine ve ardından **Base blockchain** üzerinde NFT olarak basmasına olanak tanıyan bir **Farcaster Mini-App** uygulamasıdır.

### ✨ Temel Özellikler

#### 🖌️ **Çizim Sistemi**
- **Gelişmiş Canvas**: HTML5 Canvas API ile responsive çizim deneyimi
- **Fırça Kontrolleri**: Boyut ve renk seçenekleri
- **Temizleme & Sıfırlama**: Tek tıkla canvas temizleme
- **Edge Detection**: Sobel operatörü ile kenar çıkarma (AI tutarlılığı için)

#### 🤖 **AI Sanat Üretimi**
- **Flux Pro 1.1 Ultra**: En gelişmiş AI art generation modeli
- **6 Farklı Stil**:
  - 🖼️ Realist Sanat (Photorealistic)
  - 🎭 Fantasy Sanat (Magical)
  - 🌸 Anime Sanat (Japanese style)
  - 🏛️ Klasik Sanat (Renaissance)
  - 🔮 Cyberpunk (Futuristic neon)
  - 🌊 Soyut Sanat (Abstract expressionism)
- **Edge Preprocessing**: Çizimlerinize %75-85 oranında sadık kalma
- **Yeniden Oluşturma**: Farklı stil seçenekleri ile yeniden generate

#### 💎 **NFT Minting**
- **Zora Protocol**: Base blockchain üzerinde NFT minting
- **IPFS Storage**: Pinata ile decentralized storage
- **Metadata Yönetimi**: Otomatik NFT metadata oluşturma
- **Wallet Entegrasyonu**: OnchainKit ile wallet bağlantısı

#### 📱 **Farcaster Entegrasyonu**
- **Mini-App SDK**: Native Farcaster deneyimi
- **Otomatik Paylaşım**: Warpcast'te NFT paylaşımı
- **Manifest İmzalama**: Otomatik manifest doğrulama
- **Toast Notifications**: Kullanıcı geri bildirimleri

#### 🎨 **Modern UI/UX**
- **Dark Theme**: Koyu renk ağırlıklı profesyonel tasarım
- **Glassmorphism**: Cam efekti ile şık kartlar
- **Gradient Accents**: Mor-Cyan-Mavi gradient vurgular
- **Responsive Design**: Mobil ve masaüstü uyumlu
- **Smooth Animations**: Framer Motion ile akıcı geçişler

---

## 🏗️ Teknoloji Stack

### **Frontend**
- **Framework**: Next.js 15.3.4 (App Router)
- **UI Library**: React 19.1.0
- **Language**: TypeScript 5.8.3
- **Styling**: Tailwind CSS 4.1.16
- **Components**: Radix UI (shadcn/ui)
- **Animations**: Framer Motion 12.12.1
- **Icons**: Lucide React

### **Blockchain & Web3**
- **Wallet Connection**: Wagmi 2.19.2 + Viem 2.38.5
- **OnchainKit**: @coinbase/onchainkit 1.1.2
- **NFT Minting**: @zoralabs/protocol-sdk 0.13.14
- **Network**: Base (Chain ID: 8453)

### **AI & Storage**
- **AI Model**: Flux Pro 1.1 Ultra (FAL.ai)
- **IPFS Provider**: Pinata + nft.storage
- **Image Processing**: Canvas API + Sobel Edge Detection

### **Farcaster**
- **SDK**: @farcaster/miniapp-sdk 0.2.1
- **Manifest Signing**: Otomatik doğrulama
- **Warpcast Integration**: Cast composer

### **State Management & Data**
- **Query**: TanStack Query (@tanstack/react-query)
- **Forms**: React Hook Form + Zod
- **Logging**: Winston

---

## 🏛️ Mimari

```
┌─────────────────────────────────────────────────────────────┐
│                     KULLANICI AKIŞI                         │
└─────────────────────────────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│  1. ÇIZIM                                                    │
│  ┌────────────┐    ┌──────────────┐   ┌─────────────┐     │
│  │  Canvas    │───▶│ Fırça/Renk   │──▶│ Çizim Data  │     │
│  │  Drawing   │    │   Kontrol    │   │  (DataURL)  │     │
│  └────────────┘    └──────────────┘   └─────────────┘     │
└─────────────────────────────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│  2. PREPROCESSING                                            │
│  ┌────────────┐    ┌──────────────┐   ┌─────────────┐     │
│  │   Edge     │───▶│ Sobel Filter │──▶│  Edge Map   │     │
│  │ Detection  │    │  (Threshold) │   │  (Binary)   │     │
│  └────────────┘    └──────────────┘   └─────────────┘     │
└─────────────────────────────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│  3. AI GENERATION                                            │
│  ┌────────────┐    ┌──────────────┐   ┌─────────────┐     │
│  │ Edge Map + │───▶│  Flux Pro    │──▶│ Generated   │     │
│  │ Style Prompt│   │  1.1 Ultra   │   │   Art URL   │     │
│  └────────────┘    └──────────────┘   └─────────────┘     │
└─────────────────────────────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│  4. IPFS UPLOAD                                              │
│  ┌────────────┐    ┌──────────────┐   ┌─────────────┐     │
│  │ Art Image  │───▶│   Pinata     │──▶│  IPFS CID   │     │
│  │  + Metadata│    │  (Pin File)  │   │  + Gateway  │     │
│  └────────────┘    └──────────────┘   └─────────────┘     │
└─────────────────────────────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│  5. NFT MINTING                                              │
│  ┌────────────┐    ┌──────────────┐   ┌─────────────┐     │
│  │ Zora SDK + │───▶│   Base       │──▶│   NFT       │     │
│  │ IPFS URI   │    │  Blockchain  │   │  Minted! ✅ │     │
│  └────────────┘    └──────────────┘   └─────────────┘     │
└─────────────────────────────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│  6. FARCASTER PAYLAŞIM                                       │
│  ┌────────────┐    ┌──────────────┐   ┌─────────────┐     │
│  │ NFT Link + │───▶│  Warpcast    │──▶│   Cast      │     │
│  │  Metadata  │    │   Composer   │   │  Created! 📱│     │
│  └────────────┘    └──────────────┘   └─────────────┘     │
└─────────────────────────────────────────────────────────────┘
```

### 📁 Dosya Yapısı

```
src/
├── app/
│   ├── api/
│   │   ├── health/          # Health check endpoint
│   │   ├── logger/          # Logging endpoint
│   │   ├── proxy/           # External API proxy
│   │   └── upload-ipfs/     # Pinata IPFS upload
│   ├── config/
│   │   └── onchainkit.ts    # OnchainKit configuration
│   ├── types/
│   │   └── api.ts           # API type definitions
│   ├── layout.tsx           # Root layout + Farcaster metadata
│   ├── page.tsx             # Main app page
│   ├── providers.tsx        # React Query + OnchainKit providers
│   └── globals.css          # Global styles
├── components/
│   ├── ui/                  # shadcn/ui components (35+ components)
│   ├── DrawingCanvas.tsx    # Main drawing canvas component
│   ├── GeneratedArt.tsx     # AI art display & NFT minting
│   ├── StyleSelector.tsx    # Art style selection
│   ├── FarcasterWrapper.tsx          # Farcaster client wrapper
│   ├── FarcasterManifestSigner.tsx   # Auto manifest signer
│   └── FarcasterToastManager.tsx     # Toast notifications
├── lib/
│   ├── ipfs.ts              # IPFS helper functions
│   ├── logger.ts            # Winston logger setup
│   ├── utils.ts             # Utility functions (cn, etc.)
│   └── zora-mint.ts         # Zora NFT minting logic
├── hooks/
│   ├── useAddMiniApp.ts     # Farcaster add mini-app hook
│   ├── useManifestStatus.ts # Manifest status tracking
│   └── use-mobile.tsx       # Mobile detection hook
├── utils/
│   └── manifestStatus.ts    # Manifest status utilities
└── fluxpro-api.ts           # Flux AI API integration
```

---

## 🚀 Kurulum

### Gereksinimler

- **Node.js**: 18.x veya üzeri
- **npm**: 9.x veya üzeri
- **Git**: Versiyon kontrol için

### 1. Projeyi Klonlayın

```bash
git clone https://github.com/your-username/draw-to-mint.git
cd draw-to-mint
```

### 2. Bağımlılıkları Yükleyin

```bash
npm install
```

### 3. Geliştirme Sunucusunu Başlatın

```bash
npm run dev
```

Uygulama şu adreste çalışacak: [http://localhost:3000](http://localhost:3000)

---

## 🔑 API Keys Yapılandırması

Uygulamanın çalışması için aşağıdaki API anahtarları gereklidir:

### **1. FAL.ai (Flux AI)**
- **Dosya**: `src/fluxpro-api.ts`
- **Key Lokasyonu**: `FAL_KEY` sabiti (satır 7)
- **Nasıl Alınır**: [fal.ai](https://fal.ai) hesabı oluşturun
- **Kullanım**: AI art generation için

```typescript
// src/fluxpro-api.ts
const FAL_KEY = 'your-fal-api-key-here';
```

### **2. Pinata (IPFS)**
- **Dosya**: `src/app/api/upload-ipfs/route.ts`
- **Key Lokasyonu**: `PINATA_JWT` sabiti (satır 4)
- **Nasıl Alınır**: [pinata.cloud](https://app.pinata.cloud) hesabı oluşturun
  - Dashboard → API Keys → New Key
  - `pinFileToIPFS` yetkisini seçin
  - JWT token'ı kopyalayın
- **Kullanım**: NFT image & metadata storage

```typescript
// src/app/api/upload-ipfs/route.ts
const PINATA_JWT = 'your-pinata-jwt-token-here';
```

### **3. OnchainKit (Coinbase)**
- **Dosya**: `src/app/config/onchainkit.ts`
- **Key Lokasyonu**: `apiKey` (satır 7)
- **Nasıl Alınır**: [Coinbase Developer Portal](https://portal.cdp.coinbase.com)
- **Kullanım**: Wallet bağlantısı ve Base network entegrasyonu

```typescript
// src/app/config/onchainkit.ts
export const config: OnchainKitConfig = {
  apiKey: 'your-coinbase-api-key-here',
  chain: base,
};
```

### **4. Farcaster (Opsiyonel)**
- **Dosya**: `public/.well-known/farcaster.json`
- **Yapılandırma**: Farcaster manifest metadata
- **Nasıl Ayarlanır**: Farcaster developer docs'u takip edin
- **Kullanım**: Farcaster mini-app integration

---

## 📚 Kullanım

### 1️⃣ **Çizim Yapın**
1. Ana sayfada canvas bölümüne gidin
2. Fırça boyutunu ve rengini seçin
3. Mouse veya touch ile çizim yapın
4. "Clear Canvas" ile temizleyebilirsiniz

### 2️⃣ **Stil Seçin**
6 farklı stil seçeneğinden birini seçin:
- **Realist**: Gerçekçi, fotorealistik sanat
- **Fantasy**: Büyülü, fantastik dünya
- **Anime**: Japon anime tarzı
- **Klasik**: Rönesans tarzı klasik sanat
- **Cyberpunk**: Gelecekçi, neon ışıklı
- **Soyut**: Ekspresyonist soyut sanat

### 3️⃣ **AI Sanat Üretin**
1. "Generate AI Art" butonuna tıklayın
2. Sistem çiziminizi edge detection ile işler
3. Flux AI sanat üretir (30-60 saniye)
4. Sonuç ekranda görünür

### 4️⃣ **NFT Olarak Basın**
1. Üretilen sanat için:
   - NFT ismi girin
   - Açıklama ekleyin (opsiyonel)
2. "Connect Wallet" ile cüzdanınızı bağlayın
3. "Mint as NFT" butonuna tıklayın
4. İşlem onayı bekleyin
5. Zora'da NFT'nizi görüntüleyin!

### 5️⃣ **Warpcast'te Paylaşın**
- NFT mint edildikten sonra otomatik olarak Warpcast'te paylaşabilirsiniz
- Topluluk ile sanatınızı paylaşın!

---

## 🛠️ Geliştirme

### Build

```bash
npm run build
```

### Lint

```bash
npm run lint
```

### Type Check

```bash
npx tsc --noEmit
```

---

## 🚢 Deployment

### Vercel (Önerilen)

1. GitHub'a push yapın
2. [Vercel](https://vercel.com) hesabınızla bağlayın
3. Repository'yi import edin
4. Environment variables ekleyin (API keys)
5. Deploy!

### Environment Variables

Vercel dashboard'da şu değişkenleri ekleyin:
```
# Opsiyonel - eğer environment variable kullanmak isterseniz
NEXT_PUBLIC_FAL_API_KEY=your-fal-key
NEXT_PUBLIC_PINATA_JWT=your-pinata-jwt
NEXT_PUBLIC_COINBASE_API_KEY=your-coinbase-key
```

**Not**: Şu anda API keys kod içinde hardcoded. Production'da environment variable kullanımı önerilir.

---

## 🎯 Nasıl Çalışır?

### Edge Detection Preprocessing

Çizimlerinizin AI tarafından korunması için **Sobel Edge Detection** algoritması kullanılır:

```typescript
// Sobel operatörü ile kenar tespiti
const applyEdgeDetection = (imageData: ImageData): ImageData => {
  const sobelX = [-1, 0, 1, -2, 0, 2, -1, 0, 1];
  const sobelY = [-1, -2, -1, 0, 0, 0, 1, 2, 1];
  
  // Her pixel için gradient hesaplama
  for (let y = 1; y < height - 1; y++) {
    for (let x = 1; x < width - 1; x++) {
      let gx = 0, gy = 0;
      // 3x3 kernel uygulaması
      // ...gradient hesaplama
      const magnitude = Math.sqrt(gx * gx + gy * gy);
      // Binary threshold
      output[idx] = magnitude > 50 ? 255 : 0;
    }
  }
};
```

**Sonuç**: AI sadece kenarları görür → Yapıyı değiştiremez → Sadece renklendirme yapar!

### AI Prompt Engineering

AI'a spesifik talimatlar verilerek tutarlılık sağlanır:

```typescript
const prompt = `
CRITICAL: Preserve EXACT composition from reference image.
- EXACT same shapes and positions
- STRICT structural maintenance
- Only enhance: colors, textures, style
- DO NOT change composition
`;
```

### Zora NFT Minting

```typescript
// 1. IPFS'e yükle
const ipfsUrl = await uploadToIPFS(image, metadata);

// 2. Zora contract call
const { request } = await simulateContract({
  address: zoraMintContract,
  abi: zoraCreator1155ImplABI,
  functionName: 'mintWithRewards',
  args: [minterAccount, tokenId, quantity, minterArguments, referrer],
});

// 3. Blockchain transaction
const hash = await writeContract(request);
```

---

## 🤝 Katkıda Bulunma

Katkılarınızı bekliyoruz! 

1. Fork edin
2. Feature branch oluşturun (`git checkout -b feature/amazing-feature`)
3. Commit edin (`git commit -m 'Add amazing feature'`)
4. Push edin (`git push origin feature/amazing-feature`)
5. Pull Request açın

---

## 📄 Lisans

Bu proje MIT lisansı altında lisanslanmıştır.

---

## 🙏 Teşekkürler

- **Farcaster**: Mini-app platform
- **FAL.ai**: Flux AI API
- **Pinata**: IPFS hosting
- **Zora**: NFT protocol
- **Coinbase**: OnchainKit & Base network
- **Vercel**: Hosting platform
- **shadcn/ui**: UI component library

---

## 📞 İletişim

Sorular veya öneriler için:
- **GitHub Issues**: [github.com/your-repo/issues](https://github.com/your-repo/issues)
- **Farcaster**: [@your-username](https://warpcast.com/your-username)
- **Email**: your-email@example.com

---

<div align="center">

**⭐ Projeyi beğendiyseniz yıldız vermeyi unutmayın!**

Made with 💜 for the Farcaster & Base community

[⬆ Başa Dön](#-draw-to-mint---ai-nft-sanat-uygulaması)

</div>
