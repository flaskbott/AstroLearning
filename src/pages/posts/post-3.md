---
title: 遇到的问题
author: 小大卫
description: "我遇到了一些问题。"
image:
  url: "https://docs.astro.build/assets/rays.webp"
  alt: "Thumbnail of Astro rays."
pubDate: 2022-07-15
tags: ["astro", "learning in public", "setbacks", "community"]
layout: "../../layouts/MarkdownPostLayout.astro"
---

## 期间遇到的问题

markdown 文件在编译运行后显示乱码

```markdown
鎴戠殑绗  竴绡囧崥瀹 ㈡ 枃绔 �
鍙戣〃浜庯細 2022-07-01

娆 ㈣ 繋鏉ュ埌鎴戝  涔犲叧浜 � Astro 鐨勬柊鍗氬  锛佸湪杩欓噷锛屾垜灏嗗垎浜  垜寤虹珛鏂扮綉绔欑殑瀛︿範鍘嗙 ▼ 銆 �

鎴戝仛浜嗕粈涔 �
瀹夎  Astro 锛氶  鍏堬紝鎴戝垱寤轰簡涓 € 涓  柊鐨 � Astro 椤圭洰骞惰  缃  ソ浜嗘垜鐨勫湪绾胯处鍙枫 €�

鍒朵綔椤甸潰锛氱劧鍚庢垜瀛︿範浜嗗  浣曢 € 氳繃鍒涘缓鏂扮殑 .astro 鏂囦欢骞跺皢瀹冧滑淇濆瓨鍦 � src/pages/ 鏂囦欢澶归噷鏉ュ埗浣滈〉闈 €€�

鍙戣〃鍗氬  鏂囩珷锛氳繖鏄  垜鐨勭  涓 € 绡囧崥瀹 ㈡ 枃绔狅紒鎴戠幇鍦ㄦ湁鐢 � Astro 缂栧啓鐨勯〉闈 ㈠ 拰鐢 � Markdown 鍐欑殑鏂囩珷浜嗭紒
```

## 解决方案

## 自定义 Astro Layout

在 Astro 中，你可以创建自定义的布局文件来渲染 Markdown 文件。这允许你定义 Markdown 文件的外观和布局。以下是一些示例步骤：

在你的项目中创建一个名为 layouts 的目录（如果没有的话）。
在 layouts 目录中创建一个新的布局文件，例如 markdown-layout.astro。
在布局文件中定义你的页面结构，包括 <meta charset="UTF-8"> 标签以确保字符编码正确。

```markdown
---
---

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Your Page Title</title>
    <!-- 其他头部内容 -->
</head>
<body>
    <header>
        <!-- 你的页眉内容 -->
    </header>
    <main>
        <slot></slot> <!-- Markdown 内容将在这里插入 -->
    </main>
    <footer>
        <!-- 你的页脚内容 -->
    </footer>
</body>
</html>
```

## 关联 Markdown 文件与自定义布局

```markdown
---
layout: layouts/markdown-layout.astro
---

# Markdown Content
```

这样，Markdown 文件将与你的自定义布局关联，并使用你定义的 HTML 结构进行渲染。
