# Kaya Furniture Website

A simple, fast, mobile-friendly website for **Kaya Furniture**. It shows 99 furniture designs across 8 categories and sends customer enquiries straight to WhatsApp.

## Features

- Hero section, category tiles and a filterable photo gallery
- 8 categories: Kitchen, Beds, Center tables, Home furniture, Office furniture, TV racks, Vanity tables, Wardrobes
- Full-screen photo viewer (click a photo; use the arrow keys or on-screen buttons; press Esc to close)
- Floating **WhatsApp us** button and an enquiry form (name, phone, what they need, details) that opens WhatsApp with a neatly formatted message, including who sent it and when
- Fully responsive: phone menu (hamburger), 2-column gallery on phones, swipe left/right in the photo viewer, safe-area support for notched phones, and wider layouts on large screens
- Plain HTML, CSS and JavaScript. No build step, no frameworks

## Folder structure

```
kaya-furniture/
├── index.html    Page content and the JavaScript (gallery, filters, WhatsApp)
├── style.css     All styling
├── fonts/        Bangers font (used for the KAYA logo only)
├── images/       Furniture photos, named category-number.jpg
└── README.md
```

## Run it locally

1. Keep `index.html`, `style.css` and the `images` folder together in one folder.
2. Double-click `index.html` to open it in your browser.

The fonts (Young Serif and Figtree) load from Google Fonts, so an internet connection is needed to see them. Without it, the site falls back to system fonts.

## Change the contact details

Open `index.html` and update:

| What | Where to look |
| --- | --- |
| WhatsApp number | `const PHONE="+91 7903702075";` near the bottom (country code first, no `+` or spaces) |
| Number shown on the page | The "Phone / WhatsApp" block in the Contact section (also update the `wa.me` link there) |
| Instagram link | `const IG_URL="https://www.instagram.com/kayafurniture_07?stkn=ZGtta2plYW00ZTJs";` near the bottom (this is the Instagram icon in the footer) |
| Showroom address | The "Showroom" block in the Contact section |
| Opening hours | The "Hours" block in the Contact section |

## Add or remove photos

1. Put the new photo in `images/` and name it with its category first, for example `kitchen-101.jpg`.
2. In `index.html`, find the list that starts with `const D=[` and add a line in the same format:
   ```js
   ["kitchen-101.jpg", "kitchen"]
   ```
3. To remove a photo, delete its entry from that list and delete the file from `images/`.

Category keys: `kitchen`, `bed`, `center`, `home`, `office`, `tv`, `vanity`, `wardrobe`.

Tip: keep photos under about 1100 px wide and around 100 KB each so the site loads quickly on mobile data.

## Add a new category

1. Add it to the `CATS` object in `index.html`, for example `sofa:"Sofas"`.
2. Add photos with that key in the `D` list.

The category tile, filter chip and enquiry dropdown are created automatically.

## Change colors and fonts

All colors are at the top of `style.css` under `:root`:

```css
--bg:#0B2A17;    /* page background (logo green) */
--bg2:#0F3A20;   /* cards and alternate sections */
--pill:#1F5A36;  /* logo pill green */
--lime:#B2C73B;  /* logo outline, buttons, highlights */
--ink:#EDF2E7;   /* main text */
```

Fonts are set in the `<link>` tag in `index.html` and in `style.css`.

## Put it online

The site is static, so any free static host works:

- **Netlify:** drag and drop the whole `kaya-furniture` folder at app.netlify.com/drop
- **GitHub Pages:** upload the folder to a repository and turn on Pages in the settings
- **Any web hosting:** upload the folder contents to `public_html`

## Notes

- The logo is built in code (Bangers font, green pill with a lime outline). Swap it for your image logo anytime in the `.logo` link at the top of `index.html`.
- Some photos may carry faint watermarks from their original source. Replace them with your own work photos when you have them.
- The enquiry form does not store anything. It only opens WhatsApp with the message ready to send.