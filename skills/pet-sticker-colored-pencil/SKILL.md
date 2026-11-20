---
name: pet-sticker-colored-pencil
description: Use when turning a real pet into expressive stickers in the supplied soft, detailed colored-pencil illustration style.
---

## 默认使用方式

用户只需上传一张宠物照片，并说“用彩铅写实手绘风生成九宫格表情包”。先生成 3×3 九宫格作为预览，确认宠物辨识度、画风和动作后，再把 9 个格子分别生成 9 张透明底单张表情包。九宫格图片默认是预览/宣传参考，不是最终交付；只有用户明确要求九宫格成品时才直接交付九宫格。

# 宠物彩铅写实手绘贴纸风

把真实宠物转换成有丰富动作和表情的彩铅手绘贴纸。每次生成前必须同时加载宠物照片、9宫格总览参考和单张细节参考。

## 画风特征

- 以细密、方向明确的彩铅短线表现毛发，保留纸面颗粒与手绘笔触
- 柔和自然的毛色层次，阴影轻、颜色不过度饱和
- 轮廓线有轻微抖动和粗细变化，不是矢量描边
- 头脸和身体结构比简笔风更具体，但仍保持可爱、贴纸化
- 表情、姿势和视角丰富，配少量轻快的手绘动作符号
- 白色或浅色背景，九宫格均匀留白；不加边框、分隔线或水印

## 参考素材

- `assets/references/colored-pencil-realistic-9-grid.png`：彩铅笔触、柔和配色、宠物比例、动作变化和九宫格密度参考
- `assets/references/colored-pencil-realistic-single.png`：单个角色的彩铅短线、毛发叠色、轮廓变化和道具细节锚点

参考图只决定画法、笔触和表达气质，不复制其中的狗或具体身份。宠物物种、毛色分布、斑纹、脸型、耳朵、体型、尾巴和长期配饰以用户提供的身份照片为准。

## 每次生成前的硬性检查

确认身份照片、`colored-pencil-realistic-9-grid.png` 和 `colored-pencil-realistic-single.png` 都已进入本次任务。9宫格负责动作、构图和整体密度，单张图负责彩铅短线、纸感颗粒、毛发叠色和轮廓细节；任一参考图未加载时暂停生成。每张都重新使用原始身份照片和两张风格参考图，不得只依赖上一张结果。

## 身份与动作

由 `pet-identity-sticker` 在内部提取身份约束，不要求普通用户先确认身份卡。固定身份辨识点，不固定照片中的姿势、视角、眼睛开合、嘴巴状态或情绪。九宫格预览至少安排五类明显不同的动作/身体朝向；可包括趴卧、侧躺、行走、伸懒腰、跳跃、回头、探头、翻滚等，按动物结构选择合适动作。每格姿势要清晰，保持物种正常肢体数量，不出现重复肢体。

## 提示词要求

```text
Match the supplied colored-pencil pet sticker reference: soft detailed colored-pencil
fur built from visible directional strokes, subtle paper grain, natural muted colors,
gentle hand-drawn contour variation, expressive but believable pet anatomy, playful
sticker expressions and light motion accents. Preserve only the user's pet identity;
do not freeze the source photo pose. Vary body pose, orientation, view angle and
expression across the grid, with at least five distinct action families. Keep correct
species anatomy and limb count in every cell. Clean white background, even spacing,
no grid dividers, no border, no watermark, no glossy vector finish, no photorealistic
scene, no generic replacement animal.
```

生成后检查两件事：是否仍然能认出这只宠物；是否呈现参考中的彩铅短线、纸感颗粒和柔和手绘层次。若毛发变成光滑渐变或过度写实，减少渲染强度并加强可见彩铅笔触约束。
