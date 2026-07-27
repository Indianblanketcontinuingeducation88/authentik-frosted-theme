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

After that go to **Flows and Stages → Stages**.

Open **Password Stages**.

Edit the Password stage used by the authentication flow, commonly named something like:

```text
default-authentication-password
```

Configure the required password backends, normally at least:

```text
User database + standard password
```

Enable **Allow show password**

Save the stage.

Open **Flows and Stages → Stages**.

Open **Identification Stages**.

Edit the Identification stage used at the beginning of the authentication flow, commonly:

```text
default-authentication-identification
```

Set **User fields** to:

```text
Username
Email
```

Set **Password stage** to the Password stage configured in the previous section.

Enable:

```text
Enable remember me on this device
```

Set **WebAuthn Authenticator Validation stage** to a validation stage that allows WebAuthn devices.

Save the stage.

Open **Flows and Stages → Flows**.

Open the authentication flow used by the Brand.

Open **Stage Bindings**.

Keep the Identification stage as the first normal authentication step.

Remove or disable the separately bound Password stage.

Keep any required Authenticator Validation/MFA stage after identification.

Keep the User Login stage as the final stage.

Open **Flows and Stages → Stages**.

Open **Authenticator Validation Stages**.

Edit an existing validation stage or create a dedicated one.

Ensure **Device classes** includes:

```text
WebAuthn
```

use

```text
WebAuthn user verification: Required
```

Save the stage.

Return to the Identification stage and select this stage under:

```text
WebAuthn Authenticator Validation stage
```

Edit the WebAuthn/FIDO2 authenticator setup stage and configure:

```text
Resident key requirement: Preferred or Required
User verification: Required
Authenticator attachment: Unset / no restriction
```

Tested on Authentik version 2026.5.6


Theme Preview:

<img width="2966" height="1824" alt="brave_H0tyn4BaHI" src="https://github.com/user-attachments/assets/a960040f-3d8c-4e75-b4c4-de0848ab8721" />

<img width="2966" height="1824" alt="brave_oodQBL4ufc" src="https://github.com/user-attachments/assets/292d8c0f-6955-4ba7-8301-f7900ddcb8ac" />

<img width="1483" height="912" alt="jk2Pbh3YPu" src="https://github.com/user-attachments/assets/020dc1e7-91fd-4cab-99ba-af4f89c6b988" />

<img width="1483" height="912" alt="DXOXsdSNEd" src="https://github.com/user-attachments/assets/d2b07c31-5b5f-4f65-81b6-b94f580c7307" />

<img width="1483" height="912" alt="brave_F0PP5Ggwpe" src="https://github.com/user-attachments/assets/2ea19eb6-4132-4684-bad2-a42ae1240dba" />
