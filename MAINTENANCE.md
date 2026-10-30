# ndscan 维护说明

在 ARTIQ 实验上提供可组合实验片段和多维扫描。

- 上游：https://github.com/OxfordIonTrapGroup/ndscan
- 在线文档：https://xiaoshecode.github.io/xiaoshecode/repos/ndscan/
- 检查日期：2026-10-30

## 环境与使用

- 准备匹配 pyproject.toml 的 ARTIQ 8 / Python 3.10+ 环境。
- python -m pip install -e .

使用/检查入口（需先满足依赖条件）：

- `artiq_dashboard -p ndscan.dashboard_plugin`
- `python -m unittest discover -v test`

## 目录职责

- ndscan/experiment/ — 实验片段与扫描
- ndscan/plots/ — 结果展示
- examples/ — 实验示例
- test/ — 测试
- docs/ — 上游 Sphinx 文档

## 本次整理

- 新增维护文档和在线文档入口，补全用途、目录、使用路径及验证边界。

## 检查记录

- **仓库目录与入口盘点**（passed）：检查 Git 索引中的 77 个路径、README 和项目配置；不等于功能验收。
- **Python AST**（passed）：56 个文件通过解析；不导入依赖、不执行应用。
- **XML parse**（passed）：1 个文件通过解析；不导入依赖、不执行应用。
- **TOML parse**（passed）：1 个文件通过解析；不导入依赖、不执行应用。
- **完整构建与端到端运行**（not_run）：ARTIQ、Qt、oitg 和 Git 依赖未安装；未运行依赖这些组件的测试或连接实验设备。

## 验证边界与待办

- ARTIQ、Qt、oitg 和 Git 依赖未安装；未运行依赖这些组件的测试或连接实验设备。

## 后续维护约定

保留上游许可证与作者信息。沿用现有模块边界和格式配置；修复功能时同步最小回归验证。依赖或接口变更需写明迁移步骤，避免仅为目录美观搬动公开入口。
