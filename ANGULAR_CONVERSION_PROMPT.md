# Angular Frontend Conversion Prompt

## Project Overview
Convert a Veterinary Platform multi-page HTML/CSS/JavaScript website into a modern Angular frontend application. The current implementation is a single HTML file with embedded CSS and vanilla JavaScript containing multiple pages and interactive features.

## Website Content & Page Structure

### **Home Page Content**
1. **Hero Section**
   - Tagline: "New Formula 2025"
   - Main title: "Premium Veterinary Medicines"
   - Subtitle: "Trusted by vets across 30+ countries. Lab-tested formulas for livestock, poultry and companion animals."
   - CTA button: "Explore Products →"
   - Animated emoji (🧪) on right side
   - Hero pagination dots (3 dots)

2. **Categories Section**
   - Title: "Browse by Category" / "Our Product Lines"
   - 4 category cards in grid:
     - Compound Mix (with custom SVG icon)
     - Liquid Solutions (with custom SVG icon)
     - Powder Formulas (with custom SVG icon)
     - Injectables (with custom SVG icon)
   - Each card: icon + name, hover effects

3. **Featured Liquid Products Section**
   - Title: "Featured | Liquid Products"
   - Subcategories: All Products, Vitamin & Mineral Liquids, Liver & Detox Liquids, Electrolyte Solutions, Immune Support Liquids
   - 20 liquid products in carousel (5 pages × 4 cards each)
   - Arrow navigation + 5 pagination dots
   - Products: VitaLiquid Forte Plus, Hepato Care Solution, Electro Balance Mix, Immuno Boost Oral (repeated)

4. **Featured Powder Formulas Section**
   - Title: "Featured | Powder Formulas"
   - Subcategories: All Products, Growth & Performance Powders, Mineral & Calcium Powders, Probiotic Powders, Herbal & Digestive Powders
   - 16 powder products in carousel (4 pages × 4 cards each)
   - Arrow navigation + 4 pagination dots
   - Products: GrowMax Powder Pro, CalciPhos Mineral Blend, ProBio Active Plus, Herbal Digest Mix (repeated)

5. **Why Choose Us Section**
   - Title: "Our Promise" / "Why Choose Us"
   - 6 service cards in 3×2 grid:
     - Lab Certified (🔬)
     - Global Reach (🌍)
     - Multi-Species (🐄)
     - GMP Facility (🏭)
     - Flexible Packaging (📦)
     - Expert Support (🤝)

6. **Certifications Section**
   - Title: "Certified By" / "Our Certifications"
   - 4 certification cards with SVG logos
   - Description: "International farm supply chain covering 15+ markets globally."

### **Products Page Content**
- Breadcrumb: Home › Products
- Title: "All Categories" / "Product Catalogue"
- Category filter buttons: All Products, Compound Mix, Liquid, Powder
- Product grid (4 columns): 12 products total
- Products include: VitaLiquid Forte Plus, Hepato Care Solution, Electro Balance Mix, Immuno Boost Oral, GrowMax Powder Pro, CalciPhos Mineral Blend, ProBio Active Plus, Herbal Digest Mix, MultiVit Compound A, AminoFlex Blend Pro, TraceMix Ultra, OralCare Liquid Plus

### **Product Detail Page Content**
- Breadcrumb: Home › Products › Liquid › [Product Name]
- Product layout: Image left, details right
- Product info: Name, category pill, description, specifications table
- Animal usage section: Poultry, Cattle, Sheep with benefits lists
- Why choose section with benefits cards
- Related products carousel (4 products)
- Partnerships section at bottom

### **About Page Content**
- Breadcrumb: Home › About Us
- Hero section: "Our Story" / "Who We Are" with company description
- Stats section: 6 stat cards (Employees, Countries, Facility size, Products, Experience, Certifications)
- Standards section: ISO Certified, In-House R&D Lab, Sustainable Practices
- Partners section: 4 partner cards

### **Contact Page Content**
- Breadcrumb: Home › Contact
- Two-column layout:
  - **Left**: Contact info (Address, Phone, Email, Hours, Social media, Map placeholder)
  - **Right**: Contact form (Name*, Email*, Phone, Country, Product, Message*, Submit button)
- Prefill banner for products from favorites
- Success message after submission

### **Shared Components Content**
- **Navbar**: Logo, navigation links, product dropdown, search button, favorites button
- **Search Overlay**: Search input, popular chips, close functionality
- **Favorites Drawer**: Product list with images, quantity controls, contact button
- **Footer**: Company info, contact details, social links, copyright

---

## Project Structure Requirements

