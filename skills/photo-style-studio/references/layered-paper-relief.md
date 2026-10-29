# 分层剪纸浮雕 · Layered Paper Relief

## 目标与输入

把用户原片整体转译为手工裁切、层层叠放的哑光纸雕。主体轮廓、前后关系与光影仍可辨认，细节用纸片形状概括。与 paper-photo-collage 保留摄影核心不同，本分支让全景具有一致的纸材质。

输入 source_image；可选 reference_image、output_directory、用户指定画幅、色板和简化程度。参考图仅提供媒介语言，不替换原片内容。没有原片时先索取原片。

保真级别为 scene-faithful：允许生成式重绘和细节简化，不承诺原像素或物体数量逐项不变；人物数量、位置及关键主体仍须检查。选择本分支即允许纸雕化，不允许擅自改变季节或创造景物。

## 默认参数与审美

- canvas：原片比例与完整取景；保持主体比例，不拉伸。工具比例不精确时记录实际尺寸，不静默裁切补救。
- palette：从原片提取低饱和主色、亮部与阴影色；允许纸材质统一色调，保留原有物候、天气及主要光向。季节不明确时按可见特征；仅在必须判断时询问。
- relief：中等厚度，约 8–12 个主要空间层次作为起点，按场景复杂度调整，不机械限制纸片数量。
- edges：有手工细微起伏的清晰裁切边；局部少量纤维感，避免全部撕碎或毛边。
- surface：哑光纸纤维、可见薄纸厚度、轻微层间接触阴影。接触阴影服务于纸层空间，不能逆转原场景主要光向。
- typography：无字、无框、满幅；用户指定文字或纸面留白时再加入。

山体按原有山脊与坡面分层；树林将原有树群概括为纸剪轮廓；建筑保持透视、楼体与开口位置；水面使用顺着原波纹的横向纸片并保留倒影对应关系；天空按实际云团简化成宽纸层，不新增太阳。小人物保留人数、位置与动作轮廓，不补造面孔。

## 执行与提示词

1. 查看原片，列出关键轮廓、主体位置、空间层次、色板和光影。明确原片与风格参考的角色。
2. 将下方模板中的场景描述替换为实际观察，删除不适用的物体描述；已有用户设置优先于默认值。
3. 用支持参考图编辑的图像工具，将原片作为必需图像输入生成。缺少工具时交付确定版提示词，注明图片尚未生成。
4. 与原片并排检查，再按交付规范保存图片、提示词和真实检查记录。明显偏离主体或变成平面插画时针对问题修订一次；仍不满足则展示限制，等待用户决定。

```text
Transform the provided photograph into a sophisticated hand-cut layered paper relief artwork, viewed straight on. Preserve the complete original composition, [original aspect ratio], key subject proportions and spatial relationships: [observed silhouettes, object positions and foreground/midground/background].

Translate the scene into carefully nested sculptural paper planes, using roughly 8–12 major depth layers as a starting point and adapting to the subject. Show subtle paper thickness, crisp organic hand-cut edges, tactile matte fibers and delicate contact shadows between layers. Use a restrained palette derived from the source: [source colors]. Preserve the source's visible season, weather, main light direction and distribution of sunlit and shadowed areas.

[Scene-specific material translation: mountains as nested slope planes; existing tree groups as cut silhouettes; architecture as perspective-correct paper shapes; water as layered horizontal shapes retaining reflections; actual clouds as broad paper forms. Include only what exists in the source.]

The whole scene should read as a crafted physical paper relief, with clear depth and coherent paper material throughout. Simplify fine detail while retaining recognizable scene structure. Full-bleed original framing, no text or frame unless explicitly requested. Do not invent scenery or seasonal elements. Deliver one finished image, not a mockup on a tabletop.
```

## 专属验收

- 对照原片检查主要轮廓、主体比例、前后关系及取景完整性；人物存在时核对人数和位置。
- 纸层厚度、边缘、纤维和接触阴影可辨认，全景媒介统一；不是平面矢量填色、照片贴纹理或水彩。
- 简化保留场景辨识度；没有擅加地标、太阳、雪或季节变化。
- 原比例近似保持、无意外标题与相框。报告实际比例和未解决差异。
- 只交付实际生成的文件；单张栅格纸雕效果不称为可编辑分层文件或实体纸雕制作图。
