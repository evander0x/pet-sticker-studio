---
name: pet-sticker-flat-cartoon
description: Use when turning a real pet into stickers that must match the supplied clean flat-cartoon reference style.
---

# 宠物扁平贴纸风

使用这套风格把真实宠物制作成透明底表情包。每次生成前必须同时加载用户宠物照片、9宫格总览参考和单张细节参考。

## 画风定义

- 深棕色或深色平滑粗描边，线宽稳定
- 大面积平整色块，细节少而清晰
- 五官高度简化，圆润、规整、图标化
- 阴影很少，只保留少量高光或局部色块
- 道具和文字牌可以几何化、醒目、易读
- 透明底，主体完整，保留少量透明安全边距

## 参考素材

- `assets/references/flat-cartoon-9-grid.png`：扁平线条、平整色块、九宫格排版和动作密度参考
- `assets/references/flat-cartoon-single.png`：单个角色的线宽、五官、色块边缘和道具细节锚点

参考图只锁定画风，不复制其中的动物；宠物的物种、脸型、毛色、斑纹、耳朵、眼睛和独有标记以用户照片为准。

## 生成约束

先调用 `pet-identity-sticker` 提取并确认宠物身份特征卡，再生成表情。每张都重复身份卡，不要只引用上一张生成图。

提示词必须包含：

```text
Match the supplied clean flat-cartoon sticker references: smooth dark-brown bold outlines,
simple rounded geometry, flat pastel color blocks, minimal shading, simplified facial
features and clear icon-like composition. Keep the user's pet identity unchanged. Change
only the pose, emotion, props and approved text. Transparent background, complete subject,
no watermark, no rough crayon texture, no painterly finish, no photorealistic scene,
no generic replacement animal.
```

每次生成前确认身份照片、`flat-cartoon-9-grid.png` 和 `flat-cartoon-single.png` 都已进入本次任务。9宫格负责整体构图与动作语言，单张图负责局部线条和细节；任一参考图未加载时暂停生成。每张都重新使用原始身份照片和两张风格参考图，不得只依赖上一张结果。

生成 1 张试样后，先检查是否同时满足“宠物像本人”和“像参考画风”，再批量生成。
