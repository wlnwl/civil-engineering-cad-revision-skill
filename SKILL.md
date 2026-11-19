---
name: civil-engineering-cad-revision-skill
description: 面向中国土木工程毕业设计的建筑 CAD 改图，含草图对照、国内规范核验、确认后出图及完整 CAD 设计与自动化附录。
---

# 土木工程毕业设计 CAD 改图

本发布版以建筑改图主流程为准。附录是按需查阅的技术资料；示例路径为占位示例，历史测试不代表当前环境或规范要求。附录示例不得跳过确认、改动原图、清理用户文档或终止软件进程。

## 按阶段查阅资料

- [设计指导](#appendix-a-cad-designer)：查专业制图、图层、标注、块、模板、打印和验证章节。先区分建筑、机械等专业，不把一个专业的默认值套到另一个专业。
- [自动化手册](#appendix-b-cad-automation)：按需查 CAD 接口、二维绘图、三维建模、批处理、格式转换及软件兼容性。示例仅供参考；不可当成执行授权，也不可假定历史实测环境、脚本或接口在当前机器仍可用。

## CAD 草图审查

### 出图字体：先用规范或官方字体

- 正式 CAD、PDF 和图片优先采用适用制图规范明确指定的字体；规范未指定具体字库时，优先采用项目或出图单位官方模板指定且符合规范的字体。用出图软件实际可加载的字体核对可用性，不只看系统字体列表；已有图纸样式符合要求时保留。
- 指定字体本机没有或 CAD 无法加载时，从本机可用字体中选与原要求接近的替代，核对中文字形、数字、尺寸及特殊符号覆盖，并保持字高、字宽和排版尽量一致。不擅自下载或安装字体。若规范明确要求且不允许替代，应把缺字库标为待处理，不能把替代版当作合规正式交付。
- 在 CAD 及实际导出的 PDF／PNG 上复核文字、尺寸和符号有无乱码、缺字、重叠或裁切。使用替代字体时，在交付说明中列出原要求字体、实用字体及受影响的样式或图纸。

### CAD 转图片：草图审阅与交付预览

- 从 CAD 几何渲染清晰的 PNG，不用生成式图片替代线稿或尺寸标注。DWG 优先用当前 CAD 的布局打印输出 PDF 再栅格化；DXF 可用本地 DXF 渲染器按固定页面范围生成 PNG。先确认当前工具可用，只读打开底图或使用工作副本，不改原图，不擅自上传图纸。
- 审阅阶段可渲染既有底图和独立的方案预览，不提前生成正式 DWG／DXF。改前、改后分别渲染并拼成对照 PNG，统一视角、裁切范围、比例和输出像素；标出版本及改动编号，必要时补局部放大图。
- 先实际打开 PNG 验证无空白、裁切、错位、文字乱码或线条丢失，再把图片直接展示给用户。用几何或标注数据核验关键尺寸，不以像素相似度代替尺寸校核。批准后如需交付图片，从最终 CAD 重渲染，并与相应图纸版本一起交付。若无法可靠渲染，说明限制，不把示意图当成 CAD 实际输出。
- 参考 [autocad-dwg-redraw-skill](https://github.com/pengxiaoan/autocad-dwg-redraw-skill) 中的固定页面 DXF 预览和配准对比思路。该仓库主要是图片转 CAD 与 DWG 重建；这里仅吸收其预览与对比方法，不依赖仓库脚本。

### 改图必须给改前／改后对照

- 每版改图草图都提供可视对照，不能只给改后图或文字说明。优先左右并排：左侧“改前（底图）”，右侧“改后（拟改）”；采用相同范围、方向和比例。局部太小时补放大图，并标明所在楼层、轴线或构件。没有可靠底图时，注明缺失并索取，不虚构改前状态。
- 给每处改动标同一个编号（如 M01），在两侧对应位置标出。用图例区分保留、新增、删除和移位；除颜色外，再用不同线型或文字标识。尺寸变化标出前后数值及单位；未核实的数据明确标记。
- 随图附同编号清单：编号｜位置｜改前｜改后｜变化或影响｜修改理由及规范依据。涉及规范时列出规范编号、版本、具体条款及官方链接；不涉及规范的注明实际理由。
- 标注本轮草图版本和对照基准。迭代时另指出相对上一版草图改了哪些。请用户按编号反馈或确认整版；仅确认个别项不视为同意正式出图。

### 国内建筑与制图规范怎么查

- 优先查[住房城乡建设部门户网站](https://www.mohurd.gov.cn/)，按标准号或名称找发布公告、正文附件、局部修订和废止通知。搜索示例：`site:mohurd.gov.cn "住宅项目规范" "公告"`。一般国家标准及行业、地方标准题录可查[全国标准信息公共服务平台](https://std.samr.gov.cn/)；能否获取全文以页面为准，工程建设标准在平台查不到时回到主管部门查询，不据此判断废止。
- 项目所在地明确后，查当地省级住建厅和市级住建、自然资源或规划主管部门官网的地方标准、规划技术规定及实施通知。检索用“项目地名 + 事项 + 地方标准/技术规定”，核对适用区域与工程类型。
- 草图前按项目性质筛选会影响布局的要求，如住宅、防火疏散、无障碍、采光和当地规划；出图前再核对本次涉及的制图、标注等标准。用“标准号 + 局部修订/废止/实施”复查版本、生效日期、过渡规定，以及是整本废止还是仅部分条文废止。按公告和正文判定强制性与适用条件，不以网盘、转载或搜索摘要作为依据。
- 在草图和交付说明中记录实际采用的标准名称、编号与版本、具体条款、官方链接，以及对设计的影响。未核实的条文或尺寸标为待核实，不宣称符合规范；若复核要求修改已确认的设计，先发新版草图重新确认。

### 改图时：逐项列出规范依据

- 每版改图草图随附“修改与规范依据”清单，正式交付时同步更新。逐项列出：修改位置与内容｜修改前后（适用时列尺寸）｜规范名称、编号及版本、具体条款｜官方链接｜条款对本项修改的影响。
- 只列实际用于该项修改的条款。若是用户偏好或设计优化，并非规范要求，就注明原因，不强行套条文；若依据尚未核实，标为“待核实”，不宣称符合规范。

### 画草图前：联网找类似案例

- 每次提出新设计方案前先联网检索。用项目类型、规模或层数、场地和朝向、功能、结构或改造限制等已知条件组合搜索；优先找设计机构公开项目、政府公开项目资料等可核实来源。
- 选出最接近的案例，附项目名称和来源链接，说明哪些条件相似、哪些不同，以及哪些做法可借鉴、哪些不宜照搬。案例用于比较布局和设计思路，不作为规范依据，也不把案例尺寸当作本项目尺寸。
- 没找到足够相似的案例时，说明查过哪些条件及可参考的局部做法；无法联网时，明确告知用户，不把未查证的案例当成已查到的结果。展示草图时简述案例如何影响本方案。

### 草图与出图流程

1. **先展示方案。** 从资料提取用途、单位、已知尺寸和限制，必要时提问，其余假设标为暂定或待核实。展示一个推荐方案的可视草图，简述设计理由，标注关键轮廓、名称、尺寸或轴线；非按比例时注明。预览文件与正式图分开，不修改原图。给草图标版本（如 V1），说明待核实事项及确认后拟生成的图纸范围和格式，然后结束本轮等待回复。
2. **等用户明确确认。** 只有用户明确同意按当前版本生成（如“就按这版生成”），才能创建或修改正式 CAD 图纸、运行正式出图自动化、导出正式交付物。初始委托、沉默、“看到了”或询问细节都不是确认。用户提出修改时，先展示新版并重新等待确认；旧版批准不延续至新版。
3. **按确认版本出图。** 先核实仍缺失的出图必需条件，勿自行补定关键尺寸或单位。按确认范围生成，默认另存，不覆盖原图。若需改变已确认的设计，回到草图阶段。复核输出是否能打开、单位和关键尺寸是否一致，并说明成果位置及未核实事项。涉及结构、消防等安全事项的草案不得作为施工依据。

## 统一工作流

1. **确定设计依据。** 核对输入、单位、已知尺寸、专业、项目所在地及交付物。设计或改图时，先联网查类似条件的方案和适用规范，再形成草图。来源资料中的标准号和参数是查询线索，不是现行规范已核验的结论。
2. **给草图，等待确认。** 展示带版本号的可视草图、案例借鉴与差异、待核实事项及出图范围。改图时逐项列出改前改后、实际采用的规范名称和版本、具体条款、官方链接及影响；非规范性调整说明原因。未明确同意当前版本前，不生成正式 CAD、不改原图。方案变化后重新确认。
3. **自动化执行。** 按获准方案选择与当前 CAD 产品、版本和文件格式兼容的接口。先在副本或新文档验证，再执行正式绘制、标注与导出。核对目标文档；不默认关闭用户文档、清理别的任务的对象、覆盖原件或丢弃未保存更改。仅查看、解释或转换且不改变设计时，不强制走草图审查。
4. **复核交付。** 验证文件可打开及单位、关键几何、图层、标注和布局；有出图要求时检查实际导出结果，不把命令提交成功当成验收。交付时列出产物、验证结果及未核实事项。若复核发现需改变已确认的设计，退回草图阶段。


## 机械 CAD：建模与交付验证

参考 [AutoCAD-skills 的机械制图工作流](https://github.com/beiming183-cloud/AutoCAD-skills/tree/main/skills/mechanical-drafting-gbt)。本节适用于机械零件、装配与产品图，不把机械制图约定套用到建筑图。仍须先查案例和适用规范、给出草图及改动对照、等用户确认后才正式出图。

- **参数来源。** 明确单位、基准、已确认尺寸及其来源；各视图从同一模型或同一参数骨架派生。材料、公差、配合、粗糙度和采购件包络缺依据时标为待定，不自行定值。按适用 GB/T 和项目模板核验投影法、线型、标注及标题栏，不把上游示例当规范条文。
- **执行回读。** 核实本机实际可用的 CAD 接口；在副本或新文档执行。按关键对象记录“预期值／实际回读值／差异”，核对坐标、尺寸、类型与单位。发现偏差先暂停并定位原因，复核通过再继续；接口返回成功不算验收。
- **几何与跨视图。** 逐处定位悬空端点、近接未接、意外交叉和未闭合轮廓，区分真实问题与有意留缝或断线。检查主视、俯视、剖视中同一特征的相对位置和尺寸是否一致；装配任务按需查干涉、间隙及运动范围，未检查的不标为通过。
- **出图与发布。** 对照标题栏比例检查实际导出 PDF；适合页面不能当作固定比例打印。交付按任务记录图纸版本、关联模型或 BOM、验证证据和待定项。几何检查通过不代表可制造、安全认证或正式放行；有产品安全或工艺风险时保留为候选成果，交由相应负责人复核。

<a id="appendix-a-cad-designer"></a>
## Appendix A: cad-designer

# CAD设计狮 — CAD 专业设计指导

本skill提供CAD设计的专业指导，涵盖制图规范(国标)、参数化设计、图层管理系统、标注标准、批量出图策略、性能优化、AI+CAD趋势与设计检查清单。

> **配合使用**: `cad-automation` skill 负责写代码自动化画图，CAD设计狮负责告诉AI"怎么设计才对"。

---

## 0. 2026-06-11 设计决策总则

本 skill 的职责是先给出“画什么才对”，再交给 `cad-automation` 生成图形。遇到机械、模具、夹具、钣金、装配图时，必须先完成以下判断：

1. 明确图纸类型：零件图、装配图、总布置图、工艺草图、校核图。
2. 明确用途：报价、评审、加工、装配、维修、教学演示。用途不同，细节深度不同。
3. 明确验证等级：草图可 L2，交付加工图至少 L3，重要装配图建议 L4 视觉复核。
4. 明确来源署名：如果参考开源项目、资料库或网络资料，在交付包中写入 `ATTRIBUTION.md`。

---

## 0.1 冲压模具设计指导卡

当用户要求绘制冲压模具时，优先按“模架总图 + 工作零件 + 导向定位 + 技术要求”组织图纸。

### 必画内容
| 模块 | 内容 | 检查点 |
|---|---|---|
| 模架 | 上模座、下模座、凹模板、卸料板 | 外形尺寸、中心基准、板厚说明 |
| 工作部分 | 凸模、凹模刃口、冲裁轮廓、冲孔 | 间隙方向、闭合轮廓、孔中心距 |
| 导向 | 导柱、导套、中心线 | 四角对称、避开工作区 |
| 定位紧固 | 螺钉、销钉、沉孔 | 不干涉刃口和导向件 |
| 标注 | 外形、孔径、导柱距、工作轮廓 | 不封闭尺寸链、不重复标注 |
| 技术要求 | 材料、热处理、间隙、研磨、倒角 | 未知参数标“待复核”，不能编造精度 |

### 默认设计假设
如果用户只说“画一个冲压模具”，默认画“小型冲孔/落料模平面示意图”，而不是直接画可加工全套图。必须在输出中说明：该图用于方案表达和自动化能力测试，真实生产前需要按材料、吨位、闭合高度、压力中心、强度和安全规范复核。

### 禁止事项
- 不在缺少材料厚度时给出确定刃口间隙，只能写“按材料厚度 x 5%-8% 复核”。
- 不在缺少压力机参数时承诺可生产。
- 不把示意图说成完整加工图。
- 不省略导柱导套、卸料板、凹模板这类识别冲压模具的关键结构。

## 第一章：CAD制图规范（国标）

### 1.1 图纸幅面 (GB/T 14689)

| 幅面 | 尺寸(mm) | 适用场景 |
|------|---------|----------|
| A0 | 841×1189 | 总图、大型工程 |
| A1 | 594×841 | 总平面、系统图 |
| A2 | 420×594 | 平面图、装配图 |
| A3 | 297×420 | 零件图（最常用） |
| A4 | 210×297 | 简单零件、明细表 |

**装订边**: A0-A3留25mm，A4留20mm；其余边距均为5-10mm。

### 1.2 比例选择 (GB/T 14690)

| 类型 | 推荐比例 |
|------|---------|
| 原值 | 1:1（优先选用） |
| 放大 | 2:1, 5:1, 10:1 |
| 缩小 | 1:2, 1:5, 1:10, 1:50, 1:100 |

**原则**: 优先1:1，必须在标题栏注明比例。

### 1.3 图线规定 (GB/T 17450)

| 线型 | 线宽 | 用途 |
|------|------|------|
| 粗实线 | 0.5-0.7mm | 可见轮廓 |
| 细实线 | 0.18-0.25mm | 尺寸线、剖面线 |
| 虚线 | 0.25-0.35mm | 不可见轮廓 |
| 点划线 | 0.25-0.35mm | 轴线、对称线 |
| 双点划线 | 0.25-0.35mm | 假想轮廓 |

**线宽比**: 粗:中:细 = 4:2:1

---

## 第二章：图层管理系统

### 2.1 图层命名规范

来自"AutoCAD知识库"和工程实战的最佳实践：

```
命名格式: 专业码_主组_次组_状态
示例:    A-WALL-PRIM-D  (建筑-墙体-承重-拆除)
         M-DUCT-SUPN-N  (暖通-风管-送风-新建)
         S-STRU-COLN-E  (结构-柱-混凝土-现有)
```

### 2.2 常用图层色号国标

| 图层 | 色号 | 线型 | 说明 |
|------|------|------|------|
| 粗实线(WALL) | 7(白/黑) | Continuous | 可见轮廓 |
| 细实线(DIM) | 1(红) | Continuous | 尺寸标注 |
| 中心线(CEN) | 2(黄) | CENTER/CENTER2 | 轴线/中心线 |
| 虚线(HID) | 3(绿) | HIDDEN/HIDDEN2 | 隐藏线 |
| 剖面线(HAT) | 4(青) | Continuous | 填充图案 |
| 文字(TXT) | 5(蓝) | Continuous | 文字注释 |
| 辅助线(AUX) | 8(灰) | Continuous | 构造线 |
| 图框(TB) | 7(白) | Continuous | 图框/标题栏 |

### 2.3 图层自动化管理最佳实践

```python
# 一键创建国标图层模板
def create_gb_layers(acad):
    layers_cfg = {
        "WALL":  (7, "Continuous"),
        "DIM":   (1, "Continuous"),
        "CEN":   (2, "CENTER"),
        "HID":   (3, "HIDDEN"),
        "HAT":   (4, "Continuous"),
        "TXT":   (5, "Continuous"),
        "AUX":   (8, "Continuous"),
        "TB":    (7, "Continuous"),
    }
    for name, (color, ltype) in layers_cfg.items():
        if name not in [l.Name for l in acad.doc.Layers]:
            layer = acad.doc.Layers.Add(name)
            layer.Color = color
            linetypes = [lt.Name for lt in acad.doc.Linetypes]
            if ltype in linetypes:
                layer.Linetype = ltype
```

### 2.4 图层管理铁律

1. **按对象类型分层**: 墙/门/窗 → 标注 → 文字 → 填充，绝不混层
2. **随层(ByLayer)**: 颜色、线型、线宽全部设为"随层"，禁止硬编码到对象
3. **0层禁忌**: 不在0层绘制任何内容，0层仅用于创建块定义
4. **Defpoints层**: 自动生成，不可删除，不在上面绘图
5. **图层状态保存**: 使用`_LAYERSTATE`保存/恢复图层状态快照

---

## 第三章：标注标准与技巧

### 3.1 标注顺序（国标）

```
总体尺寸 → 定位尺寸 → 定型尺寸 → 公差 → 形位公差 → 粗糙度 → 技术要求
```

**标注三不原则**:
- ❌ 不封闭尺寸链（至少留一个开口环）
- ❌ 不重复标注同一尺寸
- ❌ 不将尺寸标注在虚线上

### 3.2 文字字高规范

| 幅面 | 尺寸字高 | 标题字高 | 技术要求字高 |
|------|---------|---------|------------|
| A0/A1 | 5mm | 7mm | 5mm |
| A2/A3 | 3.5mm | 5mm | 3.5mm |
| A4 | 2.5mm | 3.5mm | 2.5mm |

### 3.3 公差标注

```
线性公差: 50±0.1       → 50%%p0.1
极限偏差: 50+0.05/-0.02 → 50%+0.05%%-0.02
基孔制:   φ50H7        → %%c50H7
基轴制:   φ50f6        → %%c50f6
```

### 3.4 形位公差符号速查

| 符号 | 名称 | 符号 | 名称 |
|------|------|------|------|
| — | 直线度 | ◎ | 同轴度 |
| □ | 平面度 | ≡ | 对称度 |
| ○ | 圆度 | ⊕ | 位置度 |
| ⌒ | 圆柱度 | ↗ | 圆跳动 |
| ⊥ | 垂直度 | ↗↗ | 全跳动 |
| ∥ | 平行度 | ∠ | 倾斜度 |

### 3.5 粗糙度标注

```
Ra 3.2  →  一般加工面（最常用）
Ra 6.3  →  粗加工面
Ra 1.6  →  精加工面
Ra 0.8  →  研磨面
```

---

## 第四章：块(BLOCK)设计规范

### 4.1 块命名规范

```
项目前缀_类别_名称_规格
示例: GB_BOLT_M16x50    (国标螺栓)
      PROJ_VALVE_GATE_DN100  (项目阀门)
      SYM_DOOR_SINGLE_900    (符号单开门)
```

### 4.2 块创建最佳实践

1. **0层建块**: 块内对象画在0层，颜色/线型设为随层(ByLayer)，插入后与当前图层匹配
2. **基点合理**: 图框→左下角，螺栓→头部中心，门→铰链中心
3. **属性>文字**: 图框标题栏用属性定义(ATT)，不要用普通文字
4. **动态块**: 对频繁变形的组件（门宽、螺栓长度）使用动态块参数

### 4.3 属性定义示例

```lisp
;; 创建带属性的标题栏块
(defun c:make_titleblock ()
  (setq blk (vla-add (vla-get-Blocks *doc*) (vlax-3d-point '(0 0)) "TB_A3"))
  ;; 添加矩形边框
  (vla-AddLightWeightPolyline blk ...)
  ;; 添加属性
  (vla-AddAttribute blk 5.0 acAttributeModeVerify
    "请输入图纸名称:" (vlax-3d-point '(100 270)) "DWG_NAME" "图纸名称")
  (vla-AddAttribute blk 3.5 acAttributeModeVerify
    "请输入比例:" (vlax-3d-point '(350 270)) "SCALE" "1:1")
)
```

---

## 第五章：模板系统 (DWT)

### 5.1 模板应包含

一个完整的DWT模板至少包含：

- [x] 所有标准图层及线型
- [x] 标注样式（GB_DIM_35 / GB_DIM_50）
- [x] 文字样式（STANDARD→仿宋, GB_ROMANS→Romans）
- [x] 页面设置（A3/A4打印配置）
- [x] 图框+标题栏块
- [x] 常用符号块（粗糙度、基准、剖切）
- [ ] 打印样式(.ctb)

### 5.2 模板加载API

```python
# Python方式加载模板
acad.app.Documents.Add("templates/GB_A3.dwt")
# 或
acad.doc.SendCommand('_NEW "templates/GB_A3.dwt"\n')
```

### 5.3 一键模板生成LISP

来自CAD学习知识库的实战思路——将重复的模板创建过程脚本化：

```lisp
(defun c:init_project (/ layers dims texts)
  ;; 创建图层
  (foreach lyr '("WALL" "DIM" "CEN" "HID" "TXT" "TB")
    (entmake (list '(0 . "LAYER") '(100 . "AcDbLayerTableRecord")
      (cons 2 lyr) '(70 . 0) '(62 . 7) '(6 . "Continuous")))
  )
  ;; 设置标注样式
  (command "_DIMSTYLE" "S" "GB_DIM" "_Y")
  ;; 加载图框
  (command "_INSERT" "TB_A3" "0,0" "1" "1" "0")
  (princ "\n项目初始化完成!")
)
```

---

## 第六章：打印与出图策略

### 6.1 打印配置

| 参数 | 推荐值 | 说明 |
|------|-------|------|
| 绘图仪 | DWG To PDF.pc3 | 最通用 |
| 图纸尺寸 | ISO A3 (420×297) | 按实际选择 |
| 打印比例 | 布满图纸/1:1 | 生产图纸用1:1 |
| 打印范围 | 窗口/范围 | 精确控制 |
| 打印样式表 | monochrome.ctb | 黑白打印 |
| 图形方向 | 横向/纵向 | 按图纸 |

### 6.2 批量打印

```python
def batch_print(folder, output_folder):
    """批量打印DWG到PDF"""
    import os
    from pyautocad import Autocad
    acad = Autocad(create_if_not_exists=True)
    for f in os.listdir(folder):
        if f.endswith('.dwg'):
            pdf = os.path.join(output_folder, f.replace('.dwg', '.pdf'))
            doc = acad.app.Documents.Open(os.path.join(folder, f))
            # 设置布局
            acad.doc.ActiveLayout.ConfigName = "DWG To PDF.pc3"
            # 打印到文件
            acad.doc.Plot.PlotToFile(pdf)
            doc.Close(False)  # 不保存
```

### 6.3 打印前检查清单

- [ ] 图层全部打开、解冻、解锁
- [ ] 所有文字使用系统字体（避免缺失）
- [ ] 标注文字大小符合图纸幅面
- [ ] 打印样式表正确（黑白→monochrome.ctb）
- [ ] 打印范围正确（窗口/范围）
- [ ] PDF预览确认无缺失

---

## 第七章：性能优化

### 7.1 CAD性能瓶颈

| 症状 | 原因 | 解决 |
|------|------|------|
| 打开慢 | 过多DGN线型/字体/注册程序 | PURGE清理+清理DGN |
| 操作卡 | 大量填充图案 | 关闭填充图层或简化图案 |
| 缩放卡 | 过多节点(样条/多段线) | 简化曲线精度 |
| 保存慢 | 过多未使用的图层/样式 | 定期PURGE |
| 崩溃 | 文件过大(>50MB) | 拆分为外部参照 |

### 7.2 优化命令

```
_PURGE All * N       → 清理所有未引用对象
_AUDIT Y             → 审计修复文件错误
_OVERKILL            → 删除重复/重叠对象
_-SCALELISTEDIT R Y  → 重置标注比例列表
_WBLOCK *            → 导出为纯净DWG
```

### 7.3 正则表达式清理LISP

CAD学习知识库中的实战工具——用正则批量处理文本标注：

```lisp
;; 批量清理文字中的多余空格
(defun c:clean_text (/ ss i en str new)
  (setq ss (ssget '((0 . "TEXT,MTEXT"))))
  (setq i 0)
  (repeat (sslength ss)
    (setq en (ssname ss i))
    (setq str (cdr (assoc 1 (entget en))))
    ;; 替换多个空格为单个
    (while (vl-string-search "  " str)
      (setq str (vl-string-subst " " "  " str)))
    ;; 去除首尾空格
    (setq str (vl-string-trim " " str))
    ;; 更新文字
    (vla-put-TextString (vlax-ename->vla-object en) str)
    (setq i (1+ i))
  )
  (princ "\n文字清理完成!")
)
```

---

## 第八章：AI+CAD工作流设计

### 8.1 AI在CAD中的三层角色

来自AI+CAD知识库的核心分析：

| 层级 | 功能 | 典型应用 |
|------|------|---------|
| **L1 特征识别** | AI看懂图纸 | Smart Blocks, 智能标注, 图元分类 |
| **L2 辅助生成** | AI辅助绘图 | Text-to-CAD, 参数推荐, 自动布局 |
| **L3 自主设计** | AI独立设计 | MecAgent, Omega, 装配体生成 |

### 8.2 AI辅助CAD工作流

```
[工程师意图] → [LLM解析] → [设计方案] → [代码生成] → [CAD执行] → [验证反馈]
     ↑                                                              |
     └──────────────── 迭代优化 ←───────────────────────────────────┘
```

**关键原则**: AI生成代码→人工审查→CAD执行→结果验证→修正提示→重新生成

### 8.3 常用AI+CAD工具矩阵

| 工具 | 能力 | 成熟度 |
|------|------|--------|
| CADAM | 自然语言→参数化3D模型 | ⭐⭐⭐ |
| Pointer-CAD | LLM→B-Rep实体 | ⭐⭐⭐⭐ |
| text-to-cad | 自然语言→可编辑CAD | ⭐⭐⭐ |
| Leo AI | 文本→零件+装配体 | ⭐⭐⭐ |
| MecAgent | 技术规格→CAD模型 | ⭐⭐⭐ |
| VideoCAD | 视频学习→CAD操作 | ⭐⭐ |
| WHUCAD | 开源CAD智能核心 | ⭐⭐⭐ |

### 8.4 提示词工程(CAD场景)

```
[角色] 你是一个AutoCAD自动化专家
[任务] 根据以下工程参数生成DWG图纸
[参数] 矩形: 500×300mm, 壁厚5mm, 圆角R10, 四角M6螺孔
[格式] 生成Python pyautocad代码
[约束] 图层: 轮廓→WALL层(白色), 中心线→CEN层(黄色), 标注→DIM层(红色)
[标注] 国标格式, 字高3.5mm, 标注样式GB_DIM
```

---

## 第九章：行业模板速查

### 9.1 机械制图

- **零件图**: 三视图+轴测图，含公差/粗糙度/形位公差
- **装配图**: 明细表+序号，标配合关系
- **四类图**: 轮廓图(WALL)→标注图(DIM)→中心线(CEN)→剖面图(HAT)

### 9.2 建筑制图

- **平面图**: 轴线→墙体→门窗→标注→文字
- **图层示例**: A-WALL / A-DOOR / A-WINDOW / A-DIM / A-TEXT
- **比例**: 平面1:100, 立面1:100, 详图1:20

### 9.3 市政/公路 (CAD学习知识库重点)

- **桩位图**: 轴线定位→桩位编号→坐标标注→桩表
- **道路纵横**: 桩号标注→坡度→高程→填挖方
- **管网**: 管径标注→流向→管底标高

### 9.4 电气制图

- **原理图**: 元件符号→连线→端子号
- **布局图**: 设备位置→线槽→标注
- **软件**: EPLAN(专用)或AutoCAD Electrical(含图库)

---

## 第十章：设计检查清单

### 10.1 图形内容

- [ ] 所有图层按规范创建和命名
- [ ] 对象颜色/线型/线宽均为"随层(ByLayer)"
- [ ] 0层无内容（仅用于块定义）
- [ ] 无多余图层、样式、块定义（PURGE清理）
- [ ] 所有块正确命名且基点合理

### 10.2 标注与文字

- [ ] 总体尺寸→定位尺寸→定型尺寸顺序正确
- [ ] 无封闭尺寸链
- [ ] 无重复标注
- [ ] 文字字高符合幅面要求
- [ ] 特殊符号正确(%%c, %%d, %%p)

### 10.3 打印出图

- [ ] 打印样式表正确(黑白打印=monochrome.ctb)
- [ ] 打印范围内含所有图形和图框
- [ ] 线宽比例正确（粗:中:细=4:2:1）
- [ ] Defpoints层已检查(该层不打印)
- [ ] PDF预览无误

### 10.4 文件管理

- [ ] 文件名格式: 项目号_图号_名称_版本.dwg
- [ ] 外部参照路径正确(相对路径优先)
- [ ] 字体文件与图形绑定或使用通用字体
- [ ] 图纸已AUDIT审计无错误
- [ ] 备份文件已生成(.bak/.sv$)

---

## 知识来源

---

**配合使用**: `cad-automation` skill — 本skill提供设计方法论，cad-automation提供代码实现。

---

## 第十一章：设计验证层级体系（2026-06-01 从 SW 设计狮架构移植）

> 本章从 sw-designer v2.5.0 的 L1-L4 验证层级体系移植，针对 CAD 场景适配。
> sw-designer 第十五章定义了 "返回值→特征数→实体物理测量→视觉QA" 的四级信任层。

### 11.1 CAD 的四级验证信任层

从最弱到最强：

| 层级 | 验证方式 | CAD 等效 | 可信度 | 假阳性风险 |
|:---:|------|------|:---:|------|
| **L1** | API返回值 != null | pyautocad 方法返回值 | ⭐ | 极高——`AddCircle`返回对象但可能画在错误图层 |
| **L2** | ModelSpace.Count 增长 | 实体数量变化 | ⭐⭐ | 高——空文字/辅助线也算实体 |
| **L3** | 选择集遍历 + PURGE审计 | 对象类型/图层/颜色验证 | ⭐⭐⭐ | 中——能抓到类型错误，抓不到坐标错误 |
| **L4** | 多视口 VLM 视觉审查 | 截图→多模态交叉审查 | ⭐⭐⭐⭐⭐ | 极低——能发现"标高写错了"这种纯数据抓不到的错 |

### 11.2 设计验证的设计哲学

```
问题: "Python代码没报错 + AutoCAD执行了" ≠ "图纸画对了"

原因:
- COM 调用返回成功只表示 AutoCAD 接收了命令
- 对象可能画在错误图层/错误坐标系/错误位置
- 标注可能在图纸空间而非模型空间
- 多段线可能开口而非闭合

解决: 设计验证必须到达 L3（对象审计），L4（视觉交叉审查）是工业级的进阶要求。
```

### 11.3 从 sw-designer 移植的设计决策

| SW 设计铁律 | CAD 对应 | 说明 |
|------|------|------|
| 启动环境净化 | 清理孤儿选择集 + PURGE | 每次运行前假设环境是"脏"的 |
| 实体数 > 特征数 | 有效对象数 > ModelSpace 总数 | 排除辅助线/空文字等"假实体" |
| 基准面 > 实体面 | WCS > UCS | 永远在世界坐标系中描述几何 |
| 双向贯穿 > 特定深度 | 全图审计 > 局部检查 | AUDIT Y + PURGE A 全图清理 |
| 三级降级 | Python → SendCommand → LISP | 设计时考虑实现路径的可用性 |

### 11.4 CAD 设计铁律速查（基于 SW 五大地雷模式）

| # | 设计铁律 | 违反后果 |
|:---:|------|------|
| 1 | **启动即清理**：关闭孤儿文档 + 清除所有选择集 | SelectionSet 同名冲突导致 COM 异常 |
| 2 | **WCS 锁定**：每次 SendCommand 前 `_UCS _W` | UCS 旋转导致所有坐标错位 |
| 3 | **捕捉关闭**：自动绘图前 `_NON` 关闭对象捕捉 | 端点吸附导致点选位置偏移 |
| 4 | **用完即删**：选择集操作后必须 Delete() | 同名选择集累积导致程序中断 |
| 5 | **审计验证**：每次保存前 AUDIT + PURGE | 垃圾实体导致文件膨胀/打开缓慢 |
| 6 | **英文命令**：SendCommand 用 `_LINE` 而非 `直线` | 中文版/英文版命令名不一致 |
| 7 | **0层禁忌**：0层仅用于块定义，不绘图 | 块插入后颜色/线型失控 |

---

## 第十二章：CAD 设计-验证循环（从 SW 双环架构移植）

> sw-designer 第十五章定义了 "内环编译→外环几何视觉→迭代" 的双重嵌套纠错环。
> CAD 场景下无编译过程，但执行→审查→修改的迭代循环同样适用。

### 12.1 CAD 单环验证-迭代模型

```
┌──────────────────────────────────────────┐
│         CAD 设计-验证 迭代环               │
├──────────────────────────────────────────┤
│                                            │
│  [生成代码] → [COM执行] → [AUDIT审计]      │
│       ↑                        │           │
│       │              ┌─────────┴──────┐    │
│       │              ▼                ▼    │
│       │        L3对象审计通过    L3对象审计失败 │
│       │              │                │    │
│       │         L4视觉QA         错误数据     │
│       │              │                │    │
│       │      ┌───────┴───────┐        │    │
│       │      ▼               ▼        │    │
│       │  [视觉PASS]     [视觉FAIL]    │    │
│       │      │               │        │    │
│       │    ✅完成       修改意见       │    │
│       │                      │        │    │
│       └──────────────────────┘        │    │
│             合并反馈 → 修改代码          │    │
│             迭代直到全部 PASS            │    │
└──────────────────────────────────────────┘
```

### 12.2 迭代中止的设计决策

| 决策点 | 规则 | 设计理由 |
|------|------|------|
| 最大迭代 | 简单图≤3轮 / 中等图≤5轮 / 复杂图≤8轮 | 超出范围说明设计意图有根本性错误 |
| 同类型错误 | 3次 → 熔断 | 不是参数微调能解决的 |
| L3优先于L4 | 先修对象错误再修视觉错误 | 对象数量/类型是"硬"标准 |
| 坐标系错误 | 1次即停 | 坐标系问题必须人工介入 |

### 12.3 设计验证融合检查清单

基于 sw-designer 第十四章的检查清单模式：

```
CAD 自动化出图前检查清单:
☐ 启动时清理了所有孤儿选择集
☐ UCS 已锁定为世界坐标系 (_UCS _W)
☐ 对象捕捉已临时关闭 (_NON)
☐ 所有 SendCommand 使用英文命令+下划线前缀
☐ 块定义都在 0 层创建
☐ 选择集操作后已 Delete()
☐ 保存前已执行 AUDIT + PURGE
☐ 图纸空间输出：模型空间为1:1，图纸空间为输出比例
```

---

### 知识库更新记录

| 版本 | 日期 | 核心变更 | 来源 |
|:---:|------|------|------|
| v1.1.0 | 2026-06-01 | 新增第十一章(设计验证层级 L1-L4) + 第十二章(设计验证迭代环 + 七铁律速查) | 架构优化 |
| v1.0.0 | 2026-05-24 | 初始版本，含10大章节：制图规范/图层/标注/块/模板/打印/性能/AI+CAD/行业模板/检查清单 | 知识体系构建 |

<a id="appendix-b-cad-automation"></a>
## Appendix B: cad-automation

# CAD 自动化绘图 Skill（优化版）

本skill提供AutoCAD自动化绘图的完整知识体系，涵盖Python COM自动化、AutoLISP插件开发、国产CAD兼容等核心内容。

## 0. 2026-06-11 优化版使用原则

本版把 CAD 自动化从“只会调用 AutoCAD”升级为“三栈协同”：

| 场景 | 首选技术 | 原因 | 降级方案 |
|---|---|---|---|
| 已安装 AutoCAD、要直接生成 DWG | `win32com` / `pyautocad` | 可调用真实 AutoCAD，适合出 DWG、标注、图层、打印 | SendCommand / SCR |
| 没有 CAD 软件、要稳定生成交换文件 | `ezdxf` | 离线生成 DXF，适合 CI、服务器、批量草图 | 生成 SVG/JSON 几何清单 |
| 参数化 3D、模具/夹具/结构件建模 | `CadQuery` / FreeCAD | 适合尺寸驱动和 STEP/STL 输出 | 先生成 2D 总图，再转 3D |
| 国产 CAD 兼容 | COM + 英文命令 + DXF | 中望/浩辰对 COM 和 DXF 兼容度通常较高 | AutoLISP |

### 执行铁律
1. 先判断环境：`AutoCAD.Application` 能连接则走 COM，不能连接则走离线 DXF。
2. 模型空间永远按 1:1、毫米单位绘制；图纸空间只处理视口和出图比例。
3. 每次自动绘图都要创建标准图层、锁定 WCS、清理选择集、执行 `AUDIT/PURGE/ZOOM E/REGENALL`。
4. 输出前至少做 L3 验证：对象数量、关键图层、关键几何尺寸、文字/标注存在性。
5. 使用外部开源项目的思路、API 或示例时，在交付包中保留 `ATTRIBUTION.md`，注明来源、许可证和本项目的使用方式。

### 外部开源资料吸收范围
本 skill 只吸收公开文档中的工程方法，不复制大段源代码。参考项目：

| 项目 | 作用 | 许可证 | 使用方式 |
|---|---|---|---|
| `reclosedev/pyautocad` | AutoCAD ActiveX 自动化封装、坐标与对象遍历思路 | BSD-2-Clause | 作为 COM 自动化路线参考 |
| `mozman/ezdxf` | 离线 DXF 创建/读写/修改 | MIT | 作为无 AutoCAD 环境的 fallback |
| `CadQuery/cadquery` | Python 参数化 3D CAD | Apache-2.0 | 作为 3D 参数化建模路线参考 |
| 开源CAD自动化项目 | 行业最佳实践参考 | 多种 | 作为技术路线与接口设计参考 |

## ⚠️ Python AutoCAD COM 关键踩坑

### 环境
- AutoCAD 2020+ (中文版), Python 3.10+ + pyautocad/pywin32, Windows 11

### 连接方式
| 方式 | 结果 |
|------|------|
| `pyautocad.Autocad(create_if_not_exists=True)` | ✅ 推荐，自动处理COM |
| `win32com.client.Dispatch("AutoCAD.Application")` | ✅ 底层连接 |
| `win32com.client.GetActiveObject("AutoCAD.Application")` | ✅ 连接已运行的实例 |
| `win32com.client.Dispatch("AutoCAD.Application.24")` | ✅ 指定版本(2021=24,2022=24.1,2023=24.2,2024=24.3) |

### 核心踩坑
1. **pyautocad 安全数组**: 坐标必须用 `APoint(x,y,z)` 包装
2. **COM对象生命周期**: `GetActiveObject`失败则需`Dispatch`
3. **单位**: AutoCAD内部使用绘图单位，默认公制mm
4. **中文命令**: 用 `acad.doc.SendCommand("_LINE ")` 带下划线前缀
5. **选择集**: `acad.doc.SelectionSets` 使用后必须`Delete()`，否则累积报错
6. **中望/浩辰兼容**: pyautocad同样支持(COM接口兼容)，但部分VLAX函数需要适配

---

## 一、AutoCAD 基础知识

### 1.1 AutoCAD 概述

AutoCAD是Autodesk公司开发的通用CAD软件，支持建筑、机械、电气、土木等领域。

### 1.2 坐标系

- **WCS (世界坐标系)**: 绝对坐标系，原点固定
- **UCS (用户坐标系)**: 可自定义原点和方向
- **极坐标**: `@距离<角度` (如 `@100<45`)
- **相对坐标**: `@x,y` (如 `@50,30`)

### 1.3 文件类型

| 类型 | 扩展名 | 说明 |
|------|--------|------|
| 图形文件 | .dwg | 标准图形文件 |
| 交换格式 | .dxf | 文本/二进制交换格式 |
| 模板 | .dwt | 含预设样式模板 |
| 标准 | .dws | 图层/标注/文字标准 |
| 脚本 | .scr | 批量命令脚本 |
| 线型 | .lin | 自定义线型定义 |
| 填充 | .pat | 自定义填充图案 |

### 1.4 常用API对象层次

```
AutoCAD.Application
├── ActiveDocument (Document)
│   ├── ModelSpace        (模型空间)
│   ├── PaperSpace        (图纸空间)
│   ├── Layers            (图层集合)
│   ├── Linetypes         (线型集合)
│   ├── TextStyles        (文字样式)
│   ├── DimStyles         (标注样式)
│   ├── Blocks            (块集合)
│   ├── SelectionSets     (选择集)
│   ├── Groups            (组集合)
│   └── Utility           (角度/距离/坐标工具)
├── Documents
├── Preferences           (系统配置)
└── MenuGroups            (菜单组)
```

---

## 二、绘图命令 (Drawing)

### 2.1 基本图元

```python
from pyautocad import Autocad, APoint, aDouble
acad = Autocad(create_if_not_exists=True)

# 直线
line = acad.model.AddLine(APoint(0,0,0), APoint(100,50,0))

# 圆
circle = acad.model.AddCircle(APoint(50,50,0), 30)

# 圆弧 (center, radius, start_angle弧度, end_angle弧度)
arc = acad.model.AddArc(APoint(50,50,0), 30, 0, 3.14159)

# 轻量多段线 (2D, 推荐)
pts = aDouble(0,0, 100,0, 100,50, 50,50)  # x,y交替
pline = acad.model.AddLightWeightPolyline(pts)
pline.Closed = True
pline.Color = 1  # 红色

# 椭圆
ellipse = acad.model.AddEllipse(APoint(50,50,0), APoint(30,0,0), 0.5)

# 样条曲线
fit_pts = aDouble(0,0,0, 20,30,0, 50,10,0, 80,60,0, 100,0,0)
spline = acad.model.AddSpline(fit_pts, aDouble(1,1,0), aDouble(1,0,0))

# 文字
text = acad.model.AddText("设计说明", APoint(10,10,0), 5)
mtext = acad.model.AddMText(APoint(10,10,0), 50, "多行\\P文字")

# 点
point = acad.model.AddPoint(APoint(50,50,0))
```

### 2.2 填充 (Hatch)

```python
outer_loop = [pline]
hatch = acad.model.AddHatch(0, "ANSI31", True)
hatch.AppendOuterLoop(outer_loop)
hatch.Evaluate()
hatch.PatternScale = 2.0
hatch.PatternAngle = 0.785  # 45°
hatch.Color = 3
```

### 2.3 SendCommand 方式 (兼容性最好)

```python
acad.doc.SendCommand("_CIRCLE 50,50 30 ")
acad.doc.SendCommand("_LINE 0,0 100,50 \n")
# \n = 回车, 空格 = 结束当前输入
```

---

## 三、编辑命令 (Modify)

### 3.1 基本编辑

```python
# 移动
obj.Move(APoint(0,0,0), APoint(50,0,0))

# 复制
new_obj = obj.Copy()
new_obj.Move(APoint(0,0,0), APoint(100,0,0))

# 旋转 (基点, 角度弧度)
obj.Rotate(APoint(0,0,0), 1.5708)  # 90°

# 缩放 (基点, 比例因子)
obj.ScaleEntity(APoint(0,0,0), 2.0)

# 镜像 (镜像线两点)
obj.Mirror(APoint(0,0,0), APoint(0,100,0))

# 偏移
obj.Offset(10)  # 返回数组(可能多个结果)

# 阵列 (矩形)
obj.ArrayRectangular(3, 2, 1, 100, 50, 0)  # rows,cols,levels,row_sp,col_sp,level_sp
```

### 3.2 通过SendCommand操作

```python
acad.doc.SendCommand("_MOVE\n")       # 移动
acad.doc.SendCommand("_COPY\n")       # 复制
acad.doc.SendCommand("_ROTATE\n")     # 旋转
acad.doc.SendCommand("_SCALE\n")      # 缩放
acad.doc.SendCommand("_MIRROR\n")     # 镜像
acad.doc.SendCommand("_OFFSET 10\n")  # 偏移
acad.doc.SendCommand("_TRIM\n")       # 修剪
acad.doc.SendCommand("_EXTEND\n")     # 延伸
acad.doc.SendCommand("_FILLET R 5\n_FILLET\n")  # 圆角R5
acad.doc.SendCommand("_CHAMFER D 3 3\n_CHAMFER\n") # 倒角3x3
```

---

## 四、图层管理 (Layers)

```python
# 创建图层
layer = acad.doc.Layers.Add("WALL")
layer.Color = 1     # 红色 (ACI色号)
layer.Linetype = "Continuous"

# 设置当前图层
acad.doc.ActiveLayer = acad.doc.Layers("WALL")

# 遍历所有图层
for layer in acad.doc.Layers:
    print(f"{layer.Name}: color={layer.Color}, linetype={layer.Linetype}")

# 锁定/冻结/关闭
ref = acad.doc.Layers("WALL")
ref.Lock = True       # 锁定
ref.Freeze = False    # 冻结
ref.LayerOn = True    # 开关

# 修改对象图层
line.Layer = "DIM"

# 批量修改图层 (SendCommand)
acad.doc.SendCommand("_LAYMCH\n")       # 图层匹配
acad.doc.SendCommand("_LAYISO\n")       # 图层隔离
acad.doc.SendCommand("_LAYUNISO\n")     # 取消隔离
```

### ACI常用色号

| 色号 | 颜色 | 适用 |
|------|------|------|
| 1 | 红 | 标注/重点 |
| 2 | 黄 | 中心线 |
| 3 | 绿 | 辅助线 |
| 4 | 青 | 文字 |
| 5 | 蓝 | 轮廓 |
| 6 | 品红 | 剖面 |
| 7 | 白/黑 | 默认 |
| 8 | 灰 | 参考线 |

---

## 五、标注与文字 (Dimensions & Text)

### 5.1 标注

```python
p1 = APoint(0, 0, 0)
p2 = APoint(100, 0, 0)
text_pos = APoint(50, -20, 0)

# 线性标注
dim = acad.model.AddDimAligned(p1, p2, text_pos)

# 旋转标注
dim = acad.model.AddDimRotated(p1, p2, text_pos, 0)

# 半径/直径标注
dim_rad = acad.model.AddDimRadial(APoint(50,50,0), circle, 10)  # leader_length
dim_dia = acad.model.AddDimDiametric(APoint(50,50,0), circle, 10)

# 角度标注
dim_ang = acad.model.AddDimAngular(APoint(0,0,0), p1, p2, APoint(30,30,0))

# 坐标标注
dim_ord = acad.model.AddDimOrdinate(APoint(50,50,0), APoint(50,0,0), True) # X坐标

# 标注样式
dim_style = acad.doc.DimStyles.Add("GB_DIM")
dim.TextHeight = 3.5    # 字高
dim.ArrowheadSize = 2.5 # 箭头大小
dim.DecimalSeparator = "."
```

### 5.2 公差与粗糙度

```python
# 公差标注(通过SendCommand兼容性好)
acad.doc.SendCommand("_TOLERANCE\n")
# 或使用Leader+文字模拟
leader = acad.model.AddLeader(points, annotation, 0)
```

### 5.3 特殊字符

| 代码 | 字符 |
|------|------|
| %%c | φ 直径 |
| %%d | ° 度 |
| %%p | ± 正负号 |
| %%u | 下划线开关 |
| \\P | 换行(MTEXT) |

---

## 六、块与属性 (Blocks & Attributes)

### 6.1 块定义

```python
# 创建块定义
block = acad.doc.Blocks.Add(APoint(0,0,0), "MyBlock")
# 在块定义中添加对象
block.AddCircle(APoint(0,0,0), 10)
block.AddLine(APoint(-10,0,0), APoint(10,0,0))

# 插入块参照
insert_pt = APoint(50, 50, 0)
block_ref = acad.model.InsertBlock(insert_pt, "MyBlock", 1, 1, 1, 0)
```

### 6.2 带属性的块

```python
# 创建属性定义
att = block.AddAttribute(
    5,              # 字高
    0,              # 模式(0=无)
    "标签",         # 提示
    APoint(0,15,0), # 插入点
    "TAG",          # 标签
    "默认值"         # 默认值
)

# 插入后修改属性
for att in block_ref.GetAttributes():
    if att.TagString == "TAG":
        att.TextString = "零件-001"
        att.Update()
```

### 6.3 外部参照 (Xref)

```python
# 附着外部参照
xref = acad.model.AttachExternalReference(
    "reference/base.dwg",  # 文件路径
    "base",              # 块名
    APoint(0,0,0),       # 插入点
    1, 1, 1, 0           # 比例和旋转
)
```

---

## 七、选择集与过滤

```python
# 创建选择集
ss = acad.doc.SelectionSets.Add("SS1")

# 全选
ss.Select(5)  # acSelectionSetAll

# 窗口选择
ss.Select(0, APoint(0,0,0), APoint(100,100,0))  # acSelectionSetWindow

# 过滤选择 (所有圆,半径>10)
import win32com.client
ft = win32com.client.VARIANT(0, [0, "CIRCLE", 40, 10.0])  # DXF组码过滤
fd = win32com.client.VARIANT(0, [0, ">="])
ss.Select(5, 0, 0, ft, fd)

# 遍历选择集
for obj in ss:
    print(f"对象类型: {obj.ObjectName}, 图层: {obj.Layer}")

# 删除选择集
ss.Delete()
```

### DXF组码常用过滤

| 组码 | 含义 | 示例 |
|------|------|------|
| 0 | 对象类型 | "CIRCLE","LINE","TEXT" |
| 8 | 图层名 | "WALL","DIM" |
| 62 | 颜色 | 1(红), 2(黄) |
| 40 | 半径(圆)/字高(文字) | 10.0 |
| 10 | 中心点/插入点 | 坐标 |

---

## 八、三维建模 (3D Modeling)

### 8.1 基本3D实体

```python
# 长方体
box = acad.model.AddBox(APoint(0,0,0), 100, 50, 30)  # 角点,长,宽,高

# 圆柱体
cyl = acad.model.AddCylinder(APoint(50,50,0), 20, 100)  # 底面中心,半径,高

# 球体
sphere = acad.model.AddSphere(APoint(50,50,30), 25)

# 圆锥体
cone = acad.model.AddCone(APoint(50,50,0), 15, 50)

# 圆环体
torus = acad.model.AddTorus(APoint(50,50,0), 30, 10)  # 中心,大半径,管半径
```

### 8.2 拉伸与旋转

```python
# 创建面域
regions = acad.model.AddRegion([pline])[0]

# 拉伸面域成实体
height = 50
taper_angle = 0  # 拔模角度(弧度)
solid = acad.model.AddExtrudedSolid(regions, height, taper_angle)

# 旋转面域成实体
solid = acad.model.AddRevolvedSolid(regions, APoint(0,0,0), APoint(0,0,100), 360)
```

### 8.3 布尔运算

```python
# 并集
solid1.Boolean(0, solid2)  # acUnion

# 差集
solid1.Boolean(1, solid2)  # acSubtraction

# 交集
solid1.Boolean(2, solid2)  # acIntersection
```

### 8.4 SendCommand 3D

```python
acad.doc.SendCommand("_BOX\n0,0,0\nL\n100\n50\n30\n")
acad.doc.SendCommand("_CYLINDER\n50,50,0\n20\n100\n")
acad.doc.SendCommand("_SUBTRACT\n")  # 差集
acad.doc.SendCommand("_UNION\n")     # 并集
```

---

## 九、图纸空间与打印

### 9.1 布局操作

```python
# 获取布局列表
for layout in acad.doc.Layouts:
    print(f"布局: {layout.Name}")

# 创建新布局
acad.doc.Layouts.Add("A3_打印")

# 切换布局
acad.doc.ActiveLayout = acad.doc.Layouts("A3_打印")

# 创建视口
vp = acad.doc.PaperSpace.AddPViewport(
    APoint(10,10,0),  # 中心点
    200,              # 宽
    150               # 高
)
vp.Display(True)  # 显示视口内容
```

### 9.2 打印/导出PDF

```python
# 通过SendCommand
acad.doc.SendCommand("_PLOT\n")        # 打印
acad.doc.SendCommand("_EXPORTPDF\n")   # 导出PDF

# 通过API
plot_cfg = acad.doc.Plot  # ActivePlotConfiguration
plot_cfg.ConfigName = "DWG To PDF.pc3"
plot_cfg.PaperUnits = 1   # mm
plot_cfg.StandardScale = 0  # acScaleToFit
plot_cfg.PlotType = 4      # acExtents
acad.doc.Plot.PlotToFile("output.pdf")
```

---

## 十、AutoLISP 自动化 (CAD知识库核心)

### 10.1 LISP基础

来自"CAD学习知识库"的308个插件揭示了LISP在工程领域的真实生产力。

```lisp
;; 基础结构
(defun c:命令名 (/ 局部变量1 局部变量2)
  (setq var1 value1)       ; 设置变量
  (setq ss (ssget))        ; 获取选择集
  (princ "\\n提示文字")    ; 命令行输出
  (princ)                  ; 静默退出
)

;; 选择集遍历
(defun c:changecolor (/ ss i en)
  (setq ss (ssget))
  (setq i 0)
  (repeat (sslength ss)
    (setq en (ssname ss i))
    (setq ed (entget en))
    (entmod (subst (cons 62 1) (assoc 62 ed) ed))  ; 改为红色
    (setq i (1+ i))
  )
)

;; 坐标标注 (from ZBBZ.lsp)
(defun c:zbbz ()
  ;; 创建标注图层
  (entmake (list '(0 . "LAYER") '(100 . "AcDbLayerTableRecord")
    '(2 . "UserDimCoors") '(70 . 0) '(62 . 7) '(6 . "Continuous")))
  ;; 设置当前图层
  (setvar "CLAYER" "UserDimCoors")
  ;; 获取点
  (while (setq pt (getpoint "\\n拾取标注点:"))
    (setq x (rtos (car pt) 2 3))
    (setq y (rtos (cadr pt) 2 3))
    (setq str (strcat "X=" x "\\PY=" y))
    (entmake (list '(0 . "MTEXT") (cons 1 str) (cons 10 pt) '(40 . 3.5)))
  )
)
```

### 10.2 批量处理框架 (mini_系列)

CAD学习知识库中最核心的模式——`mini_`前缀系列，提供了专业级工程自动化框架：

```lisp
;; mini_ 系列的核心模式: 配置-选择-处理
(defun c:mini_任务名 ( / old_cmd config_file sel_set result)
  ;; 1. 保存当前环境
  (setq old_cmd (getvar "CMDECHO"))
  (setvar "CMDECHO" 0)
  
  ;; 2. 加载配置(如有)
  ;; (load "mini_config.lsp")
  
  ;; 3. 选择对象
  (princ "\\n选择对象: ")
  (setq sel_set (ssget))
  
  ;; 4. 处理逻辑
  ;; ... 
  
  ;; 5. 恢复环境
  (setvar "CMDECHO" old_cmd)
  (princ)
)
```

### 10.3 LISP常用函数速查

| 函数 | 用途 |
|------|------|
| `(ssget)` | 选择对象返回选择集 |
| `(entget en)` | 获取实体数据表 |
| `(entmod data)` | 修改实体数据 |
| `(entmake data)` | 创建新实体 |
| `(ssadd en ss)` | 添加实体到选择集 |
| `(sslength ss)` | 选择集数量 |
| `(ssname ss i)` | 获取第i个实体名 |
| `(command "CMD" ...)` | 执行AutoCAD命令 |
| `(vla-get-property obj)` | 获取ActiveX属性 |
| `(vlax-curve-getArea obj)` | 获取曲线面积 |
| `(vlax-curve-getDistAtPoint obj pt)` | 获取点到起点距离 |

### 10.4 LISP→Python 对照

| AutoLISP | Python(pyautocad) |
|----------|-------------------|
| `(setq p (getpoint))` | `p = acad.doc.Utility.GetPoint()` |
| `(command "LINE" p1 p2 "")` | `acad.model.AddLine(p1, p2)` |
| `(entget (car (entsel)))` | `acad.doc.Utility.GetEntity()` |
| `(ssget)` | `acad.doc.SelectionSets.Add("SS")` |
| `(vl-load-com)` | pyautocad自动处理 |
| `(entmod ...)` | `obj.Layer = "NEW"` 等属性赋值 |

---

## 十一、批量处理与文件操作

### 11.1 批量打开/处理/保存

```python
import os
from pyautocad import Autocad

acad = Autocad(create_if_not_exists=True)

def batch_process_dwgs(folder):
    """批量处理DWG文件"""
    for f in os.listdir(folder):
        if not f.endswith('.dwg'):
            continue
        path = os.path.join(folder, f)
        # 打开
        doc = acad.app.Documents.Open(path)
        doc = acad.app.ActiveDocument  # 确保获取最新文档
        
        # 在这里做处理...
        # 例如：清理、修改图层、添加标注等
        
        # 保存关闭
        doc.Save()
        doc.Close()
        print(f"已处理: {f}")

# 使用
batch_process_dwgs("drawings/")
```

### 11.2 文件格式转换

```python
import os

def convert_dwg_to_dxf(folder):
    """批量DWG→DXF"""
    for f in os.listdir(folder):
        if f.endswith('.dwg'):
            path = os.path.join(folder, f)
            out = path.replace('.dwg', '.dxf')
            acad.doc.SendCommand(f'_OPEN "{path}"\n')
            time.sleep(1)
            acad.doc.SendCommand(f'_SAVEAS DXF 2018 "{out}"\n')
            time.sleep(0.5)
            acad.doc.SendCommand('_CLOSE\n')

# 支持的导出格式
formats = {
    '.dxf': 'DXF',     # 交换格式
    '.dwt': 'DWT',     # 模板
    '.pdf': 'PDF',     # 文档
    '.dwf': 'DWF',     # 轻量浏览
    '.stl': 'STL',     # 3D打印
    '.iges': 'IGS',    # 通用三维
    '.step': 'STP',    # 通用三维
}
```

### 11.3 运行脚本

```python
# 运行SCR脚本
acad.doc.SendCommand("_SCRIPT scripts/draw.scr\n")

# 加载LISP插件
acad.doc.SendCommand("(load \"plugins/mytool.lsp\")\n")
acad.doc.SendCommand("MYTOOL\n")  # 执行LISP命令

# 运行VBA宏
acad.doc.SendCommand("_-VBARUN MyMacro\n")
```

---

## 十二、中望CAD/浩辰CAD兼容

### 12.1 COM接口兼容性

来自"AutoCAD知识库"的国产CAD适配经验：

```python
# 中望CAD (ZWCAD)
try:
    acad = win32com.client.Dispatch("ZWCAD.Application")
except:
    acad = win32com.client.Dispatch("AutoCAD.Application")

# 浩辰CAD (GStarCAD)
try:
    acad = win32com.client.Dispatch("GStarCAD.Application")
except:
    acad = win32com.client.Dispatch("AutoCAD.Application")

# 通用兼容写法
def get_cad():
    for progid in ["AutoCAD.Application", "ZWCAD.Application", "GStarCAD.Application"]:
        try:
            return win32com.client.Dispatch(progid)
        except:
            continue
    raise Exception("未找到可用的CAD程序")
```

### 12.2 差异点

| 特性 | AutoCAD | 中望CAD | 浩辰CAD |
|------|---------|---------|---------|
| COM Dispatch | ✅ | ✅ | ✅ |
| pyautocad | ✅ | ✅ | ✅ |
| AutoLISP | ✅ | ✅ | ✅ |
| VLISP扩展 | ✅ | 部分支持 | 部分支持 |
| ObjectARX | ✅ | ZRX | GRX |
| SendCommand | ✅ | ✅ | ✅ |
| 三维建模 | ✅ | ✅ | ✅ |

---

## 十三、AI+CAD 前沿 (AI+CAD知识库)

### 13.1 Text-to-CAD / AI生成CAD

目前主流的AI+CAD方向：

1. **自然语言→CAD模型**: CADAM、Leo AI、MecAgent等
2. **LLM生成CAD代码**: 通过大模型生成AutoLISP/Python/C#代码，再由AutoCAD执行
3. **特征识别**: AI识别工程图中的几何特征
4. **智能标注**: 自动提取模型项目生成标注

### 13.2 AI辅助CAD工作流

```python
# 通过AI生成AutoCAD脚本
# 示例：用户说 "画一个100x50的矩形，四周倒角R5"
# AI自动生成：

def ai_create_rounded_rect(length=100, width=50, radius=5):
    """AI生成的带倒角矩形"""
    acad = Autocad(create_if_not_exists=True)
    # 画矩形
    pts = aDouble(0,0, length,0, length,width, 0,width)
    pline = acad.model.AddLightWeightPolyline(pts)
    pline.Closed = True
    # 倒角
    acad.doc.SendCommand(f"_FILLET R {radius}\n_FILLET P\n")
    # 选择多段线
    pline.Highlight(True)
    acad.doc.SendCommand("P L\n")
    return pline

# 结合LLM的CAD Agent模式
# 1. LLM解析用户意图
# 2. 生成CAD操作序列
# 3. 通过COM/SendCommand执行
# 4. 验证结果反馈
```

### 13.3 重要开源项目

| 项目 | 说明 |
|------|------|
| Pointer-CAD | DeepSeek+港大,LLM生成B-Rep实体 |
| Zero-to-CAD | Autodesk, 大规模CAD构造序列 |
| text-to-cad | Jake, 自然语言→可编辑CAD |
| VideoCAD | MIT, 视频学习CAD操作 |
| WHUCAD | 武大, 首个CAD智能核心开源 |
| LLM4CAD | UT Austin, 多模态LLM→3D CAD |
| CADAM | 自然语言→参数化3D模型 |

---

## 十四、常见问题与调试

### 14.1 常见错误

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| pyautocad连接失败 | AutoCAD未运行 | 手动启动,或用`create_if_not_exists=True` |
| COM错误"RPC服务器不可用" | AutoCAD已关闭 | 重新dispatch |
| 选择集"已存在" | 未Delete旧选择集 | 每次用完`ss.Delete()` |
| SendCommand无反应 | 命令格式错误 | 空格代替回车确认, `\n`代替回车 |
| 中文乱码 | 编码问题 | SendCommand前确保AutoCAD设为GBK |
| LISP加载失败 | 路径含中文 | 用英文路径或`(findfile)` |
| 三维操作报错 | 未切换到3D视图 | `acad.doc.SendCommand("_VSCURRENT _R\n")` |

### 14.2 调试技巧

```python
# 查看所有对象属性
obj = acad.model(0)  # 第一个对象
for prop in dir(obj):
    if not prop.startswith('_'):
        try:
            val = getattr(obj, prop)
            print(f"{prop} = {val}")
        except:
            pass

# 列出所有文档
for i in range(acad.app.Documents.Count):
    doc = acad.app.Documents(i)
    print(f"文档 {i}: {doc.Name}")

# 查看选择集内容
ss = acad.doc.SelectionSets.Add("DEBUG")
ss.Select(5)  # 全选
print(f"当前图形有 {ss.Count} 个对象")

# 逐个查看类型
for obj in ss:
    print(f"  {obj.ObjectName}: Layer={obj.Layer}, Color={obj.Color}")
ss.Delete()
```

---

## 十五、工作流程总结

### AI自动化CAD标准流程

```
用户需求 → 分析绘图策略 → 选择APILISP/SendCommand → 生成代码 → 连接CAD执行 → 验证结果
```

### 功能矩阵

| 功能 | Python | LISP | SendCommand | 
|------|:---:|:---:|:---:|
| 基本绘图 | ✅ | ✅ | ✅ |
| 编辑操作 | ✅ | ✅ | ✅ |
| 图层管理 | ✅ | ✅ | ✅ |
| 标注 | ✅ | ✅ | ✅ |
| 块/属性 | ✅ | ✅ | ✅ |
| 选择集过滤 | ✅ | ✅ | ✅ |
| 三维建模 | ✅ | ⚠️ | ✅ |
| 图纸空间 | ✅ | ⚠️ | ✅ |
| 批量处理 | ✅ | ✅ | ⚠️ |
| 文件转换 | ✅ | ⚠️ | ✅ |
| 外部参照 | ✅ | ✅ | ✅ |

### 选择指南

- **快速原型**: SendCommand（最通用，中望/浩辰全兼容）
- **生产自动化**: Python + pyautocad（类型安全，逻辑复杂）
- **插件开发**: AutoLISP（AutoCAD原生，用户自定义命令）
- **企业级**: C# .NET API（性能最强，DLL部署）
- **AI辅助**: LLM → Python/LISP代码 → COM执行

---

**注意**: 所有代码单位为绘图单位（默认mm），使用前确认AutoCAD图形单位设置。国产CAD(中望/浩辰)COM接口基本兼容，部分VLAX函数差异请查阅对应API文档。

---

## 十六、CAD 核心铁律速查（2026-06-01 从 SW skill 架构移植）

> 以下铁律来自 solidworks-automation v4.4.0 的成功验证模式，针对 CAD 场景做了适配。

---

### 铁律 0：启动即清理——关闭孤儿文档 + 清理选择集 🔴

**SW对应**: solidworks-automation Sec 24 铁律0 (CloseDoc 启动清理)

**CAD病灶**: 反复调试运行时，AutoCAD 同样会积累未保存的 Drawing*.dwg，且 COM 选择集(SelectionSets)使用后不 Delete() 会累积导致后续操作报错。

```python
# ═══════ CAD启动首行代码 ═══════
import win32com.client
acad = win32com.client.Dispatch("AutoCAD.Application")

# 1. 清理所有孤儿选择集
for ss in acad.ActiveDocument.SelectionSets:
    try:
        ss.Delete()
    except:
        pass

# 2. 如果当前文档为空(Drawing1.dwg)，新建正式文档
doc = acad.ActiveDocument
if doc.Name.startswith("Drawing") and doc.ModelSpace.Count == 0:
    # 用模板新建
    doc.New("acadiso.dwt")
```

**LISP 等效**:
```lisp
;; 启动清理
(defun startup_clean ()
  ;; 清除所有选择集
  (while (setq ss (ssget "_X"))
    (setq ss nil))
  ;; 确保在模型空间
  (setvar "TILEMODE" 1)
  (princ)
)
```

---

### 铁律 1：选择集用完必 Delete——CAD 的"GetBodies2 防假跑" 🔴

**SW对应**: GetBodies2 实体计数验证

**CAD病灶**: `SelectionSets.Add("SS1")` 使用后不 Delete，再次运行同名选择集会报 "已存在" → 程序中断。

```python
# ✅ 安全选择集模式（用完即删）
def safe_select(acad, filter_type=None):
    ss_name = "TEMP_SS"
    # 删除已存在的同名选择集
    try:
        acad.ActiveDocument.SelectionSets(ss_name).Delete()
    except:
        pass
    ss = acad.ActiveDocument.SelectionSets.Add(ss_name)
    ss.Select(5)  # 全选
    result = list(ss)
    ss.Delete()  # ← 铁律：用完必删
    return result
```

**验证机制——CAD 等效于 GetBodies2**:
```python
def verify_drawing(acad, expected_objects: int = None):
    """验证图纸状态——CAD 的 GetBodies2 等效"""
    model = acad.ActiveDocument.ModelSpace
    count = model.Count
    
    doc = acad.ActiveDocument
    doc.SendCommand("_AUDIT Y\n")  # 审计修复
    doc.SendCommand("_PURGE A * N\n")  # 清理垃圾
    
    # 计算实体数（不含选择集内的辅助对象）
    ss = safe_select(acad)
    obj_count = len(ss)
    
    return {
        "object_count": obj_count,
        "model_count": count,
        "passed": expected_objects is None or obj_count >= expected_objects
    }
```

---

### 铁律 2：三级执行策略——CAD 等效于 Python→VBA→C# 🔴

**SW对应**: Sec 24 铁律8 (Tier 1 Python COM → Tier 2 VBA宏 → Tier 3 C# exe)

| 级别 | 方案 | 适用场景 | 限制 |
|:---:|------|------|------|
| **Tier 1** | Python + pyautocad | 图元创建、图层管理、标注 | COM 对象生命周期管理 |
| **Tier 2** | SendCommand / SCR 脚本 | 复杂编辑（TRIM/FILLET/CHAMFER） | 异步执行、错误处理弱 |
| **Tier 3** | AutoLISP / C# .NET | 插件开发、性能敏感、批量 | LISP 调试困难；C# 需 AutoCAD .NET SDK |

**降级逻辑**:
```python
def try_execute(operation, *args):
    """CAD 三级降级执行"""
    # Tier 1: pyautocad
    try:
        return operation(*args)
    except:
        pass
    # Tier 2: SendCommand
    try:
        cmd = build_sendcommand(operation, *args)
        acad.doc.SendCommand(cmd)
        return True
    except:
        pass
    # Tier 3: 加载 LISP 脚本
    try:
        acad.doc.SendCommand(f'(load "fallback.lsp")\n')
        acad.doc.SendCommand(f'FALLBACK\n')
        return True
    except:
        return False
```

---

### 铁律 3：CAD 六大隐藏地雷 ⚡

**SW对应**: Sec 21.2 五大 Interop DLL 地雷

| # | 地雷 | 现象 | 正确做法 |
|:---:|------|------|------|
| 1 | 选择集不 Delete | "选择集已存在" 错误 | 用完立即 `ss.Delete()` |
| 2 | SendCommand 编码 | 中文命令乱码/无效 | 用英文命令+下划线前缀 `_LINE` |
| 3 | UCS 混淆 | 坐标与实际位置不符 | `SendCommand("_UCS _W\n")` 先切到世界坐标系 |
| 4 | 对象捕捉干扰 | SendCommand 点选位置错误 | `SendCommand("_NON\n")` 临时关闭对象捕捉 |
| 5 | LISP `command` 与 `vl-cmdf` | command 受 UNDO 影响 | 批量操作用 `vl-cmdf` |
| 6 | pyautocad APoint 缺失 | 类型错误 | 所有坐标必须 `APoint(x,y,z)` 包装 |

```python
# 地雷3-4 的防护模板
def safe_sendcommand(acad, cmd):
    """发送命令前先重置 UCS + 关闭对象捕捉"""
    # 固定世界坐标系
    acad.doc.SendCommand("_UCS _W\n")
    # 临时关闭对象捕捉（避免吸附到错误位置）
    acad.doc.SendCommand("_NON\n")
    time.sleep(0.05)
    acad.doc.SendCommand(cmd)
```

---

### 铁律 4：执行后强制审计——CAD 的 ForceRebuild3 🔴

**SW对应**: ForceRebuild3 + GetBodies2 双重验证

```python
def verify_and_audit(acad):
    """CAD 执行后验证——等效于 SW 的 ForceRebuild3"""
    doc = acad.ActiveDocument
    
    # 1. 审计
    doc.SendCommand("_AUDIT Y\n")
    time.sleep(0.2)
    
    # 2. 清理（去除垃圾对象）
    doc.SendCommand("_PURGE A * N\n")
    time.sleep(0.2)
    
    # 3. 缩放范围（检查视觉完整性）
    doc.SendCommand("_ZOOM _E\n")
    time.sleep(0.2)
    
    # 4. 重生成（刷新显示）
    doc.SendCommand("_REGENALL\n")
    
    return True
```

---

### 铁律 5：编码与坐标系——SendCommand 两条前置命令 🔴

**每次 SendCommand 前强制执行的固定管线**:

```python
def sendcommand_pipeline(acad, *commands):
    """SendCommand 安全管线——两条前置 + N条主命令"""
    # === 前置1: 锁定WCS ===
    acad.doc.SendCommand("_UCS _W\n")
    time.sleep(0.05)
    
    # === 前置2: 关闭对象捕捉 ===
    acad.doc.SendCommand("_NON\n")
    time.sleep(0.05)
    
    # === 主命令 ===
    for cmd in commands:
        acad.doc.SendCommand(cmd)
        time.sleep(0.1)
    
    # === 后置: 重生成 ===
    acad.doc.SendCommand("_REGENALL\n")
```

---

### 十六、知识库更新记录

| 版本 | 日期 | 核心变更 | 来源 |
|:---:|------|------|------|
| v1.1.0 | 2026-06-01 | 新增铁律速查：启动清理/选择集防泄漏/三级降级/六大地雷/审计验证/SendCommand管线 | 架构优化 |
| v1.0.0 | 2026-05-24 | 初始版本，含14大章节：绘图/编辑/图层/标注/块/选择集/3D/打印/LISP/批量/AI+CAD | 知识体系构建 |
| v1.2.0 | 2026-10-07 | 新增第十八章：轴承座零件图全流程二次实证（COM忙等重试/文档生命周期/SendCommand挂起陷阱→PurgeAll/标注API实测/填充中文出图/验证L2-L4） | 大作业实战 |



---
---

## 十七、冲压模具自动绘图专项流程

当用户要求“画冲压模具、落料模、冲孔模、复合模、级进模、模架、凸模、凹模、卸料板、导柱导套”时，按本流程执行。

### 17.1 先问或默认的关键参数
如果用户没有给参数，使用以下可生产草图默认值，并在输出中说明：

| 参数 | 默认值 | 说明 |
|---|---:|---|
| 模架外形 | 500 x 360 mm | 小型冲孔/落料模 |
| 上模座厚度 | 45 mm | 装配剖视可标注 |
| 卸料板厚度 | 18 mm | 位于凸模下方 |
| 凹模板厚度 | 30 mm | 位于下模座上方 |
| 下模座厚度 | 50 mm | 基准底板 |
| 工件/冲裁轮廓 | 180 x 90 mm，R12 | 可替换为用户轮廓 |
| 冲孔 | 4 x %%c18 | 默认四孔 |
| 单边间隙 | 材厚 x 5%-8% | 未知材厚时标为“按材料复核” |
| 导柱 | 4 x %%c32 | 布置在四角 |

### 17.2 推荐图层
| 图层 | 色号 | 内容 |
|---|---:|---|
| `DIE_OUTLINE` | 7 | 模座、模板外形 |
| `DIE_WORK` | 1 | 凸模、凹模刃口、冲裁轮廓 |
| `DIE_GUIDE` | 2 | 导柱、导套、中心线 |
| `DIE_FASTENER` | 3 | 螺钉、销钉、沉孔 |
| `DIE_DIM` | 4 | 尺寸标注 |
| `DIE_TEXT` | 5 | 标题、技术要求、明细 |
| `DIE_AUX` | 8 | 构造线、基准线 |

### 17.3 自动绘图顺序
1. 创建图层、文字样式、标注样式。
2. 绘制模架总平面：上/下模座外形、凹模板、卸料板投影。
3. 绘制工作部分：冲裁轮廓、凸模轮廓、凹模刃口轮廓、冲孔。
4. 绘制导向部分：四角导柱导套、中心线和定位基准。
5. 绘制紧固定位：螺钉、销钉、沉孔符号。
6. 添加尺寸：外形尺寸、导柱距、工件中心距、孔径、刃口间隙说明。
7. 添加技术要求：材料、热处理、刃口间隙、配合研磨、未注倒角。
8. 执行 `AUDIT/PURGE/ZOOM E/REGENALL`，再保存 DWG。

### 17.4 L3 验证标准
冲压模具图至少要通过以下检查：

```python
required_layers = {
    "DIE_OUTLINE", "DIE_WORK", "DIE_GUIDE",
    "DIE_FASTENER", "DIE_DIM", "DIE_TEXT"
}
minimum_objects = 40
required_text = ["冲压模具", "凹模板", "凸模", "卸料板", "导柱", "技术要求"]
```

如果对象数不足、关键图层缺失、工作刃口没有闭合轮廓，必须重新生成；不能只报告“绘制成功”。

### 17.5 AutoCAD COM 最小测试脚本
可在独立测试文档中创建最小几何并检查保存、重开和导出；本仓库不附测试脚本或样图。


---

## 十八、2026-10-07 二次实战验证：通用零件图全流程（轴承座，本机实证）

> 用经典 CAD 课程大作业"轴承座零件图"（A3 图框+标题栏+主/俯/左三视图+左视全剖+剖面线+
> 10 处尺寸标注+技术要求+粗糙度属性块+PDF/PNG 出图，82 实体，纯绘制 5.5s / 含出图 11.7s）
> 在 AutoCAD 2024 简体中文 (24.3) + Python 3.14 + pywin32 上实测。
> 本节修正/补充 十六(铁律) 与 十七(冲压专项) 中未经本次验证的写法。

### 18.1 COM 忙等重试（必须）🔴
- AutoCAD 忙时抛 `-2147418111 被呼叫方拒绝接收呼叫`。**属性访问本身也会被拒**：
  `R(app.Documents.Add)` 是错的——属性求值发生在重试之外；必须
  `R(lambda: app.Documents.Add())` 把整条属性链包进重试。
- 同族错误码：`-2147417846`(RPC_RETRYLATER)、`-2147417848`。重试 60×0.5s 足够覆盖常规忙窗。

### 18.2 文档生命周期 🔴
- **绝不让 Documents 归零**：全部关闭后 COM 集合方法解析直接 `AttributeError <unknown>.Count/.Add`。
- `Documents.Add()` 后立刻取 `ActiveDocument` 需 `sleep(1.0)` + 忙等重试。
- 清空旧图用纯 COM 逆序删除：`for i in reversed(range(ms.Count)): ms.Item(i).Delete()`。
  **不要**用 `_ERASE _ALL`——空文档上会挂在"选择对象:"提示上（见 18.3）。
- 残留草稿清理只动 `Drawing*.dwg` 自动命名文档；窗口标题带 `*` 表示有未保存修改。

### 18.3 SendCommand 是最大的坑（能不用就不用）🔴
- **`_AUDIT _Y` 发现错误时会追加"写审计报告文件?"提示**——命令串没准备这个答案，
  同步 SendCommand 永久挂起（实测卡死 12 分钟）。`_PURGE _A _* _N` 的应答序列同样易错位。
- 清理一律用 **`doc.PurgeAll()`**（纯 API，无提示）。SendCommand 只用于无追加提示的命令
  （`_ZOOM _E` / `_REGENALL` 实测安全）。AUDIT 对纯生成图形可省略。
- 解除挂起：`doc.SendCommand(chr(3)*2)`（Ctrl+C）。COM 已卡死 + 锁屏/UIPI 时键盘不可达，
  最后手段 `taskkill /IM acad.exe /F`（先核对窗口内无用户未保存数据）。

### 18.4 标注 API 实测 ⚡
- `AddDimDiametric` 是 **3 参** `(Object, ChordPoint, LeaderLength)`，4 参 TypeError。
- **迭代 ModelSpace 拿到的圆/弧引用再传给标注类 API，易报"对象已被删除"**（-2145386420）。
- 最稳写法：直径类尺寸用跨象限点 `AddDimAligned(p1, p2, tp)` + `TextOverride="%%c50"`
  （%%c=⌀ %%d=° %%p=±）；半径用手工引线+文字。
- 标注样式直接设系统变量（A3 实测：DIMTXT 3.5 / DIMASZ 2.5 / DIMEXO 0.8 / DIMEXE 2.0 /
  DIMDEC 0 / LTSCALE 4 / DIMSCALE 1）。

### 18.5 填充 / 中文 / 出图（实测可用）✅
- 填充：`AddHatch(0,"ANSI31",True)` → `AppendOuterLoop(VARIANT(VT_ARRAY|VT_DISPATCH,[闭合pline]))`
  → 内孔 `AppendInnerLoop`（岛）→ `PatternScale` → `Evaluate()`。边界用闭合 LightWeightPolyline。
- 中文样式：`TextStyle.FontFile="gbenor.shx"; BigFontFile="gbcbig.shx"`；重名样式要复用
  （`TextStyles.Add` 重名会炸，先查 `Name in [s.Name for s in doc.TextStyles]`）。
- `Linetypes.Load` 对已加载线型抛"记录名重复" → 先遍历查重再 Load。
- 出图：先 `SetVariable("BACKGROUNDPLOT", 0)`（否则 PlotToFile 异步返回拿不到文件）；
  PDF：`layout.ConfigName="DWG To PDF.pc3"`，纸张从 `GetCanonicalMediaNames()` 里选
  `ISO_A3_(420.00_x_297.00_MM)`；PNG：`PublishToWeb PNG.pc3`（`XGA_Hi-Res_(1600.00_x_1200.00_Pixels)`）；
  `PlotType=1(Extents) + StandardScale=0(ScaleToFit) + CenterPlot=True`；PlotToFile 后轮询文件落盘。

### 18.6 验证分层 L2/L3/L4 落地
- L2：`ModelSpace.Count`；L3：按 `(ObjectName, Layer)` 分类型清点（本例 82 实体：
  10 标注 / 4 圆 / 4 弧 / 2 填充 / 9 虚线 / 7 中心线 / 26 实线 / 9 文字 / 2 块参照）+ `PurgeAll()`。
- L4：PNG 出图后视觉审查——本次实测抓出 3 处纯数据检查抓不到的问题：
  A—A 视图名与 60 尺寸文字重叠、粗糙度符号压 120 尺寸线、填充对象误落 WALL 层，修复后复检通过。

### 18.7 环境事实
- 从当前 CAD 安装和注册配置确认版本及 COM ProgID；AutoCAD 常用通用 ProgID 为 AutoCAD.Application。
