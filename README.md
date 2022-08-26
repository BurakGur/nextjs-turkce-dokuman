# Next.js Türkçe Döküman

Merhaba, ben Burak. Next.js dökümanını Türkçe'ye çeviriyorum. Buradaki amacım bire bir çeviriden ziyade kendi notlarımla birlikte anlaşılır bir Türkçe Next.js dökümanı oluşturmak. Lütfen eklemek veya düzenlemek istediğiniz kısımları pull request açın.

İyi okumalar. 

### Döküman
1. [**Başlarken**](#başlarken)
2. [**Basit Özellikler**](#basit-özellikler)
   1. [**Sayfalar**](#sayfalar)

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


### Manuel Kurulum

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

Next.js sayfa konsepti üzerine inşa edilmiştir. Bir sayfa, `pages` klasörü içerisinde `.js`, `.jsx`, `.ts`, or `.tsx`
uzantılı bir dosyanın React Component olarak dışarı aktarılmış halidir. Ayrıca dosya isimlendirmesiyle dinamik route da oluşturabilirsiniz.

Projeye başlamak için `pages` klasörü içerisine `index.js` isimli bir sayfa oluşturun. Bu sayfa kullanıcılar sitenizi ziyaret ettiğinde gördükleri ana sayfanızdır. 

`pages/index.js` sayfasını aşağıdaki gibi bir tanımlama yapabilirsiniz: 

```jsx
function HomePage() {
  return <div>Welcome to Next.js!</div>
}

export default HomePage
```

Kurulum bittikten sonra:

- `npm run dev` veya `yarn dev` veya `pnpm dev` komutları ile development ortamı localinizde `http://localhost:3000` şeklinde ayağa kaldırabilirsiniz
- `http://localhost:3000` adresini ziyaret ederek uygulamanızı görebilirsiniz
- `pages/index.js` dosyasını düzenleyip sonucu tarayıcınızda görebilirsiniz

Next.js ile birlikte:

- Otomatik derleme ve paketleme
- React Fash Refresh (Hızlı Yenileme)
- Statik dışa aktarım ve `pages` ile server tarafında render
- Statik dosya aktarımı ile `public/` içerisindeki assetleri ana url'de kullanma

Ayrıca herhangi bir Next.js uygulaması productiona baştan itibaren hazırdır. Bununla ilgili daha fazla bilgi için [Yayına Alma](https://nextjs.org/docs/deployment) dökümanını okuyabilirsiniz.

## Basit Özellikler

### Sayfalar

Next.js sayfa konsepti üzerine inşa edilmiştir. Bir sayfa, `pages` klasörü içerisinde `.js`, `.jsx`, `.ts`, or `.tsx` uzantılı bir dosyanın React Component olarak dışarı aktarılmış halidir. İçerisindeki dosya ismine göre route oluşturur.

***Örnek:***  `pages/hakkimizda.js` dosyası `http://localhost:3000/hakkimizda` yolunu oluşturur.

```jsx
function About() {
  return <div>About</div>
}

export default About
```

#### Dinamik Sayfalar

Next.js dinamik sayfaları destekler. Örnek olarak, eğer `pages/yazilar/[id].js` isimli bir dosya oluşturursanız, `http://localhost:3000/yazilar/1`, `http://localhost:3000/yazilar/2` gibi uzantılara erişebilirsiniz.

Daha fazla bilgi için [Dinamik Sayfalar dökümanını](#dinamik-sayfalar) ziyaret edebilirsiniz.

### Pre-rendering

Varsayılan olarak Next.js tüm sayfaları **pre-render** işlemini uygular. Yani Next.js her sayfayı client tarafındaki JavaScript ile değil,  kendi oluşturduğu HTML ile yapar. Örnek olarak React her sayfayı client tarafındaki JavaScript ile üretir, Next.js ise bildiğimiz HTML ile yapar. Bu da hem daha iyi performans hem de daha iyi SEO puanı demektir.

Next.js 'in oluşturduğu her HTML o sayfa için gerekli minimum JavaScript koduyla birleştirilir. Sayfa tarayıcı tarafından yüklendiğinde, bu JavaScript kodu çalışır ve sayfayı komple interaktif hale getirir. (Bu işleme *hidrasyon* denir.)

#### Pre-rendering'in İki Türü

Next.js'in iki tür pre-rendering çeşidi vardır. Bunlar **Static Generation** (Statik Üretim) ve **Server-side Rendering** (Sunucu taraflı render) olarak tanımlanır ve farkları HTML sayfalarını **ne zaman** ürettikleridir.

- **Statik Generation (Önerilen):** HTML build sırasında oluşturulur ve her istekte kullanılır.
- **Server-side Rendering**: HTML her istekte oluşturulur.

Buradaki temel fark Static Generation bize HTML kodu oluşmuş bir yapı sunarken Server-side Rendering istek anında oluşturur.


Önemli olan noktalardan bir tanesi, Next.js her sayfa için pre-rendering yöntemini **seçmenize** izin verir. Burada "hibrit" bir yapı da kullanabilirsiniz. Next.js uygulamanızın çoğu sayfasında Static Generation kullanırken, bazı sayfalar da Server-side Rendering kullanabilirsiniz.

Biz performans sebebiyle Server-side Rendering yerine **Static Generation** kullanmanızı **öneriyoruz**. Statik oluşturulmuş sayfalar herhangi bir ekstra ayar yapmadan CDN ile cachelenebilir ve performans olarak çok üst seviyelere çıkabilir. Ancak bazı durumlarda Server-side Rendering tek seçenek olabilir.

Ayrıca Statik Generation ve Server-side Rendering ile birlikte **client tarafında data fetch** işlemleri yapabilirsiniz. Bu bazı sayfaların client tarafında JavaScript ile render edileceğini anlamına gelir. Daha fazla bilgi için [Data Fetching](#client-tarafında-data-fetch) dökümanına göz atabilirsiniz.

### Static Generation (Önerilen)

<details>
  <summary>Örnekler</summary>
  <ul>
  <li>
    <a href="https://github.com/vercel/next.js/tree/canary/examples/cms-wordpress" class="absolute" target="_blank" rel="noopener noreferrer">WordPress Örneği</a> ( <a href="https://next-blog-wordpress.vercel.app" class="absolute" target="_blank" rel="noopener noreferrer">Demo</a>)
  </li>
  <li>
    <a href="https://github.com/vercel/next.js/tree/canary/examples/blog-starter" class="absolute" target="_blank" rel="noopener noreferrer">Markdown Dosyalarıyla Blog Başlangıcı</a> ( <a href="https://next-blog-starter.vercel.app/" class="absolute" target="_blank" rel="noopener noreferrer">Demo</a>)
  </li>
  <li>
    <a href="https://github.com/vercel/next.js/tree/canary/examples/cms-datocms" class="absolute" target="_blank" rel="noopener noreferrer">DatoCMS Örneği</a> ( <a href="https://next-blog-datocms.vercel.app/" class="absolute" target="_blank" rel="noopener noreferrer">Demo</a>)
  </li>
  <li>
    <a href="https://github.com/vercel/next.js/tree/canary/examples/cms-takeshape" class="absolute" target="_blank" rel="noopener noreferrer">TakeShape Örneği</a> ( <a href="https://next-blog-takeshape.vercel.app/" class="absolute" target="_blank" rel="noopener noreferrer">Demo</a>)
  </li>
  <li>
    <a href="https://github.com/vercel/next.js/tree/canary/examples/cms-sanity" class="absolute" target="_blank" rel="noopener noreferrer">Sanity Örneği</a> ( <a href="https://next-blog-sanity.vercel.app/" class="absolute" target="_blank" rel="noopener noreferrer">Demo</a>)
  </li>
  <li>
    <a href="https://github.com/vercel/next.js/tree/canary/examples/cms-prismic" class="absolute" target="_blank" rel="noopener noreferrer">Prismic Örneği</a> ( <a href="https://next-blog-prismic.vercel.app/" class="absolute" target="_blank" rel="noopener noreferrer">Demo</a>)
  </li>
  <li>
    <a href="https://github.com/vercel/next.js/tree/canary/examples/cms-contentful" class="absolute" target="_blank" rel="noopener noreferrer">Contentful Örneği</a> ( <a href="https://next-blog-contentful.vercel.app/" class="absolute" target="_blank" rel="noopener noreferrer">Demo</a>)
  </li>
  <li>
    <a href="https://github.com/vercel/next.js/tree/canary/examples/cms-strapi" class="absolute" target="_blank" rel="noopener noreferrer">Strapi Örneği</a> ( <a href="https://next-blog-strapi.vercel.app/" class="absolute" target="_blank" rel="noopener noreferrer">Demo</a>)
  </li>
  <li>
    <a href="https://github.com/vercel/next.js/tree/canary/examples/cms-prepr" class="absolute" target="_blank" rel="noopener noreferrer">Prepr Örneği</a> ( <a href="https://next-blog-prepr.vercel.app/" class="absolute" target="_blank" rel="noopener noreferrer">Demo</a>)
  </li>
  <li>
    <a href="https://github.com/vercel/next.js/tree/canary/examples/cms-agilitycms" class="absolute" target="_blank" rel="noopener noreferrer">Agility CMS Örneği</a> ( <a href="https://next-blog-agilitycms.vercel.app/" class="absolute" target="_blank" rel="noopener noreferrer">Demo</a>)
  </li>
  <li>
    <a href="https://github.com/vercel/next.js/tree/canary/examples/cms-cosmic" class="absolute" target="_blank" rel="noopener noreferrer">Cosmic Örneği</a> ( <a href="https://next-blog-cosmic.vercel.app/" class="absolute" target="_blank" rel="noopener noreferrer">Demo</a>)
  </li>
  <li>
    <a href="https://github.com/vercel/next.js/tree/canary/examples/cms-buttercms" class="absolute" target="_blank" rel="noopener noreferrer">ButterCMS Örneği</a> ( <a href="https://next-blog-buttercms.vercel.app/" class="absolute" target="_blank" rel="noopener noreferrer">Demo</a>)
  </li>
  <li>
    <a href="https://github.com/vercel/next.js/tree/canary/examples/cms-storyblok" class="absolute" target="_blank" rel="noopener noreferrer">Storyblok Örneği</a> ( <a href="https://next-blog-storyblok.vercel.app/" class="absolute" target="_blank" rel="noopener noreferrer">Demo</a>)
  </li>
  <li>
    <a href="https://github.com/vercel/next.js/tree/canary/examples/cms-graphcms" class="absolute" target="_blank" rel="noopener noreferrer">GraphCMS Örneği</a> ( <a href="https://next-blog-graphcms.vercel.app/" class="absolute" target="_blank" rel="noopener noreferrer">Demo</a>)
  </li>
  <li>
    <a href="https://github.com/vercel/next.js/tree/canary/examples/cms-kontent" class="absolute" target="_blank" rel="noopener noreferrer">Kontent Örneği</a> ( <a href="https://next-blog-kontent.vercel.app/" class="absolute" target="_blank" rel="noopener noreferrer">Demo</a>)
  </li>
  <li>
    <a href="https://github.com/vercel/next.js/tree/canary/examples/cms-builder-io" class="absolute" target="_blank" rel="noopener noreferrer">Builder.io Örneği</a> ( <a href="https://cms-builder-io.vercel.app/" class="absolute" target="_blank" rel="noopener noreferrer">Demo</a>)
  </li>
  <li>
    <a href="https://github.com/vercel/next.js/tree/canary/examples/cms-tina" class="absolute" target="_blank" rel="noopener noreferrer">TinaCMS Örneği</a> ( <a href="https://cms-tina-example.vercel.app/" class="absolute" target="_blank" rel="noopener noreferrer">Demo</a>)
  </li>
  <li>
    <a href="https://static-tweet.vercel.app/" class="absolute" target="_blank" rel="noopener noreferrer">Static Tweet (Demo)</a>
  </li>
</ul>
</details>

Eğer **Statik Generation** kullanıyorsanız HTML **build yaptığınız zaman** oluşturulur. Yani production ortamında `next build` komutunu çalıştırdığınızda sayfanın HTML halini oluşturmuş olursunuz. Bu oluşturulan HTML her istekte yeniden kullanılır ve CDN ile cachelenir.

Next.js'de datanız olsun veya olmasın sayfaları statik olarak oluşturabilirsiniz. Şimdi her iki duruma da bakalım.

#### Data ile Static Generation

Pre-rendering için bazı sayfaların data fetch işlemi yapması gerekir. Burada iki senaryo vardır ve bu iki senaryonun birisi ve ikisi birden de aynı anda olabilir. Her durumda, Next.js'in sağladığı şu fonksiyonları kullanabilirsiniz: 

1. Sayfanız gelen datadan **içeriğe** bağlı olabilir: Bu durumda `getStaticProps` kullanınız.
2. Sayfanız gelen dataya göre **url uzantısı** oluşturabilir. Bu durumda `getStaticPaths` kullanınız. (genellikle `getStaticProps` ile birlikte kullanılır. )



#### Senaryo 1: Sayfanız gelen datadaki içeriğe bağlı

**Örnek:** Blog sayfanız bir CMS (*Content Management System - İçerik Yönetim Sistemi*) üzerinden blog yazılarını listlemek için fetch işlemine ihtiyaç duyabilir.

```jsx 
// TODO: Bu sayfanın pre-render yapabilmesi için `posts` datasının
//       bir API'den gelmesi gerekiyor.

function Blog({ posts }) {
  return (
    <ul>
      {posts.map((post) => (
        <li>{post.title}</li>
      ))}
    </ul>
  )
}

export default Blog
```

Next.js pre-render için gerekli olan datayı fetch edebilmek için aynı dosyada `getStaticProps` isimli bir  edilebilir `async` fonksiyonda fetch işlemini yapmaya izin verir. Bu fonksiyon build zamanında çağrılır ve fetch işleminden gelen datayı `props` olarak sayfaya basar.

```jsx
function Blog({ posts }) {
  // Render posts...
}

// Bu fonksiyon build zamanında çağrılır
export async function getStaticProps() {
  // Bir API'den fetch işlemi yapılır
  const res = await fetch('https://.../posts')
  const posts = await res.json()

  // return { props: { posts } } ile, yukarıdaki Blog componentine
  // build zamanında posts içeriğide prop olarak gönderilir.
  return {
    props: {
      posts,
    },
  }
}

export default Blog
```

`getStaticProps`'un nasıl çalıştığıyla ilgili daha fazla bilgi için [Data Fetching](https://github.com/BurakGur/nextjs-turkce-dokuman#client-tarafında-data-fetch) dökümanına göz atabilirsiniz.


