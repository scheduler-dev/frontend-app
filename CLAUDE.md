# Frontend App

React + TypeScript dashboard application.

## Project Structure

```
src/
├── components/   # Reusable UI components
├── pages/        # Route-level page components
├── hooks/        # Custom React hooks
├── api/          # API client and types
└── utils/        # Shared utilities
```

## Development

```bash
npm install
npm run dev       # Start dev server (localhost:3000)
npm test          # Run tests
npm run build     # Production build
```

## Key Rules

- Use functional components with hooks (no class components)
- Prefer `const` over `let`; never use `var`
- All API calls go through `src/api/client.ts`
- Components must have TypeScript prop interfaces
- Write tests for all custom hooks

## Tech Stack

- React 18 + TypeScript 5
- Vite for bundling
- Tailwind CSS for styling
- React Query for server state
- Vitest + Testing Library for tests