### Directory Structure
```
src/
├── app/
│   ├── shared/
│   │   ├── components/
│   │   │   ├── navbar/
│   │   │   ├── search-overlay/
│   │   │   ├── favorites-drawer/
│   │   │   ├── slider-carousel/
│   │   │   ├── pagination-dots/
│   │   │   ├── section-header/
│   │   │   ├── button/
│   │   │   ├── category-filter/
│   │   │   ├── product-card/
│   │   │   └── footer/
│   │   ├── services/
│   │   │   ├── product.service.ts
│   │   │   ├── favorites.service.ts
│   │   │   ├── navigation.service.ts
│   │   │   └── search.service.ts
│   │   ├── models/
│   │   │   ├── product.model.ts
│   │   │   ├── category.model.ts
│   │   │   ├── favorite.model.ts
│   │   │   └── navigation.model.ts
│   │   └── styles/
│   │       ├── variables.scss
│   │       ├── utilities.scss
│   │       └── theme.scss
│   ├── pages/
│   │   ├── home/
│   │   │   ├── home.component.ts|html|scss
│   │   │   ├── hero-section/
│   │   │   ├── categories-section/
│   │   │   ├── featured-liquid-section/
│   │   │   ├── featured-powder-section/
│   │   │   ├── why-choose-section/
│   │   │   └── certifications-section/
│   │   ├── products/
│   │   │   ├── products.component.ts|html|scss
│   │   │   └── product-filter-section/
│   │   ├── about/
│   │   │   ├── about.component.ts|html|scss
│   │   │   ├── about-hero/
│   │   │   ├── animal-products-section/
│   │   │   └── benefits-section/
│   │   ├── contact/
│   │   │   ├── contact.component.ts|html|scss
│   │   │   ├── contact-form/
│   │   │   └── contact-info/
│   │   └── product-detail/
│   │       └── product-detail.component.ts|html|scss
│   ├── app.component.ts|html|scss
│   ├── app.module.ts
│   ├── app-routing.module.ts
│   └── app.config.ts (for standalone if using Angular 14+)
├── assets/
│   ├── images/
│   │   └── vet_imges/
│   ├── icons/
│   └── fonts/
├── styles/
│   └── global.scss
├── main.ts
├── index.html
└── environments/
```

---

## Components to Create (Reusable Shared Components)

### 1. **shared/components/navbar/navbar.component**
- **Inputs:** `currentPage: string`, `favoriteCount: number`
- **Outputs:** `pageChange: EventEmitter<string>`
- **Functionality:**
  - Display VetGroup logo with clickable navigation
  - Render navigation links with routing
  - Show product dropdown with subcategories (Liquid and Powder)
  - Search button (triggers search overlay)
  - Favorites button with badge showing count
  - Sticky positioning at top

### 2. **shared/components/search-overlay/search-overlay.component**
- **Inputs:** `isOpen: boolean`
- **Outputs:** `close: EventEmitter<void>`, `search: EventEmitter<string>`
- **Functionality:**
  - Fixed overlay with semi-transparent background
  - Search input field with placeholder
  - Display popular search chips (clickable)
  - Close on background click or button
  - Animated fade-in

### 3. **shared/components/favorites-drawer/favorites-drawer.component**
- **Inputs:** `favorites: Favorite[]`, `isOpen: boolean`
- **Outputs:** `close: EventEmitter<void>`, `updateQuantity: EventEmitter<{id: string, qty: number}>`, `removeFavorite: EventEmitter<string>`
- **Functionality:**
  - Slide-in drawer from right side
  - Display list of favorite products with images
  - Quantity +/- buttons
  - Remove button for each item
  - Summary showing product count
  - "Send Request via Contact Page" button
  - "Continue Browsing" button

### 4. **shared/components/slider-carousel/slider-carousel.component**
- **Inputs:** `items: any[]`, `itemsPerPage: number = 4`, `autoSlide: boolean = false`
- **Outputs:** `slideChange: EventEmitter<number>`
- **Functionality:**
  - Grid-based carousel with horizontal scroll
  - Previous/Next arrow buttons
  - Pagination dots
  - Smooth transform transitions
  - Support for different item counts per page
  - Responsive grid columns

### 5. **shared/components/pagination-dots/pagination-dots.component**
- **Inputs:** `totalDots: number`, `activeDot: number`
- **Outputs:** `dotClick: EventEmitter<number>`
- **Functionality:**
  - Display dots for slider pages
  - Highlight active dot
  - Clickable dot navigation
  - Smooth dot width animation on active state

