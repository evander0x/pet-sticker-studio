# Pet Sticker Studio

真实宠物转表情包的独立项目。

## 工作内容

- 先从真实照片提取宠物身份特征卡
- 再选择一种画风生成九宫格或单张表情包
- 保留宠物的固定辨识特征，同时允许眼睛、嘴巴、姿势和情绪变化
- 生成结果放在 `generated/`，每只宠物的资料放在 `pets/`

## 画风 skills

- `skills/pet-sticker-handdrawn`：手绘蜡笔 / 彩铅风
- `skills/pet-sticker-flat-cartoon`：简洁扁平卡通风
- `skills/pet-sticker-doodle-grid`：简笔涂鸦九宫格风
- `skills/pet-identity-sticker`：身份特征提取与一致性约束

## 目录约定

```text
pet-sticker-studio/
├── skills/       # 身份与画风 skills，含必要参考图
├── pets/         # 宠物照片、身份特征卡、确认记录
├── generated/    # 九宫格和单张生成结果
└── docs/         # 生成批次和验收记录
```
