# authentik-frosted-theme

Authentik Frosted Glass Theme

Please open issues if you find any visual bugs!

Download theme.css, copy content and paste into 
Admin Dashboard -> System -> Brands -> Authentik Default OR create a new brand under your domain -> Branding settings -> Custom CSS field

then go to your brand, scroll down to Atrributes and paste this:

```yaml
settings:
  theme:
    base: dark
    background: >
      background:
        radial-gradient(circle at 15% 10%, rgba(62, 132, 180, 0.16), transparent 35%),
        radial-gradient(circle at 85% 85%, rgba(72, 79, 112, 0.12), transparent 35%),
        linear-gradient(135deg, #05070b 0%, #0a1018 55%, #080b10 100%);
      background-attachment: fixed;
  layout:
    type: 3-column
  navbar:
    userDisplay: name
  enabledFeatures:
    search: true
    settings: true
    apiDrawer: false
    applicationEdit: false
    notificationDrawer: false
```

Then, in Admin Interface -> Flow & Stages -> Flows -> `default-authentication-flow` -> EDIT BUTTON -> Appearance settings -> Layout -> Choose "Stacked"

Tested on Authentik version 2026.5.6


Theme Preview:

<img width="2966" height="1824" alt="brave_H0tyn4BaHI" src="https://github.com/user-attachments/assets/a960040f-3d8c-4e75-b4c4-de0848ab8721" />

<img width="2966" height="1824" alt="brave_oodQBL4ufc" src="https://github.com/user-attachments/assets/292d8c0f-6955-4ba7-8301-f7900ddcb8ac" />

<img width="1483" height="912" alt="jk2Pbh3YPu" src="https://github.com/user-attachments/assets/020dc1e7-91fd-4cab-99ba-af4f89c6b988" />

<img width="1483" height="912" alt="DXOXsdSNEd" src="https://github.com/user-attachments/assets/d2b07c31-5b5f-4f65-81b6-b94f580c7307" />

<img width="1483" height="912" alt="brave_F0PP5Ggwpe" src="https://github.com/user-attachments/assets/2ea19eb6-4132-4684-bad2-a42ae1240dba" />
