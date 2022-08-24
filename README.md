# **Next JS Türkçe Döküman**

1. [**Başlarken**](#başlarken)

## Başlarken 

Next.js dökümanına hoş geldiniz!

Eğer Next.js'de yeniyseniz öğrenmeye [buradan](https://nextjs.org/learn/basics/create-nextjs-app) kurslarda başlayabilirsiniz.

Quizler içeren interaktif kurslar size Next.js'i kullanma konusunda bilmeniz gereken her şeyde size yardımcı olacak.

Eğer Next.js ile alakalı herhangi bir sorunuzda [Github Discussions](https://github.com/vercel/next.js/discussions) sayfasından her zaman soru sorabilirsiniz.

#### Sistem Gereksinimleri

- Node.js 12.22.0 veya daha üstü
- MacOS, Windows (WSL dahil), ve Linux desteklenmektedir

### Otomatik Kurulum

Yeni bir Next.js uygulaması oluştururken `create-next-app` ile oluşturmayı öneriyoruz. Çünkü her şey otomatik olarak sizin için hazır halde geliyor. Yeni bir proje oluşturmak için terminalizden şu komutları yazabilirsiniz:

```bash
npx create-next-app@latest
# veya
yarn create next-app
# veya
pnpm create next-app
```

Eğer TypeScript ile bir proje oluşturmak istiyorsunuz `--typescript` komutu ekleyebilirsiniz:

```bash
npx create-next-app@latest --typescript
# veya
yarn create next-app --typescript
# veya
pnpm create next-app --typescript
```

Kurulum tamamlandıktan sonra:

- `npm run dev` veya `yarn dev` veya `pnpm dev` komutları ile development ortamı localinizde `http://localhost:3000` şeklinde ayağa kaldırabilirsiniz
- `http://localhost:3000`  adresini ziyaret ederek uygulamanızı görebilirsiniz
- `pages/index.js` dosyasını düzenleyip sonucu tarayıcınızda görebilirsiniz

Daha fazla bilgi ve `create-next-app` komunutu nasıl kullanılacağıyla ilgili dökümana [buradan](https://nextjs.org/docs/api-reference/create-next-app) ulaşabilirsiniz.



### Manuel Kurulum

`next`, `react` ve `react-dom` paketlerini projenize kurun: 

```bash
npm install next react react-dom
# veya
yarn add next react react-dom
# veya
pnpm add next react react-dom
```

`package.json` dosyasını açın ve `scripts` bölümüne şu satırları ekleyin:

```json
"scripts": {
  "dev": "next dev",
  "build": "next build",
  "start": "next start",
  "lint": "next lint"
}
```

Bu scriptler uygulamanın geliştirme ortamındaki farklılıklarına referans olur:

- `dev` - `next dev` komutuyla birlikte development modda uygulamayı başlatır
- `buld` - `next build` komutuyla uygulamayı production ortam için build alır
- `start` - `next start` komutuyla birlikte Next.js'i production ortamda başlatır
- `lint` - `next lint` komutuyla ESLint ayarlarıyla projeyi düzenler

Ana klasörde `pages` ve `public` adında iki tane klasör oluşturun:

- `pages` - İçerisindeki dosya ismine göre route oluşturur. Örnek: `pages/hakkimizda.js` dosyası
  `http://localhost:3000/hakkimizda` yolunu oluşturur

- `public` - Statik assetleri (resimler, font vs) depolamaya yaran klasördür. Bu klasördeki assetleri code içerisinde
  ana url'den çekiliyormuş gibi kullanabiliriz. Örnek: `public/logo.png` dosyasını kod içerisinde aşağıdaki gibi kullanabiliriz

  ```jsx
  <img src="/logo.png" />
  ```


