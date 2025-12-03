# sample-demo-here

A pnpm + Go monorepo with React Router 7 apps and shared UI components.

## Structure

```
.
├── apps/
│   ├── app1/          # React Router 7 app 1
│   └── app2/          # React Router 7 app 2
├── packages/
│   └── ui/            # Shared UI components (shadcn/ui)
└── api/               # Go API
```

## Prerequisites

- Node.js 20+
- pnpm 10+
- Go 1.22+

## Getting Started

### Install Dependencies

```bash
pnpm install
```

### Development

Run all apps in development mode:

```bash
pnpm dev
```

Or run individual apps:

```bash
# App 1 (default port 5173)
cd apps/app1 && pnpm dev

# App 2 (default port 5173)
cd apps/app2 && pnpm dev
```

### Build

```bash
pnpm build
```

### Go API

```bash
cd api
go mod tidy
go run .
```

The API runs on port 8080 with the following endpoints:

- `GET /` - Welcome message
- `GET /health` - Health check
- `GET /api/hello` - Hello World
- `GET /api/hello/{name}` - Personalized hello

## Shared UI Package

The `@repo/ui` package contains shared shadcn/ui components:

- `Button` - A versatile button component with variants (default, secondary, outline, destructive, ghost, link)

### Usage

```tsx
import { Button } from "@repo/ui";

export function MyComponent() {
  return (
    <div>
      <Button>Click me</Button>
      <Button variant="secondary">Secondary</Button>
      <Button variant="outline">Outline</Button>
    </div>
  );
}
```