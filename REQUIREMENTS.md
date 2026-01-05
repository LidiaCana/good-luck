# Good Luck - Project Requirements

## 1. Project Overview

Good Luck is a raffle platform application where users can either organize raffles or participate in them. The platform enables raffle organizers to create and manage raffles, while participants can browse, subscribe to, and purchase tickets for raffles.

## 2. Technical Stack

### Backend
- **Framework**: Phoenix (Elixir)
- **Language**: Elixir
- **Database**: PostgreSQL (recommended for Phoenix)
- **Payment Processing**: Stripe
- **Authentication**: Auth0 or Clerk (external service)

### Frontend
- **Framework**: Flutter (Dart)
- **Alternative Considerations**: 
  - React Native (if web support is needed)
  - React with Next.js (if web-first approach)
  - Flutter is recommended for cross-platform mobile apps

### Development Standards
- TypeScript/Elixir best practices
- ESLint/Elixir Credo for linting
- Code formatting standards
- Type safety enforcement

## 3. User Roles

### 3.1 Raffle Organizer
Users who create and manage raffles, set prices, view statistics, and manage their Stripe account.

### 3.2 Participant/User
Users who browse raffles, purchase tickets, view posts, and manage their profile and wallet.

## 4. Feature Requirements by Role

---

## 4.1 Authentication & Authorization

### 4.1.1 Authentication
- **Feature**: User authentication via external service
- **Requirements**:
  - Integration with Auth0 or Clerk
  - Support for email/password authentication
  - Social login (Google, Facebook, etc.) - optional
  - JWT token management
  - Token refresh mechanism
  - Session management
- **User Roles**: Both Organizers and Participants

### 4.1.2 Authorization
- **Feature**: Role-based access control
- **Requirements**:
  - Distinguish between Organizer and Participant roles
  - Role assignment during registration or profile setup
  - Permission checks for role-specific features
- **User Roles**: Both

---

## 4.2 Raffle Organizer Features

### 4.2.1 Dashboard
- **Feature**: Main dashboard for organizers
- **Requirements**:
  - Overview of active raffles
  - Quick statistics (total earnings, active raffles count)
  - Recent activity feed
  - Quick actions (create new raffle, view analytics)
- **User Role**: Organizer only

### 4.2.2 Raffle Management
- **Feature**: Create and manage raffles
- **Requirements**:
  - **Create Raffle**:
    - Raffle title/name
    - Description
    - Prize details
    - Ticket price (virtual currency)
    - Maximum number of tickets (optional)
    - Raffle draw date/time
    - Prize images/media
    - Terms and conditions
  - **Edit Raffle**:
    - Modify raffle details (before draw date)
    - Update ticket price (with restrictions)
    - Extend draw date (with restrictions)
  - **Cancel Raffle**:
    - Cancel before draw date
    - Refund mechanism for purchased tickets
  - **View Raffle Details**:
    - See all raffle information
    - View ticket sales count
    - View participants list
- **User Role**: Organizer only

### 4.2.3 Pricing & Earnings
- **Feature**: Set ticket prices and view earnings
- **Requirements**:
  - Set ticket price per raffle (in virtual currency)
  - View total earnings per raffle
  - View total earnings across all raffles
  - Earnings breakdown (by date, by raffle)
  - Export earnings reports (CSV/PDF)
- **User Role**: Organizer only

### 4.2.4 Statistics & Analytics
- **Feature**: View raffle statistics
- **Requirements**:
  - **Raffle Statistics**:
    - Total tickets sold per raffle
    - Revenue per raffle
    - Conversion rate (views vs purchases)
    - Participant demographics (optional)
  - **Overall Statistics**:
    - Total raffles created
    - Total tickets sold (all raffles)
    - Total revenue
    - Average ticket price
    - Most popular raffles
  - **Visualizations**:
    - Charts for revenue over time
    - Ticket sales trends
    - Raffle performance comparison
- **User Role**: Organizer only

### 4.2.5 Raffle History
- **Feature**: View past raffles
- **Requirements**:
  - List of all past raffles (completed, cancelled)
  - Filter by date range
  - Filter by status (completed, cancelled)
  - View winner information
  - View final statistics for each raffle
- **User Role**: Organizer only

### 4.2.6 Ticket Sales Management
- **Feature**: View ticket purchases
- **Requirements**:
  - Real-time count of tickets sold
  - List of participants who bought tickets
  - Participant details (name, ticket count, purchase date)
  - Export participant list
  - Search/filter participants
- **User Role**: Organizer only

### 4.2.7 Post Management
- **Feature**: Create and manage promotional posts
- **Requirements**:
  - **Create Posts**:
    - Post title
    - Post description/content
    - Upload images (multiple)
    - Upload videos (optional)
    - Link to raffle
    - Post scheduling (optional)
  - **Edit Posts**:
    - Modify post content
    - Update media
    - Delete posts
  - **View Posts**:
    - List all posts
    - View post engagement (likes, comments, shares)
    - Post analytics (views, clicks)
