# AI Agent Instructions for EventKu Platform

## Project Overview
EventKu is a web-based event management platform built with HTML, CSS, and vanilla JavaScript. The platform allows users to browse, search, and book tickets for various events, with separate interfaces for regular users and event organizers.

## Architecture

### Frontend Structure
- **Authentication Flow** (`login.html`, `signup.html`, `auth.css`)
  - Uses LocalStorage for user data persistence
  - Implements basic form validation for email, username, and password
  - Pattern: Stateless authentication with client-side validation

- **User Dashboard** (`dashboard_new.html`, `style.css`)
  - Event showcase with categorized display
  - Search functionality with category filtering
  - Statistics display section

- **Event Details** (`detail-event.html`, `detail.css`)
  - Ticket quantity management with real-time price updates
  - Interactive counter UI pattern
  - Responsive layout with grid and flexbox

- **Event Organizer Dashboard** (`eo.html`, `eo.css`)
  - Admin interface for event management
  - Bootstrap-based responsive design
  - Event status tracking system

## Key Patterns & Conventions

### CSS Organization
- BEM-like naming with component-based organization
- Variables defined in `:root` for theming
- Mobile-first responsive design with `@media` queries
- Example from `detail.css`:
```css
.event-content {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 16px 18px;
  height: 100%;
}
```

### JavaScript Patterns
- Event delegation for dynamic elements
- LocalStorage for client-side data persistence
- Example of form handling:
```javascript
signupForm.addEventListener("submit", (e) => {
  e.preventDefault();
  // Validation logic
  const userData = { email, username, password };
  localStorage.setItem("userData", JSON.stringify(userData));
});
```

### Component Structure
1. Header/Navigation
   - Consistent navbar across pages
   - Responsive menu with user authentication state

2. Event Cards
   - Standard layout with image, category, date, location
   - Interactive hover states
   - Consistent action buttons

## Development Workflow

### Adding New Features
1. Create/modify HTML in the root directory
2. Add corresponding styles in component-specific CSS file
3. Implement JavaScript functionality inline or in dedicated script sections
4. Test responsive behavior across breakpoints

### Common Tasks
- **Adding Events**: Use the event card template in `dashboard.html`
- **Styling New Components**: Follow existing color scheme from CSS variables
- **Form Validation**: Implement client-side validation following `signup.html` pattern

## Testing
- Test responsive layouts at standard breakpoints (768px, 480px)
- Verify LocalStorage data persistence
- Check form validation across all input fields

## Tips for AI Agents
1. When modifying styles, reference existing CSS variables for consistency
2. Maintain mobile-first responsive patterns
3. Follow existing validation patterns for forms
4. Keep JavaScript unobtrusive and event-driven
5. Preserve the current authentication flow using LocalStorage

## Key Files Reference
- `auth.css`: Authentication styling
- `style.css`: Main styling
- `eo.css`: Event organizer dashboard styling
- `detail.css`: Event detail page styling
- `login.html`, `signup.html`: Authentication pages
- `dashboard_new.html`: Main user interface
- `detail-event.html`: Event details and booking
- `eo.html`: Event organizer dashboard

## Best Practices
1. Use semantic HTML elements consistently
2. Maintain responsive design patterns
3. Follow established naming conventions
4. Keep JavaScript modular and event-driven
5. Utilize existing CSS utility classes