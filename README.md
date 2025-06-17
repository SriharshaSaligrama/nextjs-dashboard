# Next.js Dashboard Application

A modern, full-featured dashboard application built with Next.js 15, featuring invoice and customer management with authentication.

## Technical Stack
- **Framework**: Next.js 15
- **Authentication**: NextAuth.js
- **Database**: PostgreSQL
- **Styling**: Tailwind CSS
- **UI Components**: Custom components with Heroicons
- **State Management**: React Server Components and Client Components
- **Form Handling**: Server Actions

## Core Features

### 1. Authentication System
- Secure login system using credentials (email/password)
- Password hashing using bcryptjs
- Protected routes using Next.js middleware
- Automatic redirect to login for unauthenticated users
- Session management with NextAuth.js

### 2. Dashboard Overview
Located at `/dashboard`
- Revenue metrics visualization
- Latest invoices summary
- Interactive cards showing key metrics
- Responsive layout with different breakpoints
- Loading states with skeleton components

### 3. Invoice Management
Located at `/dashboard/invoices`
Features:
- Create new invoices
- Edit existing invoices
- Delete invoices
- View invoice details
- Filter and search capabilities
- Pagination system
- Status tracking (paid, pending, overdue)

### 4. Customer Management
Located at `/dashboard/customers`
Features:
- Customer list view
- Customer details
- Customer-invoice relationship
- Profile image management

## Database Structure

The application uses four main tables:

### Users Table
```sql
- id (UUID, Primary Key)
- name (VARCHAR)
- email (TEXT, Unique)
- password (TEXT, Hashed)
```

### Customers Table
```sql
- id (UUID, Primary Key)
- name (VARCHAR)
- email (VARCHAR)
- image_url (VARCHAR)
```

### Invoices Table
```sql
- id (UUID, Primary Key)
- customer_id (UUID, Foreign Key)
- amount (INT)
- status (VARCHAR)
- date (DATE)
```

### Revenue Table
```sql
- month (VARCHAR)
- revenue (INT)
```

## Getting Started

### Prerequisites
- Node.js (LTS version recommended)
- PostgreSQL database
- pnpm (or npm/yarn)

### Installation

1. Clone the repository:
   ```bash
   git clone [repository-url]
   cd nextjs-dashboard
   ```

2. Install dependencies:
   ```bash
   pnpm install
   ```

3. Set up environment variables:
   ```bash
   cp .env.example .env.local
   ```
   Update the environment variables with your PostgreSQL credentials.

4. Initialize the database:
   ```bash
   # Access the seed endpoint to populate the database
   GET /seed
   ```

5. Start the development server:
   ```bash
   pnpm dev
   ```

### Development Commands
```bash
pnpm dev           # Start development server
pnpm build         # Build for production
pnpm start         # Start production server
```

## Security Features

1. **Authentication Protection**
   - Protected API routes
   - Secure session management
   - Password hashing
   - CSRF protection

2. **Data Validation**
   - Input sanitization
   - Type checking with TypeScript
   - Zod schema validation
   - SQL injection prevention

## Performance Optimizations

1. **Server Components**
   - Reduced client-side JavaScript
   - Automatic code splitting
   - Streaming with Suspense boundaries

2. **Data Fetching**
   - Server-side data fetching
   - Cached database queries
   - Optimistic updates

3. **UI Optimizations**
   - Lazy loading of components
   - Image optimization
   - Skeleton loading states
   - Responsive design patterns

## Error Handling
- Form validation errors
- API error responses
- Database error handling
- UI error boundaries
- Custom error pages
- Loading states and skeletons

## Acknowledgments
- Built with [Next.js](https://nextjs.org/)
- Authentication powered by [NextAuth.js](https://next-auth.js.org/)
- UI components from [Heroicons](https://heroicons.com/)
- Styling with [Tailwind CSS](https://tailwindcss.com/)
