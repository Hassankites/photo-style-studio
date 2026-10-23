# 交付与验收

每次任务使用独立输出目录，建议包含：

- `final.png`：原始观看方向、尺寸和比例的无损成品。
- `overlay.png`：与成品同尺寸、可直接对齐的透明叠层。
- `layers/`：实际使用的地图、标签、标记及可选纹理；保留可用的 SVG 中间件。不创建空图层凑数。
- `manifest.json`：可复现信息。

manifest 必需字段：branch、preservation、source_filename、source_sha256、source_size、output_size、orientation_handling、color_profile_handling、location_label、location_precision、marker_meaning、map_sources（来源 URL 或数据标识、检索日期、许可、署名）、outputs、checks。

未使用的未知值写 null，不编造。manifest 默认不包含绝对本机路径、原始 EXIF 或未获公开授权的 GPS。地图所需公开署名按实际许可显示在成品或指定载体中；不能用“极简设计”移除必要署名。

checks 对每项记录 pass / fail / not_run 和简短证据：

1. 原片文件哈希未变。
2. 观看方向、输出尺寸、比例保持一致。
3. 合并叠层 alpha=0 的区域与规范化基准逐像素一致；若没有这样的像素，不能宣称检查通过。
4. 全图与局部预览：无主体遮挡、字形破损、明显色偏或矩形地图底板。
5. 地名与地图来源一致，区域标记不暗示精确拍摄位置。
6. 图层尺寸一致，叠层确有透明通道，来源与许可说明齐全。

给用户展示成品、可下载文件和位置精度说明。若有未运行检查，明确写出。成功交付不等于发布；不自动创建远程仓库或上传照片。
