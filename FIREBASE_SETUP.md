# Firebase setup ya KOLONGO

Programu hii ni static website ya GitHub Pages. Ili data ihifadhiwe kwenye Firebase badala ya kifaa kimoja, weka Firebase Web App config kwenye `index.html`, sehemu ya `const firebaseConfig`.

## Hatua

1. Fungua [Firebase Console](https://console.firebase.google.com/).
2. Tengeneza au chagua project.
3. Fungua **Project settings → Your apps → Web app**.
4. Copy object ya **Firebase SDK configuration**.
5. Badilisha values za `WEKA_*` kwenye `index.html`:

```js
const firebaseConfig = {
  apiKey: "...",
  authDomain: "project-id.firebaseapp.com",
  databaseURL: "https://project-id-default-rtdb.firebaseio.com",
  projectId: "project-id",
  storageBucket: "project-id.firebasestorage.app",
  messagingSenderId: "...",
  appId: "..."
};
```

6. Kwenye Firebase Console fungua **Realtime Database**, tengeneza database, kisha hakikisha rules zako zimeruhusu matumizi salama ya programu.
7. Fanya deploy tena kupitia **Settings → Pages** baada ya kuhifadhi mabadiliko.

## Muhimu

- Firebase config ya Web App si private key; usiweke service-account JSON au private key kwenye GitHub Pages.
- Bila config halisi, `index.html` hutumia `localStorage` kwa makusudi. Hii inamaanisha data inabaki kwenye browser/kifaa hicho tu.
- Usitumie database rules za `read, write: true` kwenye mfumo wa production bila authentication.
