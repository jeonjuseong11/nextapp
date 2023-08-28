# **Next.js 13 정리 Repository**

## **설치 및 프로젝트 생성**

1. Node.js와 VSCode 설치 후 진행
2. 프로젝트 저장 할 폴더 생성
3. 프로젝트 생성 (npx 사용)

현재폴더의 nextjs의 개발환경을 만드는 명령어

```bash
npx create-next-app@latest .
#@는 버전을 설정
#.은 현재 폴더에서 진행하겠다를 의미
```

해당 명령어를 입력하면 밑에 질문들이 나오는데 해당 질문들은 원하는 프로젝트에 따라 변경해 주면 된다

```
✔ Would you like to use TypeScript? … No / Yes
✔ Would you like to use ESLint? … No / Yes
✔ Would you like to use Tailwind CSS? … No / Yes
✔ Would you like to use `src/` directory? … No / Yes
✔ Would you like to use App Router? (recommended) … No / Yes
✔ Would you like to customize the default import alias? … No / Yes
```

13버전 이전에는 Page Router를 사용했고  
13버전 이후에는 App Router를 사용함

## **프로젝트 실행**

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```

## **샘플 앱 세탁**

### src/app/layout.js

웹 페이지의 골격을 구성함

```js
import "./globals.css";
import { Inter } from "next/font/google";

const inter = Inter({ subsets: ["latin"] });

export const metadata = {
  title: "Create Next App",
  description: "Generated by create next app",
};

export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <body className={inter.className}>{children}</body>
    </html>
  );
}
```

해당 코드에서 불필요한 부분 제거

```js
import "./globals.css";

export const metadata = {
  title: "Create Next App",
  description: "Generated by create next app",
};

export default function RootLayout({ children }) {
  return (
    <html>
      <body>{children}</body>
    </html>
  );
}
```

### src/app/page.js

latout.js안에 {children}에 들어가는 부분  
이것도 역시 불필요한 코드를 제거

```js
import Image from "next/image";

export default function Home() {
  return <>Hello, Nextjs!</>;
}
```

### src/app/global.css

여기 스타일 또한 모두 제거하게 되면 개발할 준비가 완료되게 된다
