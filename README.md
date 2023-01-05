<h2>Motivation</h2>
Play with middleware so i can use it for authorization

<h2>Implementation</h2>

Only middleware.ts is used - you can not choose other name. In this example every access to /about is redirect to /about-2

```typescript
import { NextResponse } from "next/server";
import type { NextRequest } from "next/server";

export function middleware(request: NextRequest) {
  return NextResponse.redirect(new URL("/about-2", request.url));
}

export const config = {
  matcher: "/about",
};

```


<h2>Open issues</h2>
<ul>
<li>The <a href='https://nextjs.org/docs/advanced-features/middleware#using-middleware'>documentation</a> suggest to put middleware.ts in the root or under src directory. It did not worked for src ,may be bacuse the project is not aware of this folder</li>
</ul>