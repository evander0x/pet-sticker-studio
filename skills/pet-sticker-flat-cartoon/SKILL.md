---
name: pet-sticker-flat-cartoon
description: Use when turning a real pet into stickers that must match the supplied clean flat-cartoon reference style.
---

# 宠物扁平贴纸风

使用这套风格把真实宠物制作成透明底表情包。生成前必须同时使用：用户宠物照片作为身份参考，以及本 skill 的 `assets/references/` 作为画风参考。

## 画风定义

- 深棕色或深色平滑粗描边，线宽稳定
- 大面积平整色块，细节少而清晰
- 五官高度简化，圆润、规整、图标化
- 阴影很少，只保留少量高光或局部色块
- 道具和文字牌可以几何化、醒目、易读
- 透明底，主体完整，保留少量透明安全边距

## 参考素材

- `assets/references/pet-01-received.png`：宠物扁平卡通主体和牌子构图参考
- `assets/references/03-top-right-received.png`：简洁线条、平整色块和文字牌参考

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

生成 1 张试样后，先检查是否同时满足“宠物像本人”和“像参考画风”，再批量生成。
