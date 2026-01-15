# AarogyaNet - Healthcare Web Application

A comprehensive healthcare web application built with React, TypeScript, and modern web technologies. This application provides a complete platform for patients to search medicines, book doctor appointments, and manage their healthcare needs.

## Features

### 🏥 Core Healthcare Features
- **Medicine Search & Ordering**: Browse, search, and order medicines with prescription management
- **Doctor Appointments**: Find doctors, view availability, and book appointments
- **Order Tracking**: Real-time tracking of medicine orders
- **User Profiles**: Comprehensive user profile management with avatar upload
- **Prescription Management**: Digital prescription handling

### 🔐 Authentication & Security
- JWT-based authentication with automatic token refresh
- Role-based access control (Patient, Doctor, Admin)
- Protected routes and secure API communication
- Password strength validation and secure storage

### 🎨 Modern UI/UX
- Responsive design with Tailwind CSS
- Clean, accessible components
- Mobile-first approach
- Loading states and error handling
- Modern card-based layouts

### 🛠 Technical Features
- TypeScript for type safety
- Zustand for state management
- React Router for navigation
- Axios for API communication
- WebSocket support for real-time features
- Form validation with react-hook-form

## Tech Stack

- **Frontend**: React 19, TypeScript, Vite
- **Styling**: Tailwind CSS
- **State Management**: Zustand
- **Routing**: React Router DOM
- **HTTP Client**: Axios
- **Icons**: Heroicons
- **Form Handling**: React Hook Form
- **Date Handling**: date-fns
- **Authentication**: JWT with automatic refresh

## Project Structure

```
src/
├── api/                 # API service layer
│   ├── authApi.ts      # Authentication endpoints
│   ├── doctorApi.ts    # Doctor-related endpoints
│   ├── medicineApi.ts  # Medicine-related endpoints
│   ├── userApi.ts      # User profile endpoints
│   └── base.ts         # Axios configuration
├── components/         # Reusable UI components
│   ├── auth/          # Authentication components
│   ├── common/        # Generic UI components
│   ├── doctor/        # Doctor-specific components
│   ├── layout/        # Layout components
│   └── medicine/      # Medicine-specific components
├── hooks/             # Custom React hooks
│   ├── useAuth.ts     # Authentication hook
│   ├── useFetch.ts    # Data fetching hook
│   └── useWebSocket.ts # WebSocket hook
├── pages/             # Page components
│   ├── auth/          # Login/Signup pages
│   ├── doctor/        # Doctor-related pages
│   ├── medicine/      # Medicine-related pages
│   └── profile/       # User profile pages
├── routes/            # Routing configuration
│   ├── AppRoutes.tsx  # Main routes
│   └── ProtectedRoute.tsx # Route protection
├── store/             # Zustand stores
│   ├── authStore.ts   # Authentication state
│   ├── doctorStore.ts # Doctor-related state
│   └── medicineStore.ts # Medicine-related state
├── types/             # TypeScript type definitions
│   ├── auth.d.ts      # Authentication types
│   ├── doctor.d.ts    # Doctor-related types
│   └── medicine.d.ts  # Medicine-related types
└── utils/             # Utility functions
    ├── constants.ts   # App constants
    ├── jwt.ts         # JWT utilities
    └── validators.ts  # Form validators
```

## Getting Started

### Prerequisites
- Node.js (v18 or higher)
- npm or yarn

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd aarogyanet
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Setup**
   ```bash
   cp .env.example .env
   ```
   
   Update the `.env` file with your API configuration:
   ```env
   VITE_API_BASE_URL=http://localhost:3001/api
   VITE_WS_URL=ws://localhost:3001
   NODE_ENV=development
   ```

4. **Start the development server**
   ```bash
   npm run dev
   ```

5. **Open your browser**
   Navigate to `http://localhost:5173`

### Building for Production

```bash
npm run build
```

The built files will be in the `dist` directory.

## API Integration

The application is designed to work with a REST API backend. Key endpoints include:

- **Authentication**: `/auth/login`, `/auth/signup`, `/auth/refresh`
- **Medicines**: `/medicines`, `/medicines/search`, `/cart`, `/orders`
- **Doctors**: `/doctors`, `/doctors/search`, `/appointments`
- **Users**: `/users/profile`, `/users/preferences`

## Key Components

### Authentication
- **LoginForm**: User login with validation
- **SignupForm**: User registration with role selection
- **ProtectedRoute**: Route protection based on authentication

### Medicine Management
- **MedicineCard**: Display medicine information
- **SearchBar**: Medicine search with filters
- **OrderTracker**: Track order status and delivery

### Doctor Services
- **DoctorCard**: Display doctor profiles
- **AppointmentSlotPicker**: Book appointment slots
- **ConsultationPage**: Manage consultations

### Common Components
- **Button**: Reusable button with variants
- **Input**: Form input with validation
- **Modal**: Accessible modal dialogs
- **Loader**: Loading indicators
- **Card**: Content containers

## State Management

The application uses Zustand for state management with separate stores for:

- **authStore**: User authentication and profile
- **medicineStore**: Medicine catalog, cart, and orders
- **doctorStore**: Doctor listings and appointments

## Routing

Protected routes ensure authenticated access to sensitive pages:
- Public: Home, Login, Signup, Medicine Search, Doctor List
- Protected: Profile, Orders, Appointments, Consultations

## Development Guidelines

### Code Style
- Use TypeScript for all new files
- Follow React functional component patterns
- Use custom hooks for reusable logic
- Implement proper error boundaries

### Component Structure
- Keep components small and focused
- Use composition over inheritance
- Implement proper prop typing
- Include accessibility attributes

### API Integration
- Use the provided API services
- Implement proper error handling
- Show loading states for async operations
- Cache data when appropriate

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

This project is licensed under the MIT License.

## Support

For support and questions, please contact the development team or create an issue in the repository.

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default tseslint.config([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...
      // Enable lint rules for React
      reactX.configs['recommended-typescript'],
      // Enable lint rules for React DOM
      reactDom.configs.recommended,
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```
