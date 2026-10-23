# 新分支接口

新分支追加为 `references/<branch-id>.md`，然后在 SKILL.md 分支表添加触发场景和链接；仅实际实现的分支进入 description。不要预先创建空分支。

每个分支应说明：目标、输入、默认参数、保真级别、素材来源、构图与审美规则、执行方式、工具缺失时的降级、分支专属验收。

复用共同输入：source_image、reference_image、branch、preservation、output_directory。地点等字段只属于需要它们的分支。原片与参考图角色必须保持明确。

默认继承 strict 原图保护与 delivery-contract。需要重绘、调色或裁切的新风格必须显式声明不同保真级别并由用户选择，不能放宽所有分支。

新分支验收至少覆盖正常输入、信息缺失、工具缺失和与保真规则冲突四类场景。记录实际测试结果，不能将用例表当作已通过证据。
