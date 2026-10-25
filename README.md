# text-to-cad（收藏）

> 本仓库是个人收藏的软件工具介绍页。工具本体由原作者维护：**https://github.com/earthtojake/text-to-cad**

## 是什么

给 AI 编码助手（Claude Code、Codex、Cursor、Gemini、Grok 等）装上「CAD 超能力」。用文字描述一个零件（比如"相机支架，壁厚 3mm，留两个 M3 孔"），Agent 会编写参数化建模代码，经 OpenCascade 几何内核精确计算，输出真正的工程文件。

## 核心能力

- **真实 CAD 输出**：STEP（主输出）、STL、3MF、GLB——不是近似网格，尺寸精确、可直接进切片软件或 CNC 流程
- **工程图纸**：生成带尺寸的工程图 PDF、DXF 切割图
- **可制造性检查（DFM）**：导出前自动检查，并对接 3D 打印、钣金（SendCutSend）、CNC 打样服务
- **机器人支持**：URDF / SRDF / SDF 直出，ROS / Gazebo 可直接用
- **本地运行**：底层 build123d + Open CASCADE，首次启动需联网下载运行时

## 安装（Claude Code）

```bash
claude plugin marketplace add earthtojake/text-to-cad
claude plugin install text-to-cad@earthtojake
```

要求 uv + Python 3.11+。

## 评价与注意

- GitHub 约 1.9 万 star，MIT 协议，2026 年 4 月创建，迭代非常活跃（80+ 个 release）
- 适合硬件创客、机器人爱好者快速出原型；**不能替代专业机械工程审查**（公差、材料、安全验证）
- 坑：默认开启匿名遥测（可 `uvx cadgen telemetry off` 关闭）；Windows 11 的「智能应用控制」可能拦截 OpenCascade 未签名模块，建议在 WSL 里跑

## 相关链接

- 工具本体：https://github.com/earthtojake/text-to-cad
- 在线示例画廊：见原仓库 README
