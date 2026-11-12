**Pocket Rove 1.6.9(1) 独立只读核查**

核查时间：2026-09-11 09:13 +08:00。Owner：本独立核查任务；源码权威根 `/Volumes/EXTERNAL/app/EarthOnlineGuide`，Git 根 `/Volumes/EXTERNAL/app`，当前分支 main，HEAD d61ae2d8216b8f4edbd8f7bfa8ebb8ae9fbd1097。保留既有未提交状态；Git HEAD 不作为整个 App 当前源码的完整版本封印。

已读取适用 AGENTS.md、全局细则 §2/§3/§4、完整 PROJECT_CORE.md。只读检查源码、现有记录、日志、plist、JSON 和一张既有 PNG；没有复制工作区、修改源码或台账、运行构建/测试、安装、上传、提交审核，也没有操作 Chrome ASC 页面。仅新增独立报告初稿及本补充版，未覆盖任何已有文件。

**结论：原句部分准确，不能原样采用。** 建议改为：

> 1.6.9(1) 已完成本地 Release 归档，并有局部 Debug 模拟器演示；本轮无法认证实时 ASC，当前上传状态 UNKNOWN。已有全库双语固定条件粗测和旧版英文组件测试，但当前 1.6.9 的准确双语全量排版测量、长度门禁及设备/大字号/真机/用户视觉验收尚未闭环。

PASS 指所列有限命题得到证据支持；FAIL 指验收要求尚未满足，不等于已复现产品缺陷；UNKNOWN 指没有当前可核实证据。

| 核查命题 | 判定 | 依据与边界 |
|---|---|---|
| 本地 1.6.9(1) Release archive 成功 | PASS | 原始 archive.log 成功标记与归档 plist 一致；2026-09-11 08:50:26 +08:00 建档 |
| “仅完成归档”可概括所有本地工作 | FAIL | 还有多次 Debug 构建、自然换行演示及 sky capture 现场记录 |
| 当前 ASC 未上传 1.6.9 | UNKNOWN | 实时只读 CLI 因缺少认证失败；旧观察不能证明当前不存在上传 |
| 所有任务完全没有测量 | FAIL | 1,012 个 ID 的中英固定条件粗测确实存在，且文本逐条匹配当前源包 |
| 当前版本已完成准确双语全量测量与长度门禁 | FAIL | 粗测条件、类型覆盖和门禁均不足；没有当前布局完整结果闭环 |
| 全机型/小屏/大字号/iPad/真机/用户视觉已通过 | UNKNOWN | 找不到与当前版本绑定的完整覆盖矩阵或相应通过证据；验收闭环为 FAIL |
| 当前源码采用两种语言较大占位 | PASS，限源码 | 已揭晓任务标题、板块标签、结语采用双语叠放隐藏测量；不能据此宣称整页所有状态等高、无溢出 |
| sky capture fixture 排除 Release | PASS | 位于 DEBUG 编译分支；归档编译命令无 DEBUG/TESTFLIGHT，归档二进制不含该环境变量字串 |
| 本归档是双语 TestFlight 包 | FAIL | 实际 EarthOnlineGuide / Release；双语包需要 PocketRove-TestFlight / TestFlight |

**补充时点：ASC 版本草稿与二进制严格分开**

主任务在本报告初稿后补充：用户已授权将商店名称改为 `Pocket Rove: Daily Adventures`；主任务称已新建 1.6.9「准备提交」版本草稿以解锁名称字段，正在保存英文名称，并称未上传安装包、未选择构建、未提交 1.6.9 审核。来源为任务 `01a07e82-3a5a-79f1-9814-bbb74b012171` 的本轮消息，属于执行者报告，本独立任务未通过实时 ASC 二读验证；名称是否保存成功也未确认。

因此，“ASC 出现 1.6.9 版本草稿”不能解释为“1.6.9(1) 二进制已上传”。当前草稿、名称保存、构建上传/关联、提交审核分别记录；本核查关于上传状态的 UNKNOWN 结论不变，也不再以“没有 1.6.9 草稿”描述当前 ASC。

**1. 归档与 ASC**

