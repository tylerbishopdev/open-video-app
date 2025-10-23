# Open.Video App - Setup Guide

## Project Successfully Created!

Your Vue 3 application with Tailwind CSS and shadcn-vue has been set up and is working.

## Current Status

- Vue 3 with TypeScript
- Tailwind CSS v4 configured
- shadcn-vue dependencies installed
- Carousel component created with Embla Carousel
- Main page layout matching your screenshot

## What's Working

1. **Layout**: Matches your screenshot with:
   - Fixed background image support
   - Open.Video logo in header
   - Large "SearchCreatorChannels" heading with cyan/white colors
   - Search bar with icon
   - Left navigation menu (Featured Channels, My Channel, Studio, About, Terms, Privacy)
   - Carousel for featured creators

2. **Build**: Successfully compiles without errors

3. **Dev Server**: Runs on http://localhost:5173/

## Next Steps - IMPORTANT

### 1. Add Your Background Image

Replace the placeholder at:
```
/Users/shibasafe/EzoicProject/open-video-app/public/background.jpg
```

With your actual background image (the photographer with camera image you showed).

### 2. Add Featured Creator Images

Update the carousel items in `/Users/shibasafe/EzoicProject/open-video-app/src/App.vue` (lines 17-48):

Replace the placeholder image URLs with your actual creator images:
```typescript
const carouselItems = [
  {
    id: 1,
    title: '@2StrawsMMA',  // Update with actual creator name
    image: '/path/to/creator1.jpg',  // Add your creator images to /public
    url: 'https://...'  // Update with actual URL
  },
  // ... add more creators
]
```

### 3. Customize Colors (Optional)

The current colors match your screenshot:
- Cyan (#67e8f9 / text-cyan-300) for "Search" and "Channels"
- White for "Creator"
- Blue gradient background overlay

To adjust, edit the Tailwind classes in `App.vue`.

## Running the Project

```bash
cd open-video-app

# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## Project Structure

```
open-video-app/
├── src/
│   ├── components/
│   │   └── Carousel.vue       # Embla Carousel component
│   ├── lib/
│   │   └── utils.ts           # Utility functions (cn helper)
│   ├── App.vue                # Main page component
│   └── style.css              # Tailwind CSS imports
├── public/
│   └── background.jpg         # Background image (ADD YOUR IMAGE HERE)
└── package.json
```

## Dependencies Installed

- **Vue 3** - Core framework
- **Tailwind CSS v4** - Styling
- **Embla Carousel** - Carousel functionality
- **Radix Vue** - Headless UI components
- **Lucide Vue** - Icons (Search, Menu, ChevronLeft, ChevronRight)
- **class-variance-authority** - Variant management
- **clsx & tailwind-merge** - Class name utilities

## Customization Tips

1. **Menu Items**: Update `menuItems` array in `App.vue` (lines 7-14)
2. **Carousel Settings**: Adjust in `Carousel.vue` (lines 18-24)
3. **Responsive**: The layout is responsive with mobile menu toggle
4. **Animations**: Carousel has autoplay with 3-second intervals

## Notes

- The carousel uses Embla Carousel with autoplay
- Background image is fixed position and fills the screen
- All Tailwind utilities are available
- TypeScript is configured and working
- Production build is optimized and ready

Open http://localhost:5173/ in your browser after running `npm run dev` to see your application!