- **User Role**: Organizer only

### 4.2.8 Multimedia Content
- **Feature**: Upload and manage media
- **Requirements**:
  - Image upload (JPEG, PNG, WebP)
  - Video upload (MP4, MOV)
  - File size limits
  - Image compression/optimization
  - Video transcoding (optional)
  - Media library/gallery
  - Delete media
- **User Role**: Organizer only

### 4.2.9 Stripe Account Management
- **Feature**: Manage Stripe integration
- **Requirements**:
  - Connect Stripe account
  - View Stripe account status
  - View Stripe balance
  - Configure payout settings
  - View transaction history
  - Handle Stripe webhooks
  - Disconnect Stripe account
- **User Role**: Organizer only

---

## 4.3 Participant/User Features

### 4.3.1 Raffle Discovery
- **Feature**: Browse available raffles
- **Requirements**:
  - **Raffle Feed**:
    - List of all available raffles
    - Filter by category (if implemented)
    - Filter by price range
    - Filter by draw date
    - Search raffles by name/description
    - Sort by: newest, price, draw date, popularity
  - **Raffle Details**:
    - View full raffle information
    - View prize details and images
    - View ticket price
    - View number of tickets sold
    - View draw date
    - View organizer information
    - View terms and conditions
- **User Role**: Participant only

### 4.3.2 Ticket Purchase
- **Feature**: Buy tickets for raffles
- **Requirements**:
  - Select number of tickets to purchase
  - View total cost
  - Confirm purchase
  - Payment processing (virtual currency)
  - Purchase confirmation
  - Ticket receipt
  - View purchased tickets in profile
- **User Role**: Participant only

### 4.3.3 Post Viewing
- **Feature**: View promotional posts
- **Requirements**:
  - View posts from organizers
  - View post media (images, videos)
  - Like posts (optional)
  - Comment on posts (optional)
  - Share posts (optional)
  - Filter posts by organizer
- **User Role**: Participant only

### 4.3.4 Winner Posts
- **Feature**: Create and view winner posts
- **Requirements**:
  - **Create Winner Post**:
    - Post title
    - Post description
    - Upload images/videos
    - Link to won raffle
    - Share experience
  - **View Winner Posts**:
    - Browse posts from other winners
    - Filter by raffle
    - Like/comment on winner posts
- **User Role**: Participant only

### 4.3.5 Casino Games (Coming Soon)
- **Feature**: Casino games section
- **Requirements**:
  - Placeholder tab/section
  - "Coming Soon" message
  - Future implementation placeholder
- **User Role**: Participant only

### 4.3.6 Profile Management
- **Feature**: Manage user profile
- **Requirements**:
  - Edit profile name
  - View profile information
  - View account balance (virtual currency)
  - View purchase history
  - View tickets purchased
  - View won raffles
  - Profile picture (optional)
- **User Role**: Participant only

### 4.3.7 Wallet Management
- **Feature**: Manage virtual currency wallet
- **Requirements**:
  - **View Wallet**:
    - Current balance
    - Transaction history
    - Incoming/outgoing transactions
  - **Top Up Wallet**:
    - Add funds to wallet
    - Integration with payment gateway (Stripe)
    - Minimum/maximum top-up limits
    - Top-up confirmation
    - Transaction receipt
  - **Wallet Security**:
    - Transaction limits
    - Security verification for large transactions
- **User Role**: Participant only

---

## 5. Technical Requirements

### 5.1 Backend (Phoenix/Elixir)

#### 5.1.1 API Structure
- RESTful API design
- JSON API format
- API versioning (v1, v2, etc.)
- Rate limiting
- CORS configuration
- API documentation (OpenAPI/Swagger)

#### 5.1.2 Database Schema
- **Users Table**:
  - id, email, name, role (organizer/participant)
  - auth_provider_id (Auth0/Clerk ID)
  - created_at, updated_at
- **Raffles Table**:
  - id, organizer_id, title, description
  - ticket_price, max_tickets, draw_date
  - status (draft, active, completed, cancelled)
  - created_at, updated_at
- **Tickets Table**:
  - id, raffle_id, user_id, quantity
  - purchase_date, transaction_id
- **Posts Table**:
  - id, user_id, raffle_id (optional)
  - title, content, post_type (promotional/winner)
  - created_at, updated_at
- **Media Table**:
  - id, post_id, file_url, file_type
  - file_size, created_at
- **Transactions Table**:
  - id, user_id, transaction_type (top_up, purchase)
  - amount, balance_before, balance_after
  - status, created_at
- **Stripe Accounts Table**:
  - id, organizer_id, stripe_account_id
  - status, connected_at

#### 5.1.3 Background Jobs
- Raffle draw processing
- Email notifications
- Image/video processing
- Statistics calculation
- Payment processing

#### 5.1.4 Real-time Features
- WebSocket support for real-time updates
- Live ticket count updates
- Notification system

### 5.2 Frontend (Flutter)

