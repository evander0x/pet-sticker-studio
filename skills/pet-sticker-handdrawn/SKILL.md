---
name: pet-sticker-handdrawn
description: Use when turning a real pet into stickers that must match the supplied hand-drawn crayon or colored-pencil reference style.
---

## 默认使用方式

用户只需上传一张宠物照片，并说“用手绘风生成九宫格表情包”。先生成 3×3 九宫格作为预览，确认宠物辨识度、画风和动作后，再把 9 个格子分别生成 9 张透明底单张表情包。九宫格图片默认是预览/宣传参考，不是最终交付；只有用户明确要求九宫格成品时才直接交付九宫格。

# 宠物手绘贴纸风

使用这套风格把真实宠物制作成透明底表情包。每次生成前必须同时加载用户宠物照片、9宫格总览参考和单张细节参考。

## 画风定义

- 深棕色、略粗且不规则的手绘线稿
- 彩铅/蜡笔颗粒明显，填色有轻微深浅和出界感
- 柔和粉彩色，白色毛发不是纯白，允许有淡灰、米色或粉色笔触
- 五官和毛发细节较丰富，动作和表情可以夸张
- 爱心、星星、汗滴、闪光等装饰也要像手绘涂鸦
- 透明底，主体完整，保留少量透明安全边距

## 参考素材

- `assets/references/handdrawn-9-grid.png`：手绘线条、蜡笔颗粒、九宫格排版和动作密度参考
- `assets/references/handdrawn-single.png`：单个角色的手绘轮廓、颗粒、叠色和边缘细节锚点

参考图只锁定画风，不复制其中的猫；宠物的物种、脸型、毛色、斑纹、耳朵、眼睛和独有标记以用户照片为准。

## 生成约束

由 `pet-identity-sticker` 在内部提取身份约束，不要求普通用户先确认身份卡。九宫格预览阶段先固定 9 个动作和情绪；用户确认后，每张单图都重复完整身份约束，不要只引用上一张生成图。

提示词必须包含：

```text
Match the supplied hand-drawn sticker references: irregular dark-brown sketch outlines,
visible crayon/colored-pencil grain, soft pastel fills, imperfect handmade edges and
playful doodle accents. Keep the user's pet identity unchanged. Change only the pose,
emotion and props. Transparent background, complete subject, no watermark, no glossy
vector finish, no photorealistic scene, no generic replacement animal.
```

每次生成前确认身份照片、`handdrawn-9-grid.png` 和 `handdrawn-single.png` 都已进入本次任务。9宫格负责整体动作和装饰语言，单张图负责纹理、线条和叠色；任一参考图未加载时暂停生成。每张都重新使用原始身份照片和两张风格参考图，不得只依赖上一张结果。

阶段一检查九宫格是否同时满足“宠物像本人”和“像参考画风”；用户确认后，再按格子逐张生成，不把九宫格直接当作最终单图。