### 6. **shared/components/section-header/section-header.component**
- **Inputs:** `label: string`, `title: string`, `subtitle?: string`
- **Outputs:** None
- **Functionality:**
  - Display section label (uppercase, small)
  - Display main title (large, bold)
  - Support for light-weight text in title
  - Consistent styling across sections

### 7. **shared/components/button/button.component**
- **Inputs:** `type: 'primary' | 'outline' | 'text'`, `size: 'sm' | 'md' | 'lg'`, `disabled: boolean`, `loading: boolean`, `icon?: string`
- **Outputs:** `click: EventEmitter<void>`
- **Functionality:**
  - Reusable button with different styles
  - Support for icons and loading state
  - Proper spacing and hover effects

### 8. **shared/components/category-filter/category-filter.component**
- **Inputs:** `categories: string[]`, `selectedCategory: string`
- **Outputs:** `categorySelect: EventEmitter<string>`
- **Functionality:**
  - Display category filter buttons
  - Toggle active state
  - Highlight selected category

### 9. **shared/components/product-card/product-card.component**
- **Inputs:** `product: Product`
- **Outputs:** `favoriteToggle: EventEmitter<Product>`, `click: EventEmitter<Product>`
- **Functionality:**
  - Display product image
  - Show product name
  - Display "READ MORE" button
  - Heart favorite button (toggle states: empty/filled)
  - Hover effects (shadow, translateY)
  - Clickable card for detail page

### 10. **shared/components/footer/footer.component**
- **Inputs:** None
- **Outputs:** None
- **Functionality:**
  - Display company info
  - Show contact details
  - Display social media links
  - Copyright notice
  - Company description
  - Links footer

---

## Page Components (Feature Components)

### 1. **pages/home/home.component**
Main landing page container with:
- HeroSection component
- CategoriesSection component
- FeaturedLiquidSection component
- FeaturedPowderSection component
- WhyChooseSection component
- CertificationsSection component

#### **home/hero-section/hero-section.component**
- Display gradient hero background
- Show main title with green highlights
- Display subtext
- Show animated emoji/illustration on right
- Display hero pagination dots
- Implement carousel-like behavior for hero content

#### **home/categories-section/categories-section.component**
- **Inputs:** `categories: Category[]`
- Display 3-column grid of categories
- Each category card: icon + name
- Hover effects (border color, shadow, transform)
- Click to navigate to products filtered by category

#### **home/featured-liquid-section/featured-liquid-section.component**
- **Inputs:** `liquidProducts: Product[]`, `liquidSubcategories: string[]`
- Display "Featured | Liquid Products" section
- Sub-category filter buttons (All Products, Vitamin & Mineral, Liver & Detox, Electrolyte, Immune Support)
- Use SliderCarousel component with 5 pages (4 products per page)
- Arrow navigation buttons
- Pagination dots (5 dots)
- Product cards using ProductCard component
- Filter subcategories with slider reset

#### **home/featured-powder-section/featured-powder-section.component**
- **Inputs:** `powderProducts: Product[]`, `powderSubcategories: string[]`
- Display "Featured | Powder Formulas" section
- Sub-category filter buttons (All Products, Growth & Performance, Mineral & Calcium, Probiotic, Herbal & Digestive)
- Use SliderCarousel component with 4 pages (4 products per page)
- Arrow navigation buttons
- Pagination dots (4 dots)
- Product cards using ProductCard component
- Same structure as liquid section

#### **home/why-choose-section/why-choose-section.component**
- Display 6 service cards in 3-column grid
- Each card: icon + title + description
- Services: Lab Certified, Global Reach, Multi-Species, GMP Facility, Flexible Packaging, Expert Support

#### **home/certifications-section/certifications-section.component**
- Display "Certified By" / "Our Certifications" section
- Show 4-column grid of certification cards
- Each card: logo/image + description
- Display: FARMPLUS, certifications, etc.

### 2. **pages/products/products.component**
- Display category filter buttons
- Display full product grid (4 columns)
- Filter products by category dynamically
- Display product cards using ProductCard component

### 3. **pages/about/about.component**
- Hero banner with title
- About layout with two columns:
  - Left: Text content (About Us, mission, vision)
  - Right: Logo/image area
- Statistics cards section (3-4 cards with numbers)
- Animal products section: 
  - Alternating layout (image left/right)
  - Animal name, benefits list
- Benefits section with 4-column grid

### 4. **pages/contact/contact.component**
- Two-column layout:
  - **Left:** Contact form with fields:
    - Name, Email, Phone (required)
    - Animal type dropdown
    - Subject dropdown
    - Message textarea
    - Product selection pills (if coming from favorites)
    - Submit button
    - Success message display
  - **Right:** Contact information
    - Address, Phone, Email with icons
    - Google Maps placeholder
