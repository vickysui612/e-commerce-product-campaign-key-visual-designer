# 电商主视觉 Skill 运行提示（中文）

使用 `$e-commerce-product-campaign-key-visual-designer`，读取本包 `SKILL.md`，确认版本 `bilingual-four-gate-20261015`。不沿用会话缓存中的旧规则。以我指定的项目为 PROJECT_ROOT；按课程硬规范、多来源事实台账、产品适配方向、真实文字测量和独立 Grounding Pass 执行。

先检查实际可读取的文本、图片、网页和视频资料及可用生成/排版工具。建立来源台账、事实与冲突表、必上图/背景/禁用信息、原商品与 Logo 原件快照及双语文案清单；缺少关键资料时列明待确认项，不猜测价格、参数或优惠。未指定规格时以中英各一张 4:5 PNG（建议 1600×2000）为默认，具体要求覆盖默认。

依次执行四个人工审查节点：**A 信息确认 → B 风格意向 → T 文字排版与促销信息 → C 最终验收**。资料齐全时 A、B 可同次展示，但分别记录答复。B 提供 2–3 个传播策略不同的方向。制作并自检实际中英候选图后，T 展示全图、手机缩略图、文字/价格/日期/CTA 局部以及逐字文案和实际字体字号；T 通过后，C 展示同一版本的完整成图。冻结候选 PNG，T、C 各记录中英 SHA-256、真人答复和版本。任何改图或重新编码都重置 T、C 和受影响的视觉 QA；没有真实答复时保持 PENDING。只有我明确授权跳过某节点时才记录该节点 waiver，不把执行者检查写成人工通过。
如果现有 brief/manifest 是 schema1，先依 references/project-schema.md 迁移到schema2并备份，保留原文、字体配置和原件哈希；待补来源/方向/人工结论不伪造。使用本目录 scripts/preflight.py 验证，不以 preflight_legacy.py 的结果代替新版验收。旧图遭用户指出接触问题时，必须重新Grounding Pass并重置该项QA，不继承旧PASS。本提示是可复用执行入口，具体是否生成按当前用户任务，不继承历史任务范围。通用代码只调用 SKILL_ROOT/scripts/，按 references/portable-execution.md 使用本次 brief、摄影、检查、修复与语言布局参数，不 import 历史案例工作目录。仅更新或配置测试时不调用模型、不生成海报。
执行前按新语义层级整理文案；多行主标题整组同向，卖点icon+text默认集中一个模块，优先品牌色实心圆底+高对比线性图标+H3/Body双行文字；使用feature_module实测整组高度并共用双语圆径、图形尺寸/线宽/间距及垂直居中，不四处分散，不逐条缩字/放大图标，价格与CTA协调但可独立，默认轻量展示，不默认底部大色带。生成前完成相机/材质、品牌环境配色、道具层级与锚点计划；palette须包含五类色彩角色与原Logo/商品/材质/受众/场景/主题分析，采用Logo色时至少一处环境呼应。Color QA逐项记录六项证据并执行隐藏Logo检查；仅文字用品牌色不得PASS。按references/scene-workflow.md默认执行unified_workflow prepare→实际原图驱动联合生成→ingest→原件对照→accept与Grounding检查；有据例外才用分层合成。读取references/typography.md和design.md，完成headline_motion、promotion_composition、color_harmony、perspective_material、prop_hierarchy、typeface_fit、unified_product_identity、photographic_unity、information_cohesion实际看图检查，不能套上一商品版式。

默认用真实原商品图作为输入联合规划商品、承载面、光影和场景，再用原 Logo 文件与确定性文字排版完成中英版本。若保真或工具条件使联合生成不可行，记录证据后采用分层备选。检查商品身份、自然接触、品牌环境配色、文字测量、双语一致性及实际像素。使用本包 `scripts/preflight.py` 和 `scripts/review_binding.py` 检查当前项目；脚本检查不能代替看图与真人审查。最终交付成图、简短设计依据和真实的未解决问题。