归档命令与成功标记：[Planning/Release-1.6.9/upload-20260911/archive.log:2](/Volumes/EXTERNAL/app/EarthOnlineGuide/Planning/Release-1.6.9/upload-20260911/archive.log:2)、[Planning/Release-1.6.9/upload-20260911/archive.log:672](/Volumes/EXTERNAL/app/EarthOnlineGuide/Planning/Release-1.6.9/upload-20260911/archive.log:672)。命令使用外接盘 DerivedData `/Volumes/EXTERNAL/app/.derived-data/EarthOnlineGuide/upload-169-20260911`，configuration Release、destination generic/platform=iOS。

归档身份：[Planning/Release-1.6.9/upload-20260911/PocketRove.xcarchive/Info.plist:15](/Volumes/EXTERNAL/app/EarthOnlineGuide/Planning/Release-1.6.9/upload-20260911/PocketRove.xcarchive/Info.plist:15)（第 15–18 行版本/构建，第 26–31 行时间/scheme）。归档内 App plist 解析为 1.6.9 / 1、最低 iOS 17.0、UIDeviceFamily [1,2]；支持 iPad 的声明不代表 iPad 已验收。该目录现有直接子项只有 archive.log 和 PocketRove.xcarchive，没有本目录上传回执；这不是全局“未上传”的证明。

归档中 `earth-online-guide-source-v1.json` 与当前源文件 SHA-256 完全相同：`76e0158124352e20929bda776ee9a3b54c6157a2c86ad03b0a7b815bc46f9c6a`。只证明任务资源一致；未取得归档时完整源码哈希清单，不声称所有当前源码与归档逐文件封印一致。

本轮尝试的只读查询：`ASC_TIMEOUT_SECONDS=20 asc builds list --app 6809132107 --version 1.6.9 --processing-state all --paginate --output json`。实际错误为 `Error: builds: missing authentication`；工具建议配置认证，本轮没有创建认证或读取秘密。工具路径 `/Users/USER/.local/bin/asc`。因此最新已上传是否仍为 1.6.3(1)、是否存在 1.6.9(1)、处理状态均为 UNKNOWN。委托中的 1.6.3(1) 观察只能保留为当时观察。

台账滞后：[Planning/Release-1.6/VERSION-1.6.9.md:7](/Volumes/EXTERNAL/app/EarthOnlineGuide/Planning/Release-1.6/VERSION-1.6.9.md:7) 第 7 行仍写“未构建”，已被后续构建/归档原始证据否定；其“未上传”也不能作为实时 ASC 事实。PROJECT_CORE.md 顶部仍为旧 1.6 开发说明，不能取代最新有效产物。

**2. 全库测量到底完成了什么**

当前源包 contentVersion 为 `source-v3-copy-150-paired-r1`，有 1,012 个唯一任务 ID：801 仅核心、207 仅彩蛋、4 共享；按 eligibleTypes 展开为 805 核心 + 211 彩蛋 = 1,016 个候选。展开实现见 [EarthOnlineGuide/LocalTaskPackCatalog.swift:176](/Volumes/EXTERNAL/app/EarthOnlineGuide/EarthOnlineGuide/LocalTaskPackCatalog.swift:176)。

[Planning/Release-1.6.9/measure-task-text.swift:4](/Volumes/EXTERNAL/app/EarthOnlineGuide/Planning/Release-1.6.9/measure-task-text.swift:4) 第 4–6、13–25 行：脚本用 CoreText、Fusion Pixel 16pt、固定 375pt 假设，核心列宽 172pt / 彩蛋列宽 216pt，阈值三行。统计文件 [Planning/Release-1.6.9/task-text-audit.json:1](/Volumes/EXTERNAL/app/EarthOnlineGuide/Planning/Release-1.6.9/task-text-audit.json:1) 包含全部 1,012 个 ID，中英原文与当前源包逐条比对相同，无缺项。英文 1/2/3/4 行分布为 7/267/619/119；中文为 136/785/91/0。119 条超三行均为核心，示例 [Planning/Release-1.6.9/task-text-audit.json:103](/Volumes/EXTERNAL/app/EarthOnlineGuide/Planning/Release-1.6.9/task-text-audit.json:103)。