- Form validation
- Success/error handling

### 5. **pages/product-detail/product-detail.component**
- Display selected product details
- Full product image
- Product name, category
- Product description
- Specifications table
- Related products section
- Add to favorites button
- Request button

---

## Services to Create (shared/services/)

### 1. **ProductService**
```typescript
Methods:
- getProducts(): Observable<Product[]>
- getProductById(id: string): Observable<Product>
- getProductsByCategory(category: string): Observable<Product[]>
- getProductsBySubcategory(subcategory: string): Observable<Product[]>
- getFeaturedLiquids(): Observable<Product[]>
- getFeaturedPowders(): Observable<Product[]>
- searchProducts(query: string): Observable<Product[]>
```

### 2. **FavoritesService**
```typescript
Methods:
- getFavorites(): Observable<Favorite[]>
- addFavorite(product: Product): Observable<void>
- removeFavorite(productId: string): Observable<void>
- toggleFavorite(product: Product): Observable<void>
- updateQuantity(productId: string, quantity: number): Observable<void>
- getFavoritesCount(): Observable<number>
```

### 3. **NavigationService**
```typescript
Methods:
- navigateTo(page: string): void
- getCurrentPage(): Observable<string>
- getNavigation(): Navigation[]
```

### 4. **SearchService**
```typescript
Methods:
- search(query: string): Observable<SearchResult[]>
- getPopularSearches(): Observable<string[]>
- getSuggestions(query: string): Observable<string[]>
```

### 5. **FormService**
```typescript
Methods:
- submitContactForm(data: ContactForm): Observable<void>
- validateForm(data: ContactForm): ValidationError[]
```

---

## Data Models (shared/models/)

### Product.model.ts
```typescript
interface Product {
  id: string;
  name: string;
  category: string;
  subcategory: string;
  image: string;
  description: string;
  specifications?: Specification[];
  isFeatured: boolean;
  imageUrl: string;
}

interface Specification {
  label: string;
  value: string;
}
```

### Favorite.model.ts
```typescript
interface Favorite {
  productId: string;
  product: Product;
  quantity: number;
  addedDate: Date;
}
```

### Category.model.ts
```typescript
interface Category {
  id: string;
  name: string;
  icon: string;
  productCount: number;
}
```

### Navigation.model.ts
```typescript
interface Navigation {
  id: string;
  label: string;
  route: string;
  icon?: string;
  children?: Navigation[];
}
```

### ContactForm.model.ts
```typescript
interface ContactForm {
  name: string;
  email: string;
  phone: string;
  animalType: string;
  subject: string;
  message: string;
  selectedProducts?: string[];
}
```

---

## Styling Strategy

### Variables (shared/styles/variables.scss)
Convert all CSS custom properties to SCSS variables:
```scss
// Colors
$primary-color: #2A7D4F;
$primary-medium: #48BB78;
$primary-light: #E8F5EE;
$primary-dark: #1A5C38;
$bg-color: #FFFFFF;
$bg-secondary: #F7F8FA;
$bg-green: #F0FAF5;
$text-primary: #1A202C;
$text-medium: #4A5568;
$text-light: #718096;
$border-color: #E2E8F0;

// Shadows
$shadow-sm: 0 1px 3px rgba(0,0,0,0.08);
$shadow-md: 0 4px 12px rgba(0,0,0,0.10);
$shadow-lg: 0 8px 24px rgba(0,0,0,0.12);
$shadow-xl: 0 12px 32px rgba(0,0,0,0.15);

// Border Radius
$radius-sm: 6px;
$radius-md: 10px;
$radius-lg: 14px;
$radius-xl: 20px;
$radius-pill: 999px;
```

### Component Styling
- Each component has its own .scss file
- Use BEM naming convention
- Import variables and utilities
- Use SCSS nesting for readability
- Implement responsive design with breakpoints

### Global Styles (styles/global.scss)
- Reset default styles
- Define typography
- Set up breakpoints
- Common animations (fadeIn, float, etc.)

---

## Routing Configuration (app-routing.module.ts)

```typescript
Routes:
- '' → HomeComponent
- 'products' → ProductsComponent
- 'product/:id' → ProductDetailComponent
- 'about' → AboutComponent
- 'contact' → ContactComponent
- '**' → PageNotFoundComponent (optional)
```

---

## State Management (Optional: NgRx/Signals)

