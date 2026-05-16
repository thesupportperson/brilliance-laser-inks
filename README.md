# Brilliance Laser Inks — Homepage Clone

A static HTML clone of [brilliancelaserinks.com](https://brilliancelaserinks.com/) built for VPS hosting.

## Features

- Responsive design (mobile + desktop)
- Sticky header with mobile hamburger menu
- Announcement bar, Hero, Collections, Best Sellers, Gallery, Reviews, About, Footer sections
- GHL / LeadConnector chat widget embedded (lower right)
- Zero dependencies — single `index.html` file
- All images loaded from Brilliance CDN

## Hosting on VPS

### Option 1: Nginx
```bash
git clone https://github.com/thesupportperson/brilliance-laser-inks.git
cd brilliance-laser-inks
sudo cp index.html /var/www/html/index.html
sudo systemctl restart nginx
```

### Option 2: Python (quick test)
```bash
git clone https://github.com/thesupportperson/brilliance-laser-inks.git
cd brilliance-laser-inks
python3 -m http.server 8080
```

### Option 3: Node.js serve
```bash
npm install -g serve
git clone https://github.com/thesupportperson/brilliance-laser-inks.git
cd brilliance-laser-inks
serve . -p 80
```

## Chat Widget

The GHL LeadConnector chat widget is embedded with widget ID `6a043a630d6444dd882c6b05` and appears in the lower-right corner of the page.