这份粗测不是准确的全量布局验收，原因是：

- 只测一种字号、两个固定列宽，没有设备视口、Dynamic Type、真实 SwiftUI 布局提案和整页几何矩阵。
- 生产标题还使用 bold、PixelTextEmphasis，compact/noncompact 为 16/17pt；脚本只有常规 CTFont 16pt，未验证注册字体成功或回退，未测实际绘制边界。
- 4 个共享 ID 只按 core=true 测核心列，没有分别记录彩蛋候选形态；没有覆盖特殊彩蛋、历史旧快照与全部结语状态。
- 第 25–31 行只写 exceeded 和打印计数，没有超限失败退出或接入受控测试的证据；不能称长度门禁已启用。生产校验 [EarthOnlineGuide/LocalTaskPackCatalog.swift:75](/Volumes/EXTERNAL/app/EarthOnlineGuide/EarthOnlineGuide/LocalTaskPackCatalog.swift:75) 第 75–107 行也未包含行数验收。
- “四行”不等于“溢出”：当前任务行允许固有高度增长。119 个粗测结果是补验候选，不是 119 个已复现 UI 缺陷。

**3. 双语布局源码与正式测试边界**

[EarthOnlineGuide/AppViews.swift:2104](/Volumes/EXTERNAL/app/EarthOnlineGuide/EarthOnlineGuide/AppViews.swift:2104) 第 2104–2116 行：中英标题隐藏叠放加当前文本，共用字体和列宽，fixedSize 允许垂直增长；[EarthOnlineGuide/AppViews.swift:2126](/Volumes/EXTERNAL/app/EarthOnlineGuide/EarthOnlineGuide/AppViews.swift:2126) 第 2126–2137 行仅设置最小行高。换卡槽实际 44pt，见 [EarthOnlineGuide/AppViews.swift:2007](/Volumes/EXTERNAL/app/EarthOnlineGuide/EarthOnlineGuide/AppViews.swift:2007)。板块标签共享占位见 [EarthOnlineGuide/AppViews.swift:1928](/Volumes/EXTERNAL/app/EarthOnlineGuide/EarthOnlineGuide/AppViews.swift:1928)；结语采用两种字体隐藏测量、270pt 列宽、至少 64pt 高度，见 [EarthOnlineGuide/AppViews.swift:2204](/Volumes/EXTERNAL/app/EarthOnlineGuide/EarthOnlineGuide/AppViews.swift:2204)。

当前实现对“较大语言占位”有明确支持，但并非全页普遍自动保证：问号隐藏态按最小行高；顶部标题、CTA 等另有固定/缩放预算，仍需逐状态验收。Release 的 effectiveLanguage 强制 en，隐藏的中文调用也会被归一为英文，因此 Release 不等于双语几何测试包。

布局需求存在需核对的差异：[EarthOnlineGuide/AppViews.swift:714](/Volumes/EXTERNAL/app/EarthOnlineGuide/EarthOnlineGuide/AppViews.swift:714) 第 714–724 行标准字号使用整页外层滚动，只有 accessibility-size 使用内部任务区滚动；[EarthOnlineGuide/AppViews.swift:1619](/Volumes/EXTERNAL/app/EarthOnlineGuide/EarthOnlineGuide/AppViews.swift:1619) 第 1619–1645 行对应两条布局路径。因此版本记录中“顶部/底部固定、中间弹性”不能按所有字号已实现来验收。此处只列差异，没有修改。

