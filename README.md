# Erebus - Outdoor Activity Platform

Erebus is a cross-platform mobile app that unifies outdoor discovery, planning, recording, social features, and live cameras for hiking, skiing, and mountain biking. The initial launch focuses on Utah with plans for future expansion.

## Features

- 🏃‍♂️ Activity tracking with GPS, splits, elevation, and photos
- 🗺️ Interactive maps with routes, GPX import, and offline support
- 🌡️ Real-time conditions and hazard reporting
- 📸 Live cameras from resorts, parks, and freeways
- 👥 Social features with crews, events, and activity sharing
- 📱 Story generation with activity highlights
- 🔒 Privacy controls with home zone protection

## Tech Stack

- **Mobile**: React Native + Expo
- **Backend**: Supabase (PostgreSQL, PostGIS, Auth, Storage, Edge Functions)
- **Maps**: Mapbox/MapLibre
- **State**: Zustand + React Query
- **Analytics**: PostHog
- **Testing**: Jest + React Native Testing Library + Detox

## Requirements

- Node.js 18+
- Expo CLI
- Supabase CLI
- Xcode 14+ (iOS development)
- FFmpeg (for story rendering)

## Environment Setup

1. Copy `.env.example` to `.env` and fill in:

```bash
EXPO_PUBLIC_SUPABASE_URL=
EXPO_PUBLIC_SUPABASE_ANON_KEY=
SUPABASE_SERVICE_ROLE_KEY=
POSTHOG_API_KEY=
MAPBOX_TOKEN=
CAMERA_SOURCES_ALLOWLIST=
```

2. Install dependencies:

```bash
npm install
```

## Development

### Running Supabase Locally

```bash
supabase start
supabase db reset # Reset and run migrations
supabase db seed # Load sample data
```

### Running Mobile App

```bash
cd apps/mobile
npm run ios     # iOS Simulator
npm run android # Android Emulator
```

### Running Admin Console

```bash
cd apps/admin
npm run dev
```

## Testing

```bash
# Unit and component tests
npm test

# E2E tests (requires running Expo dev build)
npm run test:e2e

# Lint
npm run lint
```

## CI/CD

GitHub Actions handle:
- Lint and test on PR
- Build and deploy preview apps via EAS
- Deploy production builds on release

## Demo Data

The seed data includes:
- Utah ski resorts and parks
- Sample routes and activities
- Test user accounts
- Live camera feeds

## Contributing

See CONTRIBUTING.md for development guidelines.

## License

MIT 
