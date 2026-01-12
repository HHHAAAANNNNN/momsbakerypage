# 🥖 Mom's Bakery - Landing Page

[![Deploy to GitHub Pages](https://github.com/HHHAAAANNNNN/momsbakerypage/actions/workflows/deploy.yml/badge.svg)](https://github.com/HHHAAAANNNNN/momsbakerypage/actions/workflows/deploy.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A modern, responsive landing page for Mom's Bakery (Aroma Wangi Brownies Tape) - showcasing artisan bread, pastries, and local specialty products. Built with Vue 3 and Vite for optimal performance and user experience.

## 🌟 Features

- **Responsive Design**: Fully responsive layout optimized for desktop, tablet, and mobile devices
- **Modern UI/UX**: Clean, intuitive interface with smooth animations and transitions
- **Product Showcase**: Interactive product sliders featuring bread, pastries, and specialty items
- **Location Integration**: Embedded map for easy store location finding
- **Customer Testimonials**: Dedicated section for customer reviews and feedback
- **SEO Optimized**: Structured with proper meta tags and semantic HTML for better search engine visibility
- **Fast Performance**: Built with Vite for lightning-fast development and optimized production builds
- **Automatic Deployment**: CI/CD pipeline with GitHub Actions for seamless updates

## 🚀 Live Demo

Visit the live site: [Mom's Bakery Landing Page](https://hhhaaaannnnn.github.io/momsbakerypage/)

## 🛠️ Technology Stack

- **Framework**: [Vue 3](https://vuejs.org/) - Progressive JavaScript framework
- **Build Tool**: [Vite](https://vitejs.dev/) - Next generation frontend tooling
- **State Management**: [Pinia](https://pinia.vuejs.org/) - The Vue Store
- **Routing**: [Vue Router](https://router.vuejs.org/) - Official router for Vue.js
- **Styling**: CSS3 with custom design system
- **Icons**: [Lucide React](https://lucide.dev/) - Beautiful & consistent icons
- **Utilities**: 
  - `class-variance-authority` - For component variants
  - `clsx` & `tailwind-merge` - For className management
- **Code Quality**:
  - ESLint - JavaScript linting
  - Prettier - Code formatting

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js**: `^20.19.0` or `>=22.12.0` (LTS recommended)
- **npm**: Comes with Node.js (or use yarn/pnpm as alternative)

## 🏁 Getting Started

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/HHHAAAANNNNN/momsbakerypage.git
   cd momsbakerypage
   ```

2. **Navigate to the frontend directory**
   ```bash
   cd moms-bakery-frontend
   ```

3. **Install dependencies**
   ```bash
   npm install
   ```

### Development

Start the development server with hot-reload:

```bash
npm run dev
```

The application will be available at `http://localhost:5173` (or the next available port).

### Building for Production

Create an optimized production build:

```bash
npm run build
```

The built files will be in the `dist/` directory.

### Preview Production Build

Preview the production build locally:

```bash
npm run preview
```

### Code Quality

Lint and fix code issues:

```bash
npm run lint
```

Format code with Prettier:

```bash
npm run format
```

## 📁 Project Structure

```
momsbakerypage/
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Actions deployment workflow
├── moms-bakery-frontend/       # Main Vue application
│   ├── public/                 # Static assets
│   ├── src/
│   │   ├── assets/            # Images, fonts, and other assets
│   │   ├── components/        # Vue components
│   │   │   ├── GooeyNav.vue       # Navigation component
│   │   │   ├── HeroSection.vue    # Hero/banner section
│   │   │   ├── ProductSection.vue # Product showcase
│   │   │   ├── TestimoniSection.vue # Customer testimonials
│   │   │   ├── LokasiSection.vue  # Location/contact info
│   │   │   └── FooterSection.vue  # Footer
│   │   ├── router/            # Vue Router configuration
│   │   ├── stores/            # Pinia state management
│   │   ├── App.vue            # Root component
│   │   └── main.js            # Application entry point
│   ├── index.html             # HTML template
│   ├── vite.config.js         # Vite configuration
│   └── package.json           # Dependencies and scripts
└── README.md                  # This file
```

## 🔧 Configuration

### Base Path for GitHub Pages

The application is configured to work with GitHub Pages. The base path is set in `vite.config.js`:

```javascript
export default defineConfig({
  base: '/momsbakerypage/',
  // ... other config
})
```

If deploying to a different platform, adjust the `base` path accordingly.

### Router Configuration

The application uses hash mode for GitHub Pages compatibility. This is configured in the router setup.

## 🚢 Deployment

### Automatic Deployment (GitHub Pages)

This project is configured with GitHub Actions for automatic deployment:

1. Push changes to the `main` branch
2. GitHub Actions automatically builds and deploys the site
3. Site is available at: `https://hhhaaaannnnn.github.io/momsbakerypage/`

The workflow file is located at `.github/workflows/deploy.yml`.

### Manual Deployment

#### Deploy to GitHub Pages Manually

```bash
cd moms-bakery-frontend
npm run build
# Deploy the dist/ folder to GitHub Pages branch
```

#### Deploy to Other Platforms

- **Netlify**: Connect your repository and set build command to `npm run build` (in moms-bakery-frontend directory)
- **Vercel**: Import the project and configure the root directory to `moms-bakery-frontend`
- **Traditional Hosting**: Upload the contents of the `dist/` folder to your web server

## 🎨 Customization

### Updating Content

The application uses component-based architecture. To update content:

1. **Products**: Edit `ProductSection.vue` component
2. **Testimonials**: Edit `TestimoniSection.vue` component
3. **Location**: Edit `LokasiSection.vue` component
4. **Contact Info**: Edit `FooterSection.vue` component

### Styling

The project uses a custom color scheme with a warm, bakery-themed palette:
- Primary background: `#FFF8F0` (Warm cream)
- Custom animations and transitions throughout

Global styles are defined in `App.vue` and individual component styles.

### Adding New Sections

1. Create a new Vue component in `src/components/`
2. Import and use it in `App.vue`
3. Follow the existing component structure for consistency

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Make your changes**
4. **Commit your changes**
   ```bash
   git commit -m 'Add some amazing feature'
   ```
5. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
6. **Open a Pull Request**

### Development Guidelines

- Follow the existing code style and conventions
- Run `npm run lint` before committing
- Test your changes on multiple screen sizes
- Update documentation if needed
- Write clear commit messages

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Authors

- **HHHAAAANNNNN** - *Initial work* - [GitHub Profile](https://github.com/HHHAAAANNNNN)

## 🙏 Acknowledgments

- Built with [Vue 3](https://vuejs.org/) and [Vite](https://vitejs.dev/)
- Icons from [Lucide](https://lucide.dev/)
- Fonts from [Google Fonts](https://fonts.google.com/) (Playfair Display & Quicksand)

## 📞 Support

For support, questions, or feedback:
- Open an issue on [GitHub Issues](https://github.com/HHHAAAANNNNN/momsbakerypage/issues)
- Contact the repository owner

## 🗺️ Roadmap

Future enhancements planned:
- [ ] Online ordering system integration
- [ ] Admin panel for content management
- [ ] Multi-language support (Indonesian/English)
- [ ] Blog section for recipes and bakery news
- [ ] Customer account system
- [ ] Real-time inventory updates
- [ ] Payment gateway integration

---

Made with ❤️ for Mom's Bakery - Bringing the aroma of fresh brownies to your digital experience!
