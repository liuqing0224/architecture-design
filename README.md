# 建筑与室内设计产品方案

本目录用于沉淀 `/Users/l/Documents/ChatGPT` 中建筑、室内、历史复原、参数化建模、AI 效果图与交付协同经验的跨项目产品方案。

## Canonical 文档

- [通用建筑与室内设计产品方案.md](通用建筑与室内设计产品方案.md)：v1.0 总体产品与商业方案，供内部立项和产品决策使用。
- [筑序MVP产品需求文档.md](筑序MVP产品需求文档.md)：P0 可执行 PRD，包含角色、九阶段需求、业务规则、埋点和验收标准。
- [建筑与室内设计多Agent系统方案.md](建筑与室内设计多Agent系统方案.md)：v1.0 技术架构基线，包含全 TypeScript 控制面、本地 Runtime、多 Agent 契约、安全、测试和部署。
- [platform](platform/)：生产导向的全栈 MVP，包含 Next.js 工作台、Fastify 控制面、PostgreSQL、共享契约、本地 Runtime 与 CodexAdapter。
- [demo](demo/)：可运行的产品 Demo，演示用户资料门禁、远程流程控制与审核、本地 coding Agent 执行及整改回流。
- [test-projects/duplex-apartment](test-projects/duplex-apartment/)：buildingSMART 公开复式住宅试运行项目，包含本地资料、Agent 审计结果和 Gate 阻断验收记录。
- [experiments/ai-performance-house](experiments/ai-performance-house/)：AI 建筑性能决策实验，锁定上海 180㎡住宅并完成基准 + 两轮日照、通风与简化能耗迭代，包含参数模型、逐时数据、脚本、交互页、验证报告与公众号文章。

## 当前结论

产品定位已锁定为面向中小设计事务所的“证据驱动建筑与室内设计协同工作台”。首版服务 300–3000㎡住宅、民宿、小型酒店与存量改造，通过远程控制面编排流程和审核，由用户电脑上的 Runtime 调用 Codex 在本地工作区执行设计任务。

当前已完成总体产品方案、MVP PRD、技术架构设计与可闭环全栈产品。`platform/` 现支持项目列表、新建项目、本地工作区绑定、资料哈希索引、Agent 任务与人工审核、Issue 证据关闭、九阶段 Gate、交付清单和归档锁定。正式研发与试点以 `platform/` 为准；`demo/` 只保留为历史视觉基线。

2026-08-30 已使用新建住宅验收项目 `QT-RES-LOCK-01` 完成“新建 → 9 个 Gate 顺序批准 → 生成交付 manifest → 项目归档”真实服务验收；交付清单哈希为 `sha256:30028200bfe4c18cfcb84d3ba6a7b61e5971ed84004e6693dedea0d48b411d94`。

同日已接入 buildingSMART Community `Duplex Apartment` 公开住宅数据集：59 项完整本地资料完成哈希索引，5 个专业 IFC 的官方字节数、SHA-256 与 STEP 包络及 47 个 PDF 的文件签名均已复核，本地 Codex Agent 完成两轮证据审计，G0 已批准；系统因 4 个真实工程证据 Blocker 正确拒绝 G1。该项目用于验证资料驱动的失败关闭机制，不伪造后续 Gate 或交付锁定。

用户随后明确将该项目定义为模拟测试，系统使用带 `SIMULATION ONLY` 标识的证据夹具完成 9/9 Gate、交付 manifest 和归档。最终 manifest 为 `sha256:94df45f32805367b314495f2fca93f77b5f98005f3a1b97fa8fc1f5e63caec7f`；模拟闭环不构成真实工程结论。

首版不定位为通用 CAD/BIM、结构或机电计算、自动施工图、自动报审平台，也不宣称替代注册建筑师、工程师、造价师和法定审查。

2026-08-30 完成 `experiments/ai-performance-house` 独立实验：R1 在采光/通风改善的同时使 HVAC EUI 恶化 4.5%，R2 撤回过量玻璃后在简化模型内相对基准下降 6.5%；结果只用于早期相对比较，不构成实际节能或规范声明。
