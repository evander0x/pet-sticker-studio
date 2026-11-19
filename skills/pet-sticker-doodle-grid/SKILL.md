---
name: pet-sticker-doodle-grid
description: Use when turning a real pet into simple doodle-style stickers or a 3x3 expression sheet matching the supplied lightweight hand-drawn reference.
---

# 宠物简笔九宫格风

使用这套风格把真实宠物制作成简笔涂鸦表情包，尤其适合 3×3 九宫格组图。身份特征来自用户照片，画风与排版来自本 skill 的参考图。

## 画风定义

- 细而略带手绘感的深色线稿，轮廓简洁，不追求复杂毛发纹理
- 白色或浅色主体，大面积留白，少量粉色腮红和柔和色块
- 五官圆润、简化、表情清楚；允许夸张眼泪、星星、爱心和问号
- 道具使用少量干净色块，不做厚重阴影和立体渲染
- 组图优先采用 3×3 均匀排列、白底、细边框和宽留白
- 每格只放一个同一宠物及一个简单动作/道具

## 参考素材

- `assets/references/IMG_7452.JPG`：画风、九宫格排版、留白和动作密度的唯一参考

参考图只锁定画风和组图结构，不复制其中的猫；宠物的物种、脸型、毛色、斑纹、耳朵、眼睛、配饰和独有标记以用户照片为准。

## 生成约束

先调用 `pet-identity-sticker` 提取并确认宠物身份特征卡。每格都必须保留身份卡中的关键特征，不能因为简化画风而变成通用动物。

组图提示词应明确：

```text
Match the supplied reference sheet: simple thin hand-drawn doodle outlines,
minimal detail, lots of clean white space, soft pastel accents, round simplified
facial features, small expressive props, and an evenly spaced 3x3 grid if a sheet
is requested. Keep the user's pet identity and unique accessories unchanged.
No heavy crayon texture, no thick glossy vector outline, no photorealistic scene,
no watermark, no extra animals, no crowded background.
```

生成九宫格时先固定网格和每格动作清单，再检查九格中的宠物是否仍然是同一只；若用户需要单张上传，再将每格独立导出为 1:1 透明 PNG。
