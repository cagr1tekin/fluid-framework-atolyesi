# Bug App — React + Tailwind (Feature-Based)


## Kurulum

```bash
cd bug-app-react
npm install
npm run dev
```

Tarayıcı `http://localhost:5173` adresinde açılır.

## Klasör Yapısı

```
bug-app-react/
├── index.html
├── src/
│   ├── main.jsx              # entry
│   ├── index.css             # Tailwind directives
│   ├── App.jsx               # state + ctx + layout kompozisyonu
│   ├── routes.js             # page id → component map
│   │
│   ├── shared/
│   │   ├── icons/
│   │   │   ├── Icon.jsx
│   │   │   └── iconPaths.jsx
│   │   ├── data/
│   │   │   ├── nav.js        # Sidebar NAV
│   │   │   └── sampleData.js # SAMPLE_USERS, LONG_WORD, LONG_URL
│   │   ├── components/
│   │   │   ├── Avatar.jsx
│   │   │   ├── PageHeader.jsx
│   │   │   ├── Sidebar.jsx
│   │   │   ├── TopBar.jsx
│   │   │   └── Footer.jsx
│   │   └── feedback/
│   │       ├── Modal.jsx     # DeleteModal + EditModal
│   │       └── Toast.jsx     # ToastStack
│   │
│   └── features/
│       ├── home/             HomePage.jsx
│       ├── feed/             FeedPage.jsx
│       ├── notifications/    NotificationsPage.jsx
│       ├── messaging/        MessagesPage.jsx, ConversationPage.jsx
│       ├── workshops/        WorkshopsPage, WorkshopDetailPage, WorkshopCreatePage
│       ├── events/           CalendarPage, EventDetailPage
│       ├── mentors/          MentorsPage, MentorDetailPage, MentorApplyPage
│       ├── resources/        ResourcesPage, ResourceDetailPage
│       ├── profile/          ProfilePage, ProfileEditPage, LikesPage, MyCommentsPage
│       ├── settings/         SettingsAccountPage, ...Notifications, ...Privacy, ...Billing
│       └── company/          AboutPage, CareersPage, ContactPage, BlogPage, BlogPostPage, HelpPage, FaqPage
```

## Mimari Notları

- **Feature-based:** Her sayfa kendi feature klasöründe yaşar; ortak parçalar `shared/` altında.
- **State yönetimi:** Tüm global state `App.jsx` içinde tutulur, sayfalara `ctx` prop'u olarak iner. Hızlı atölye iterasyonu için kasıtlı olarak basit tutuldu (Redux/Context yok).
- **Routing:** `useState("home")` + `routes.js` map. Bug'ların component sınırlarında daha okunaklı olması için tercih edildi.
- **Tailwind:** Standart Tailwind 3 kurulumu (PostCSS + autoprefixer). Tailwind v4 farklılığı arayanlar `tailwind.config.js`'i v4'e geçirip karşılaştırabilir.