旧正式原始证据确实存在：[Planning/Evidence/v2-2026-09-05/test-runner-guard-r1/runs/playful141-r2/playful141-r2.log:1451](/Volumes/EXTERNAL/app/EarthOnlineGuide/Planning/Evidence/v2-2026-09-05/test-runner-guard-r1/runs/playful141-r2/playful141-r2.log:1451) 第 1451–1459 行显示 2026-09-08 两项 FullCatalogCopyLayoutTests PASS，[Planning/Evidence/v2-2026-09-05/test-runner-guard-r1/runs/playful141-r2/execution-result.txt:1](/Volumes/EXTERNAL/app/EarthOnlineGuide/Planning/Evidence/v2-2026-09-05/test-runner-guard-r1/runs/playful141-r2/execution-result.txt:1) 为 exit_code=0。这是旧 1.4.1 文案阶段组件测试，详见 [Planning/Release-1.4.1/playful-library-r1/README.md:44](/Volumes/EXTERNAL/app/EarthOnlineGuide/Planning/Release-1.4.1/playful-library-r1/README.md:44) 第 44–48 行：1,016 个候选英文、375/390/402/440pt、212 组英文结语；明确不代表四台真机/全页视觉/全库中文。

当前测试源码 [EarthOnlineGuideTests/FullCatalogCopyLayoutTests.swift:11](/Volumes/EXTERNAL/app/EarthOnlineGuide/EarthOnlineGuideTests/FullCatalogCopyLayoutTests.swift:11) 第 11–52、56–87 行仍主要检查英文、Dynamic Type .large、组件固有高度，没有完整双语/多字号/整页状态矩阵。第 31 行手算换卡扣减仍为 36pt，而生产槽位是 44pt，参考文本测量可能偏乐观；组件本体仍走生产 Row，故也不能简单推导旧 PASS 全部无效。未找到这些测试在当前 1.6.9 布局下重新执行的完整结果。本轮未运行任何测试。

**4. 模拟器、真机与用户验收分层**

- 构建 PASS：[Planning/Release-1.6.9/natural-wrap-final-build.log:128](/Volumes/EXTERNAL/app/EarthOnlineGuide/Planning/Release-1.6.9/natural-wrap-final-build.log:128) 第 128 行和 [Planning/Release-1.6.9/sky-capture-build.log:127](/Volumes/EXTERNAL/app/EarthOnlineGuide/Planning/Release-1.6.9/sky-capture-build.log:127) 第 127 行，仅为本地构建证据。
- 三行演示：[Planning/Release-1.6.9/THREE-LINE-DEMO.md:15](/Volumes/EXTERNAL/app/EarthOnlineGuide/Planning/Release-1.6.9/THREE-LINE-DEMO.md:15) 第 3、7、9 行早期人为换行/空截图不构成自然全量测量；第 15–18 行已用四个真实任务替代，记录 iPhone 17 / iOS 26.5 英文自然三行核心、两行彩蛋及结语，仅为选样演示。
- 既有 native sky PNG 本轮已实际查看：仅第一核心任务揭晓且未完成，其余问号隐藏，CTA 为 Select tasks；可证明这一帧，不能验证 3+1 全长内容、结语或其他语言。元数据 [Planning/Release-1.6.9/SKY-CAPTURE-20260910.md:2](/Volumes/EXTERNAL/app/EarthOnlineGuide/Planning/Release-1.6.9/SKY-CAPTURE-20260910.md:2) 第 2–11 行绑定 Debug、iPhone 17/iOS26.5、选定 fixture。PNG SHA-256 与记录一致：`21788cba5245d011fc3eb464c920410f725c01a94e1c534032052b45f513c861`。
- `three-line-today-en.png` 与 `sky-revealed-incomplete-20260910.png` 均为 0 字节失败输出，不能引用作截图通过证据。
- 旧双语同场景局部比较见 [Planning/Release-1.6/BILINGUAL-1.6.3.md:9](/Volumes/EXTERNAL/app/EarthOnlineGuide/Planning/Release-1.6/BILINGUAL-1.6.3.md:9) 第 9 行，明确其他尺寸/辅助字号未验证。当前小屏、极端字号、iPad 横竖屏/窄窗口、真机和用户视觉完整验收 UNKNOWN；不能用旧矩阵或设备安装代替。

**5. DEBUG fixture 与配置**

[EarthOnlineGuide/ContentView.swift:123](/Volumes/EXTERNAL/app/EarthOnlineGuide/EarthOnlineGuide/ContentView.swift:123) 第 123 行至 [EarthOnlineGuide/ContentView.swift:339](/Volumes/EXTERNAL/app/EarthOnlineGuide/EarthOnlineGuide/ContentView.swift:339) 第 339 行包住 VerificationFixturePreparation，包括第 210、223–235 行的 skyCapture。sky 只替换第一条为 core-013，且阻止预置 Completion；不等于普通随机用户日。

