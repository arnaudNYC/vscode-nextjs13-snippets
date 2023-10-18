# React & Next.js Snippets for VSCode

This README provides details about a collection of snippets for React and Next.js in TypeScript. These snippets are designed to help developers quickly scaffold out components, layouts, templates, and other common structures used in React and Next.js applications.

## How to Use

1.  In a `.tsx` file in VSCode, type the prefix associated with the desired snippet.
2.  Press `Enter` or `Tab` to insert the snippet.
3.  Use the tab key to navigate between placeholders and fill in the desired values.

## Snippets

### Component with props

**Usage:** `nscp ->`

**Generated Code:**

```tsx
export interface ComponentProps {}

export default function Component(props: ComponentProps) {
  return;
}
```

### Component without props

**Usage:** `nsc ->`

**Generated Code:**

```tsx
export default function Component() {
  return;
}
```

### Component with children

**Usage:** `nscc ->`

**Generated Code:**

```tsx
export interface ComponentProps {
  children: React.ReactNode;
}

export default function Component({ children }: ComponentProps) {
  return <>{children};</>;
}
```

### Server component without props

**Usage:** `nssc ->`

**Generated Code:**

```tsx
import "server-only";

export default function ServerComponent() {
  return;
}
```

### Server component with props

**Usage:** `nsscp ->`

**Generated Code:**

```tsx
import "server-only";

export interface ServerComponentProps {}

export default function ServerComponent(props: ServerComponentProps) {
  return;
}
```

### Server component with children

**Usage:** `nsscc ->`

**Generated Code:**

```tsx

```

### Async server component without props

**Usage:** `nsasc ->`

**Generated Code:**

```tsx
export interface ServerComponentProps {
  children: React.ReactNode;
}

export default function ServerComponent({ children }: ServerComponentProps) {
  return <>{children};</>;
}
```

### Async server component with props

**Usage:** `nsascp ->`

**Generated Code:**

```tsx
import "server-only";

export interface ServerComponentProps {}

export default async function ServerComponent(props: ServerComponentProps) {
  return;
}
```

### Async server component with children

**Usage:** `nsascc ->`

**Generated Code:**

```tsx
import "server-only";

export interface ServerComponentProps {
  children: React.ReactNode;
}

export default async function ServerComponent({
  children,
}: ServerComponentProps) {
  return <>{children};</>;
}
```

### Client Component with props

**Usage:** `nsclp ->`

**Generated Code:**

```tsx
"use client";

export interface ClientComponentProps {}

export default function ClientComponent(props: ClientComponentProps) {
  return;
}
```

### Client Component without props

**Usage:** `nscl ->`

**Generated Code:**

```tsx
"use client";

export default function ClientComponent() {
  return;
}
```

### Client Component with children

**Usage:** `nsclc ->`

**Generated Code:**

```tsx
"use client";

export interface ClientComponentProps {
  children: React.ReactNode;
}

export default function ClientComponent({ children }: ClientComponentProps) {
  return <>{children};</>;
}
```

### Provider

**Usage:** `nsp ->`

**Generated Code:**

```tsx
"use client";

interface SampleProviderProps {
  children: React.ReactNode;
  value: string;
}

const SampleContext = React.createContext<string | null>(null);

function SampleProvider({ children, value }: SampleProviderProps) {
  return (
    <SampleContext.Provider value={value}>{children}</SampleContext.Provider>
  );
}

function useSample(): string {
  const sample = React.useContext(SampleContext);
  if (!sample) {
    throw new Error("useSample must be used within a SampleProvider");
  }
  return sample;
}

export { SampleProvider, useSample };
```

### Layout

**Usage:** `nsl ->`

**Generated Code:**

```tsx
export default function SampleLayout({
  children,
}: {
  children: React.ReactNode;
}) {
  return <>{children}</>;
}
```

### Template

**Usage:** `nst ->`

**Generated Code:**

```tsx
export default function Template({ children }: { children: React.ReactNode }) {
  return <>{children}</>;
}
```

### NextJS static metadata

**Usage:** `nssm ->`

**Generated Code:**

```tsx
import { Metadata } from "next";

export const metadata: Metadata = {
  title: "",
  description: "",
};
```

### NextJS dynamic metadata

**Usage:** `nsdm ->`

**Generated Code:**

```tsx
import { Metadata, ResolvingMetadata } from "next";

export async function generateMetadata(
  props: SampleProps, // same as page
  parent: ResolvingMetadata
): Promise<Metadata> {
  return {};
}
```

### NextJS middleware

⚠️ Typescript (.ts file) only

**Usage:** `nsm ->`

**Generated Code:**

```ts
import { NextResponse } from "next/server";
import type { NextRequest } from "next/server";

export const config = {
  matcher: [
    /*
     * Match all request paths except for the ones starting with:
     * - api (API routes)
     * - _next/static (static files)
     * - _next/image (image optimization files)
     * - favicon.ico (favicon file)
     */
    "/((?!api|_next/static|_next/image|favicon.ico).*)",
  ],
};

export function middleware(request: NextRequest) {
  // console.log(`Requesting ${request.url}`);
  const response = NextResponse.next();

  return response;
}
```