**Consider using:**
- Angular Signals for reactive state (modern Angular approach)
- Or NgRx for complex state management
- Store: favorites, selected page, search results, filters
- Effects: API calls, localStorage persistence

---

## Key Features to Implement

### 1. Navigation & Routing
- Page switching without reload
- Maintain scroll position
- Remember active page
- Navbar highlight current page
- Product dropdown filtering integration

### 2. Carousel/Slider
- Previous/Next arrow navigation
- Pagination dots with click support
- Smooth CSS transitions
- Dynamic slide calculation based on items and items per page
- Support different grid column counts for different sections

### 3. Search Functionality
- Open/close search overlay
- Input with real-time search
- Display popular search chips
- Popular searches: "Vitamins & Minerals", "Powders", etc.
- Close on background click

### 4. Favorites System
- Toggle favorite on product cards
- Store favorites (localStorage initially, then API)
- Display favorite count badge
- Favorites drawer with quantity controls
- Add to contact form prefill from favorites

### 5. Form Handling
- Contact form with validation
- Email validation
- Required field validation
- Success message after submission
- Prefill selected products from favorites

### 6. Filtering
- Category filter buttons
- Sub-category filter for featured sections
- Reset slider when filter changes
- Show/hide dots based on filtered content

### 7. Responsive Design
- Mobile-first approach
- Breakpoints: 576px, 768px, 1024px, 1280px
- Adjust grid columns for different screen sizes
- Stack hero content on mobile
- Hamburger menu for mobile nav (optional)

---

## Angular Configuration Requirements

### Dependencies
```json
{
  "dependencies": {
    "@angular/animations": "^17.0.0",
    "@angular/common": "^17.0.0",
    "@angular/compiler": "^17.0.0",
    "@angular/core": "^17.0.0",
    "@angular/forms": "^17.0.0",
    "@angular/platform-browser": "^17.0.0",
    "@angular/platform-browser-dynamic": "^17.0.0",
    "@angular/router": "^17.0.0",
    "rxjs": "^7.8.0"
  },
  "devDependencies": {
    "@angular/cli": "^17.0.0",
    "@angular/compiler-cli": "^17.0.0",
    "typescript": "~5.2.0",
    "sass": "^1.69.0"
  }
}
```

### Angular Version
- Use Angular 17+ (latest)
- Use standalone components where applicable
- Use new control flow syntax (@if, @for, @switch)
- Use OnPush change detection strategy for performance

### Module/Standalone Configuration
- Consider using standalone components (recommended)
- Use CommonModule for shared components
- Use ReactiveFormsModule for forms
- Use HttpClientModule for API calls

---

## Asset Management

### Images
- Store all product images in `assets/images/vet_imges/`
- Maintain original naming: 
  - ultra-lyte-fort-mockup-EN-4000-4000-px-scaled.png
  - AMINO-16-1000G-EN-Mock-up-4000px-4000px-scaled.png
  - Powder Formulas.png
  - Liquid Solutions.png
  - etc.

### Icons
- Convert emoji to SVG icons (optional)
- Store in `assets/icons/`
- Create icon component wrapper

---

## Additional Considerations

### 1. Accessibility
- Use semantic HTML
- Add ARIA labels where needed
- Ensure proper heading hierarchy
- Support keyboard navigation

### 2. Performance
- Lazy load images
- Implement OnPush change detection
- Use trackBy in *ngFor
- Tree-shaking unused code

### 3. SEO
- Meta tags for each page
- Proper heading structure
- Alt text for images
- Structured data (optional)

### 4. Testing
- Unit tests for services
- Component tests for UI logic
- E2E tests for critical paths

### 5. LocalStorage
- Persist favorites to localStorage
- Remember user's last viewed page
- Store search history (optional)

---

## Conversion Steps (Recommended Order)

1. Set up Angular project with CLI
2. Create folder structure and shared folder
3. Create all shared components and services
4. Convert CSS to SCSS with variables
5. Create page components and routing
6. Implement data models and services
7. Build home page sections sequentially
8. Implement favorite system
9. Build products and about pages
10. Build contact page with form
11. Add responsive design
12. Test and optimize

---

## Additional Notes

- Maintain all color scheme and styling from original
- Keep all animation timings (0.3s transitions, etc.)
- Preserve all interactive behaviors exactly as coded
- Ensure carousel pagination matches exactly (4 cards per page for both Liquid and Powder)
- All inline event handlers should be converted to proper Angular event binding with handlers in components
- Replace emoji icons with proper iconography later (optional)
- Consider DRY principle - combine Liquid and Powder featured sections into single reusable component with configuration