归档日志第 432、436、596 行 Swift 编译参数为 `-O -target arm64-apple-ios17.0`，无 `-D DEBUG` / `-D TESTFLIGHT`；现有归档二进制没有 `EARTH_GUIDE_SKY_CAPTURE` 或 `EARTH_GUIDE_THREE_LINE_STRESS` 字串，结合条件编译判定 fixture 排除 Release PASS。

[EarthOnlineGuide/DisplayLocalization.swift:9](/Volumes/EXTERNAL/app/EarthOnlineGuide/EarthOnlineGuide/DisplayLocalization.swift:9) 第 9–24 行：DEBUG 或 TESTFLIGHT 才开放双语，普通 Release 固定英文。[EarthOnlineGuide.xcodeproj/project.pbxproj:538](/Volumes/EXTERNAL/app/EarthOnlineGuide/EarthOnlineGuide.xcodeproj/project.pbxproj:538) 第 538 行添加 TESTFLIGHT，不添加 DEBUG。两份 scheme 的 ArchiveAction 分别为 Release/TestFlight，见 [EarthOnlineGuide.xcodeproj/xcshareddata/xcschemes/EarthOnlineGuide.xcscheme:2](/Volumes/EXTERNAL/app/EarthOnlineGuide/EarthOnlineGuide.xcodeproj/xcshareddata/xcschemes/EarthOnlineGuide.xcscheme:2) 与 [EarthOnlineGuide.xcodeproj/xcshareddata/xcschemes/PocketRove-TestFlight.xcscheme:2](/Volumes/EXTERNAL/app/EarthOnlineGuide/EarthOnlineGuide.xcodeproj/xcshareddata/xcschemes/PocketRove-TestFlight.xcscheme:2)。[Planning/Release-1.6/TESTFLIGHT-LANGUAGE.md:3](/Volumes/EXTERNAL/app/EarthOnlineGuide/Planning/Release-1.6/TESTFLIGHT-LANGUAGE.md:3) 第 3–8 行说明了既有双语配置及模拟器验证边界。当前归档不能作为“已准备好双语 TestFlight 包”的证据；是否上传/给测试者安装还须独立验证。

**最小补验顺序（未执行；由已有项目执行 Owner 在相应授权下完成）**

1. ASC 只读 Owner：通过已认证接口或不冲突的页面读取 App 6809132107 的 1.6.9(1) 与最新构建，保留查询时间、构建 ID、上传时间和 processingState；成功后才更新上传结论。
2. 实现/QA Owner：绑定当前源码与内容哈希，使用真实生产字体、粗体/描边、实际列宽和双语有效配置，测全部 1,016 候选形态、特殊卡与当前结语；覆盖 supported 最窄宽度、compact 分界两侧及代表宽度、默认与最大辅助字号。输出自然行数/全文高/实际容器高/溢出和截断，先复核粗测 119 条。若保留三行上限，需明确并接入会失败的门禁；不自动删改任务。
3. QA Owner：在明确设备/OS矩阵上检查最坏 3 核心+彩蛋+长结语组合，含隐藏→揭晓→选择→完成、换卡可用/不可用、双语切换；iPhone 小屏和 iPad 横竖/窄窗口要覆盖滚动可达、CTA命中、边界和装饰遮挡。取当前同版截图/AX几何或实际滚动证据，不宣称穷举所有型号。
4. 既有设备测试 Owner 与用户：在上述通过后补最小真机流程和用户视觉复核，按实际范围签收。若目标为中文 TestFlight，应另经构建/上传授权使用专用 TestFlight 配置；本轮 Release 归档不能替代。

磁盘：本轮未创建构建物、缓存或下载；仅新增两份小型独立报告（合计约 33KB）。观察 `/` 可用约 19GiB、Lexar 约 1.7TiB；未清理任何文件，也不据此重新启动测试。本核查完成，产品布局/上传相关未验事项保持原状态。
