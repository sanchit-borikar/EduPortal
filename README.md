# Learn-Assign-Connect: Academic Management Platform

## Overview

Learn-Assign-Connect is a comprehensive educational management platform designed for institutions, trainers, and students. The platform facilitates assignment creation, submission management, materials sharing, and resume building.

## Key Features

### For Students
- Assignment tracking and submission
- Learning materials access and downloads
- Resume submission and portfolio building
- Profile management and progress tracking

### For Trainers
- Student management and progress tracking
- Assignment creation and grading
- Materials upload and organization
- Resume review and feedback

### For Administrators
- User management (students, trainers, admins)
- Batch and course management
- System-wide monitoring and reporting

## Technology Stack

- **Frontend**: React + TypeScript with Vite
- **Styling**: Tailwind CSS + shadcn/ui components
- **State Management**: React Context API
- **Data Fetching**: TanStack Query (React Query)
- **Authentication & Database**: Firebase (Auth, Firestore, Storage)
- **Deployment**: Firebase Hosting

## Getting Started

### Prerequisites
- Node.js (16.x or higher)
- npm or yarn
- Firebase account

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/learn-assign-connect.git
   cd learn-assign-connect
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up environment variables:
   - Copy `.env.example` to `.env.local`
   ```bash
   cp .env.example .env.local
   ```
   - Update with your Firebase configuration

### Development

Run the development server:
```bash
npm run dev
```

The application will be available at `http://localhost:8080`

### Building for Production

Build the application:
```bash
npm run build
```

Preview the production build:
```bash
npm run preview
```

## Deployment

### Deploying to Firebase Hosting

1. Install Firebase CLI globally (if not already installed):
   ```bash
   npm install -g firebase-tools
   ```

2. Login to Firebase:
   ```bash
   firebase login
   ```

3. Initialize Firebase (if not already done):
   ```bash
   firebase init
   ```
   - Select Hosting
   - Choose your Firebase project
   - Set public directory to `dist`
   - Configure as a single-page app
   - Set up automatic builds and deploys

4. Deploy to Firebase:
   ```bash
   npm run deploy
   ```

### Continuous Deployment

You can set up GitHub Actions for continuous deployment. A sample workflow is included in the `.github/workflows` directory.

## Environment Variables

The following environment variables are required:

```
VITE_FIREBASE_API_KEY=your_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_project_id.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=your_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_project_id.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=your_messaging_sender_id
VITE_FIREBASE_APP_ID=your_app_id
VITE_FIREBASE_MEASUREMENT_ID=your_measurement_id
```

## Project Structure

```
learn-assign-connect/
├── public/             # Static assets
├── src/                # Source code
│   ├── components/     # UI components
│   ├── contexts/       # React contexts
│   ├── hooks/          # Custom hooks
│   ├── lib/            # Utilities and Firebase functions
│   ├── pages/          # Page components
│   └── App.tsx         # Main application component
├── .env.example        # Example environment variables
├── .firebaserc         # Firebase project configuration
├── firebase.json       # Firebase hosting configuration
├── tailwind.config.ts  # Tailwind CSS configuration
└── vite.config.ts      # Vite configuration
```

## License

This project is licensed under the MIT License.