#### 5.2.1 Architecture
- Clean Architecture pattern
- State management (Provider, Riverpod, or Bloc)
- Dependency injection
- Repository pattern

#### 5.2.2 UI/UX Requirements
- Responsive design
- Dark mode support (optional)
- Accessibility support
- Loading states
- Error handling UI
- Empty states
- Pull-to-refresh

#### 5.2.3 Navigation
- Bottom navigation bar
- Deep linking support
- Navigation guards (auth required)

#### 5.2.4 State Management
- User authentication state
- Wallet balance state
- Raffle list state
- Shopping cart state (for ticket purchases)

### 5.3 Authentication Integration

#### 5.3.1 Auth0/Clerk Setup
- OAuth 2.0 / OpenID Connect
- Token storage (secure storage)
- Token refresh mechanism
- Logout functionality
- User profile sync

### 5.4 Payment Integration

#### 5.4.1 Stripe Integration
- Stripe Connect for organizers
- Payment intents for wallet top-ups
- Webhook handling
- Payout management
- Refund processing

### 5.5 File Storage

#### 5.5.1 Media Storage
- Cloud storage solution (AWS S3, Google Cloud Storage, or similar)
- CDN for media delivery
- Image optimization
- Video transcoding (optional)

---

## 6. Non-Functional Requirements

### 6.1 Performance
- API response time < 200ms (p95)
- Image loading optimization
- Pagination for lists
- Lazy loading

### 6.2 Security
- HTTPS only
- Input validation
- SQL injection prevention
- XSS prevention
- CSRF protection
- Secure token storage
- PCI compliance for payments

### 6.3 Scalability
- Horizontal scaling capability
- Database indexing
- Caching strategy (Redis)
- CDN for static assets

### 6.4 Reliability
- Error logging and monitoring
- Health checks
- Backup and recovery
- Transaction rollback on failures

### 6.5 Testing
- Unit tests
- Integration tests
- E2E tests
- API tests

---

## 7. Development Phases (Suggested)

### Phase 1: Foundation
- Project setup (Phoenix + Flutter)
- Authentication integration
- Basic user management
- Database schema

### Phase 2: Core Raffle Features
- Raffle CRUD operations
- Ticket purchase flow
- Basic wallet system

### Phase 3: Organizer Dashboard
- Dashboard UI
- Statistics and analytics
- Post management

### Phase 4: Enhanced Features
- Media upload
- Winner posts
- Advanced analytics

### Phase 5: Payment Integration
- Stripe Connect setup
- Wallet top-up
- Payout management

### Phase 6: Polish & Optimization
- Performance optimization
- UI/UX improvements
- Testing
- Documentation

---

## 8. API Endpoints (High-Level)

### Authentication
- `POST /api/v1/auth/login`
- `POST /api/v1/auth/logout`
- `POST /api/v1/auth/refresh`
- `GET /api/v1/auth/me`

### Raffles
- `GET /api/v1/raffles` (list)
- `GET /api/v1/raffles/:id` (details)
- `POST /api/v1/raffles` (create - organizer)
- `PUT /api/v1/raffles/:id` (update - organizer)
- `DELETE /api/v1/raffles/:id` (cancel - organizer)
- `GET /api/v1/raffles/:id/statistics` (organizer)

### Tickets
- `POST /api/v1/raffles/:id/tickets` (purchase)
- `GET /api/v1/tickets` (user's tickets)
- `GET /api/v1/raffles/:id/tickets` (organizer view)

### Posts
- `GET /api/v1/posts` (list)
- `GET /api/v1/posts/:id` (details)
- `POST /api/v1/posts` (create)
- `PUT /api/v1/posts/:id` (update)
- `DELETE /api/v1/posts/:id` (delete)

### Wallet
- `GET /api/v1/wallet` (balance)
- `GET /api/v1/wallet/transactions` (history)
- `POST /api/v1/wallet/top-up` (add funds)

### Stripe
- `POST /api/v1/stripe/connect` (connect account)
- `GET /api/v1/stripe/account` (account status)
- `GET /api/v1/stripe/balance` (balance)

---

## 9. Environment Variables

### Backend
- `DATABASE_URL`
- `SECRET_KEY_BASE`
- `AUTH0_DOMAIN` / `CLERK_SECRET_KEY`
- `STRIPE_SECRET_KEY`
- `STRIPE_WEBHOOK_SECRET`
- `AWS_ACCESS_KEY_ID` (for media storage)
- `AWS_SECRET_ACCESS_KEY`
- `AWS_S3_BUCKET`

### Frontend
- `API_BASE_URL`
- `AUTH0_CLIENT_ID` / `CLERK_PUBLISHABLE_KEY`
- `STRIPE_PUBLISHABLE_KEY`

---

## 10. Future Considerations

- Push notifications
- Email notifications
- SMS notifications
- Multi-language support
- Admin dashboard
- Casino games implementation
- Social features (follow organizers, friends)
- Raffle categories/tags
- Advanced search and filters
- Recommendation engine

