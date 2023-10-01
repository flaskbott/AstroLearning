---
title: 添加UI框架
author: 小大卫
description: "学习了一些 Astro 后，我根本停不下来！"
image:
  url: "https://docs.astro.build/assets/arc.webp"
  alt: "Thumbnail of Astro arcs."
pubDate: 2022-07-08
tags: ["astro", "blogging", "learning in public", "successes"]
layout: "../../layouts/MarkdownPostLayout.astro"
---

在学习 Astro 大约一周后，我决定尝试些新的东西。我编写并导入了一个小组件！

## 添加 preact 框架

npx astro add preact

## 编写 preact 代码以实现 岛屿 交互

```jsx
import { useState } from 'preact/hooks';

export default function Greeting({messages}) {

  const randomMessage = () => messages[(Math.floor(Math.random() * messages.length))];

  const [greeting, setGreeting] = useState(messages[0]);


  return (
    <div>
      <h3>{greeting}! Thank you for visiting!</h3>
      <button onClick={() => setGreeting(randomMessage())}>
        换一个

      </button>

    </div>

  );

```
