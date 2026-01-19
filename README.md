# E-Commerce UI

Admin Panel ve Müşteri (Client) uygulamasından oluşan e-ticaret monoreposu.

---

## Proje Yapısı

- **admin/** — Yönetim paneli
  - Ürünler, kullanıcılar, ödemeler
  - Grafikler, tablolar, CRUD formları
- **client/** — Müşteri arayüzü
  - Ürün listesi, sepet, kargo ve ödeme formları

---

## Teknolojiler

### Ortak (Admin + Client)

- Next.js 15 (App Router, Turbopack)
- React 19
- TypeScript 5
- Tailwind CSS 4
- pnpm

### Admin

- **shadcn/ui** (New York)
  - Radix UI primitifleri: Avatar, Checkbox, Dialog, Dropdown, Label, Popover, Progress, Scroll Area, Select, Separator, Tooltip, Collapsible
  - Bileşenler: `@/components/ui` (avatar, badge, button, card, chart, form, table, sidebar, select, popover, input, textarea vb.)
- **TanStack React Table** — sıralama, sayfalama, satır seçimi
- **Recharts** — AreaChart, BarChart, LineChart, PieChart
- **react-hook-form** + **Zod** + **@hookform/resolvers** — form ve validasyon
- **date-fns** + **react-day-picker** — tarih seçimi
- **next-themes** — açık/koyu tema
- **Lucide React** — ikonlar
- **tw-animate-css** — animasyonlar
- **CVA** (class-variance-authority) — bileşen varyantları
- **clsx** + **tailwind-merge** — `cn()` ile sınıf birleştirme (`lib/utils.ts`)

### Client

- **Zustand** — sepet state; `persist` + `localStorage`
- **react-hook-form** + **Zod** + **@hookform/resolvers** — kargo ve ödeme formları
- **react-toastify** — bildirimler
- **Lucide React** — ikonlar  
  *(shadcn yok; arayüz Tailwind ile özel bileşenler.)*

---

## Çalıştırma

```bash
# Admin
cd admin && pnpm install && pnpm dev

# Client
cd client && pnpm install && pnpm dev
```

Turbopack ile Next.js dev sunucusu açılır.

---

## Özellikler

**Admin**

- Ürün, kullanıcı, ödeme tabloları
- CRUD formları (ürün, kullanıcı, kategori, sipariş)
- Grafikler (alan, çubuk, çizgi, pasta)
- Sidebar, tema değiştirme

**Client**

- Ürün listesi, filtreleme, arama
- Sepet (Zustand + localStorage)
- Kargo formu, ödeme formu

---

## Konfigürasyon

- Admin `next.config`: Pexels (`images.pexels.com`) için `remotePatterns`
- ESLint: `eslint-config-next`
- Tailwind 4: `postcss.config.mjs` ile `@tailwindcss/postcss`
