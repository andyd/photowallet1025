# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Photo Wallet PWA is a privacy-focused Progressive Web App that allows users to store up to 10 photos locally on their device with no server-side storage. Built with React 18, TypeScript, and Vite, it emphasizes local-first architecture with IndexedDB for storage and gesture-based photo viewing.

## Development Commands

### Essential Commands
```bash
# Development server (runs on port 5000)
npm run dev

# Type checking
npm run check

# Production build (client + server)
npm run build

# Production start
npm start

# Database push (currently unused, but configured)
npm run db:push
```

### Working Directory
The main application code is in `photowalletPWA-replitA/` directory. Always navigate there before running commands.

## Architecture

### Monorepo Structure

The project uses a monorepo pattern with three main directories:

- **`client/`**: React frontend application
  - `client/src/components/`: UI components (custom + shadcn/ui)
  - `client/src/hooks/`: Custom hooks including `usePhotoStore` (Zustand)
  - `client/src/services/photoStorage.ts`: Dexie.js IndexedDB operations
  - `client/src/pages/`: Route pages
  - `client/src/utils/`: Utility functions for photo handling

- **`server/`**: Express backend (minimal, primarily serves static files)
  - `server/index.ts`: Main server entry point
  - `server/routes.ts`: API routes (currently only GitHub repo creation)
  - `server/vite.ts`: Vite dev server integration

- **`shared/`**: Shared TypeScript types
  - `shared/schema.ts`: Photo interface and Zod schemas

### Path Aliases

TypeScript and Vite are configured with these path aliases:
- `@/*` → `client/src/*`
- `@shared/*` → `shared/*`
- `@assets/*` → `attached_assets/*`

Always use these aliases when importing to maintain consistency.

### State Management

**Zustand Store** (`usePhotoStore` in `client/src/hooks/usePhotoStore.ts`):
- Manages photos array, loading states, and viewer state
- All photo operations (add, delete, reorder) go through this store
- Automatically syncs with IndexedDB via `photoStorage` service

**Local Storage with Dexie.js**:
- Database name: `PhotoWalletDB`
- Single table: `photos` with indices on `id`, `order`, `createdAt`
- Photos stored as Blob objects with metadata
- Maximum 10 photos enforced at UI level

### Photo Data Flow

1. User uploads file → `PhotoUploader` component
2. File converted to Blob → `usePhotoStore.addPhoto()`
3. Store calls `photoStorage.addPhoto()` → IndexedDB
4. Store updates local state → UI re-renders
5. Photos displayed in `PhotoGrid` with order maintained

### PWA Configuration

- **Service Worker**: `public/sw.js` handles offline caching
- **Manifest**: `public/manifest.json` configures install behavior
- **vite-plugin-pwa**: Configured in `vite.config.ts` (check for plugin usage)
- Install prompts handled by `InstallPrompt` and `InstallBanner` components

### Gesture System

Uses `@use-gesture/react` for touch interactions in `PhotoViewer`:
- **Swipe**: Navigate between photos (horizontal), close viewer (down)
- **Pinch**: Zoom 1x-3x
- **Double-tap**: Toggle zoom
- **Drag**: Pan when zoomed

All gestures integrated with Framer Motion for smooth animations.

## Design System

The application follows strict design guidelines in `design_guidelines.md`:

- **Dark mode primary**: Deep charcoal backgrounds (HSL: 0 0% 8%)
- **System fonts**: Native feel with -apple-system, BlinkMacSystemFont stack
- **Tailwind CSS**: Custom color palette, spacing primitives (2, 4, 8, 12, 16)
- **shadcn/ui**: "New York" style variant for UI primitives
- **Content-first**: Photos are always the hero, UI fades into background

When making UI changes, reference `design_guidelines.md` for:
- Exact color values and opacity levels
- Typography sizing and weights
- Animation timing and easing functions
- Touch target minimum sizes (44x44px)

## Build Configuration

### Development Build

- Vite dev server proxied through Express
- Hot module replacement (HMR) enabled
- Replit-specific plugins active (cartographer, dev banner, runtime errors)
- Server runs with tsx for TypeScript execution

### Production Build

Two-step process:
1. `vite build` → Outputs client to `dist/public/`
2. `esbuild server/index.ts` → Bundles server to `dist/index.js`

Output format: ESM (ES modules) for both client and server.

### Port Configuration

**Always use port 5000** (or `process.env.PORT`). Other ports are firewalled on Replit. The Express server serves both API routes and static files on this single port.

## Key Components

### Photo Management Components

- **PhotoGrid**: Main grid display with responsive columns (2/3/4 based on screen size)
- **PhotoCard**: Individual thumbnail with delete functionality
- **PhotoViewer**: Full-screen gesture-based viewer
- **AddPhotoCard**: Upload trigger styled as grid card
- **ManagePhotosDialog**: Bulk operations (reorder, delete multiple)

### PWA Components

- **InstallPrompt**: Toast-style "Add to Home Screen" prompt
- **InstallBanner**: Persistent banner for install suggestions
- **usePWA** hook: Detects install state and provides install handlers

## Server Routes

Currently minimal API surface:

- **POST /api/github/create-repo**: Creates GitHub repository and pushes code
  - Requires GitHub OAuth token (handled by `getUncachableGitHubClient`)
  - Automatically initializes git, commits, and pushes

All other requests serve static files or proxy to Vite in development.

## Photo Storage Limits

- **Maximum photos**: 10 (enforced at UI level in PhotoUploader)
- **File size limit**: 10MB per photo
- **Accepted formats**: JPEG, PNG, WebP
- **Duplicate detection**: SHA-256 hash comparison (implementation in `photoUtils.ts`)

## Database Schema

```typescript
interface Photo {
  id: string;          // UUID
  blob: Blob;          // Image data
  filename: string;    // Original filename
  order: number;       // Display sequence
  createdAt: Date;     // Upload timestamp
}
```

Indices: `id` (primary), `order`, `createdAt`

## Testing & Type Checking

- Run `npm run check` to validate TypeScript types before committing
- No test suite currently configured
- Type definitions in `tsconfig.json` include `dom`, `esnext`, `vite/client`

## Common Tasks

### Adding a New Component

1. Create in `client/src/components/` (or `components/ui/` for shadcn)
2. Use path alias: `import { Component } from '@/components/Component'`
3. Follow design guidelines for styling
4. Export from component file directly (no barrel exports)

### Modifying Photo Storage

1. Update schema in `shared/schema.ts` if changing data structure
2. Update Dexie schema in `photoStorage.ts` (increment version number!)
3. Provide migration logic for version changes
4. Update Zustand store operations in `usePhotoStore.ts`

### Adding a New API Route

1. Add route handler in `server/routes.ts`
2. Mount in `registerRoutes()` function
3. Server logs all `/api/*` requests with timing
4. Follow existing error handling pattern

## Dependencies to Be Aware Of

- **Dexie**: IndexedDB wrapper, requires careful version management for schema changes
- **Zustand**: No provider needed, import store directly
- **Wouter**: Lightweight router, different API from React Router
- **@use-gesture/react**: Unified gesture handling, pairs with Framer Motion
- **shadcn/ui**: Components are copied into codebase, not installed as package

## Replit-Specific Considerations

- Development environment assumes Replit workspace
- Replit plugins only load in development when `REPL_ID` exists
- GitHub integration expects Replit's OAuth token system
- Port 5000 is the only exposed port (firewalled environment)
