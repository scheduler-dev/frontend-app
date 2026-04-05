# GitHub Copilot Instructions

## Project Context
This is a React 18 + TypeScript 5 frontend application using Vite, Tailwind CSS, and React Query.

## Coding Guidelines

### Components
- Always define a TypeScript interface for component props
- Use `React.FC<Props>` type annotation
- Export components as named exports

```tsx
interface ButtonProps {
  label: string;
  onClick: () => void;
  disabled?: boolean;
}

export const Button: React.FC<ButtonProps> = ({ label, onClick, disabled = false }) => {
  return (
    <button onClick={onClick} disabled={disabled} className="btn">
      {label}
    </button>
  );
};
```

### API Calls
Always use React Query hooks, never raw fetch in components:

```tsx
const { data, isLoading, error } = useQuery({
  queryKey: ['users', userId],
  queryFn: () => api.users.get(userId),
});
```

### Error Handling
- Use error boundaries for component trees
- Log errors to the monitoring service via `logger.error()`
- Show user-friendly messages, never raw error strings

## File Organization
- Components: `src/components/<ComponentName>/index.tsx`
- Pages: `src/pages/<PageName>.tsx`
- Hooks: `src/hooks/use<HookName>.ts`
- API: `src/api/<resource>.ts`
