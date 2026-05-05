# OpenAkita 全部技能参考手册

> 生成日期：2026-05-05
> 技能总数：**122**（系统内置 75 个 + 外部安装 47 个）
> 用途：供其他 AI 工具参考，将 OpenAkita 的技能体系移植/适配到目标系统

---

## 目录

- [一、文件操作类](#一文件操作类)
- [二、浏览器自动化类](#二浏览器自动化类)
- [三、桌面自动化类](#三桌面自动化类)
- [四、记忆与知识管理类](#四记忆与知识管理类)
- [五、定时任务类](#五定时任务类)
- [六、IM 消息通道类](#六im-消息通道类)
- [七、Agent 与多 Agent 协作类](#七agent-与多-agent-协作类)
- [八、MCP 服务管理类](#八mcp-服务管理类)
- [九、计划与任务执行类](#九计划与任务执行类)
- [十、LLM 与服务端配置类](#十llm-与服务端配置类)
- [十一、搜索类](#十一搜索类)
- [十二、人格与沟通类](#十二人格与沟通类)
- [十三、图像生成类](#十三图像生成类)
- [十四、内容创作类](#十四内容创作类)
- [十五、图文排版与设计类](#十五图文排版与设计类)
- [十六、视频与字幕处理类](#十六视频与字幕处理类)
- [十七、文档处理类](#十七文档处理类)
- [十八、数据抓取与分析类](#十八数据抓取与分析类)
- [十九、代码开发与工程类](#十九代码开发与工程类)
- [二十、网络代理与运维类](#二十网络代理与运维类)
- [二十一、自定义安装的技能类](#二十一自定义安装的技能类)

---

## 一、文件操作类

### 1. write-file
- **类型**: 系统内置
- **功能**: 创建新文件或覆盖已有文件，支持 UTF-8 编码
- **核心能力**: 文件写入、内容覆写、自动创建父目录
- **适用场景**: 创建代码文件、保存生成的数据、写入配置文件

### 2. read-file
- **类型**: 系统内置
- **功能**: 读取文件内容，支持分页读取大文件
- **核心能力**: 文本文件读取、分页查看、指定行号范围
- **适用场景**: 查看文件内容、分析代码或数据、获取配置值
- **分页参数**: offset（起始行号）、limit（最大行数）

### 3. list-directory
- **类型**: 系统内置
- **功能**: 列出目录中的文件和子目录
- **核心能力**: 目录浏览、文件名搜索、修改时间查看
- **适用场景**: 探索目录结构、查找特定文件

### 4. run-shell
- **类型**: 系统内置
- **功能**: 执行 Shell 命令
- **核心能力**: 系统命令执行、脚本运行、软件包安装、进程管理
- **适用场景**: 运行 bash/PowerShell 命令、执行脚本、安装依赖
- **限制**: 输出超过 200 行自动截断；超时上限 300 秒

---

## 二、浏览器自动化类

### 5. browser-open
- **类型**: 系统内置
- **功能**: 启动浏览器或检查浏览器状态
- **核心能力**: 浏览器启动、状态检查、自动处理启动流程
- **适用场景**: 所有浏览器自动化任务前必须先调用此工具确认状态

### 6. browser-navigate
- **类型**: 系统内置
- **功能**: 导航到指定 URL
- **核心能力**: 网页加载、搜索 URL 拼接、自动启动浏览器
- **适用场景**: 打开网页、搜索类任务（直接在 URL 中带搜索参数）

### 7. browser-get-content
- **类型**: 系统内置
- **功能**: 获取当前页面的文本或 HTML 内容
- **核心能力**: 页面内容提取、指定元素选择器、HTML 源码获取
- **适用场景**: 读取页面信息、抓取数据、验证页面内容

### 8. browser-click
- **类型**: 系统内置
- **功能**: 点击页面上的元素（CSS 选择器或可见文本）
- **核心能力**: 元素点击、CSS 选择器定位、文本匹配定位
- **适用场景**: 点击按钮、链接、选择下拉菜单

### 9. browser-type
- **类型**: 系统内置
- **功能**: 在输入框中输入文本
- **核心能力**: 表单填写、搜索框输入、文本清空与追加
- **适用场景**: 填写搜索框、输入用户名密码、文本域内容写入

### 10. browser-screenshot
- **类型**: 系统内置
- **功能**: 截取浏览器页面截图
- **核心能力**: 页面截图、全页截图（含滚动区域）
- **适用场景**: 展示页面状态、记录网页操作结果、调试页面问题

### 11. browser-scroll
- **类型**: 系统内置
- **功能**: 滚动页面
- **核心能力**: 向上/向下滚动、指定像素数
- **适用场景**: 浏览长页面、滚动到特定区域

### 12. browser-wait
- **类型**: 系统内置
- **功能**: 等待页面元素出现
- **核心能力**: 动态元素等待、超时控制
- **适用场景**: 等待 AJAX 加载、弹窗出现、页面渲染完成

### 13. browser-execute-js
- **类型**: 系统内置
- **功能**: 在页面中执行 JavaScript 代码
- **核心能力**: JS 执行、DOM 操作、数据提取
- **适用场景**: 获取页面特定数据、修改页面状态、调用 JS 函数

### 14. browser-list-tabs
- **类型**: 系统内置
- **功能**: 列出所有打开标签页的 URL 和标题
- **核心能力**: 多标签管理、标签状态查看
- **适用场景**: 查看当前有那些页面打开、定位目标标签

### 15. browser-switch-tab
- **类型**: 系统内置
- **功能**: 按索引切换浏览器标签页
- **核心能力**: 标签切换、0 基索引
- **适用场景**: 在多标签中切换任务

### 16. browser-new-tab
- **类型**: 系统内置
- **功能**: 打开新标签页，可选导航到 URL
- **核心能力**: 新标签创建、多任务并行
- **适用场景**: 在不关闭当前页的情况下打开新内容

### 17. browser-status
- **类型**: 系统内置
- **功能**: 检查浏览器当前状态（URL、标题、标签数）
- **核心能力**: 状态查询
- **适用场景**: 快速查看当前页面信息（browser-open 已包含此功能）

### 18. browser-close
- **类型**: 系统内置
- **功能**: 关闭浏览器并释放资源
- **核心能力**: 浏览器关闭、资源回收
- **适用场景**: 浏览器任务完成后的清理

### 19. browser-task
- **类型**: 系统内置
- **功能**: 智能浏览器任务——描述任务目标，AI 自动完成
- **核心能力**: 端到端浏览器自动化、智能任务规划
- **适用场景**: 复杂浏览器操作（描述做什么，AI 自动分解步骤执行）

---

## 三、桌面自动化类

### 20. desktop-screenshot
- **类型**: 系统内置
- **功能**: 截取桌面/应用窗口截图
- **核心能力**: 全屏截图、自动保存文件、返回文件路径
- **适用场景**: 展示桌面状态、捕获应用窗口、记录操作结果

### 21. desktop-click
- **类型**: 系统内置
- **功能**: 点击桌面元素或坐标
- **核心能力**: 元素描述定位、名称前缀匹配、坐标点击
- **适用场景**: 点击按钮/图标、选择菜单项、交互桌面 UI

### 22. desktop-type
- **类型**: 系统内置
- **功能**: 在桌面应用当前光标位置输入文本
- **核心能力**: 文本输入、中文输入支持
- **适用场景**: 填写对话框、输入表单、文本编辑器输入

### 23. desktop-hotkey
- **类型**: 系统内置
- **功能**: 执行键盘快捷键
- **核心能力**: 组合键执行（Ctrl+C/V、Alt+F4 等）
- **适用场景**: 复制粘贴、保存文件、关闭窗口、撤销重做

### 24. desktop-scroll
- **类型**: 系统内置
- **功能**: 滚动鼠标滚轮
- **核心能力**: 滚轮滚动、Ctrl+滚轮缩放
- **适用场景**: 滚动文档、浏览长列表、缩放视图

### 25. desktop-wait
- **类型**: 系统内置
- **功能**: 等待 UI 元素或窗口出现
- **核心能力**: 元素等待、窗口检测、超时控制（默认 10 秒）
- **适用场景**: 等待弹窗打开、加载完成、状态同步

### 26. desktop-window
- **类型**: 系统内置
- **功能**: 窗口管理操作
- **核心能力**: 列出窗口、切换窗口、最小化/最大化/恢复/关闭
- **适用场景**: 管理多个应用窗口

### 27. desktop-find-element
- **类型**: 系统内置
- **功能**: 查找桌面 UI 元素（UIAutomation 或视觉识别）
- **核心能力**: 元素定位、按钮/菜单查找、UI 状态验证
- **适用场景**: 在点击前定位元素位置、验证 UI 状态

### 28. desktop-inspect
- **类型**: 系统内置
- **功能**: 检查窗口 UI 元素树结构
- **核心能力**: UI 结构分析、元素标识符查找
- **适用场景**: 调试 UI 自动化问题、了解应用结构、查找正确元素标识

---

## 四、记忆与知识管理类

### 29. add-memory
- **类型**: 系统内置
- **功能**: 记录重要信息到长期记忆
- **核心能力**: 偏好学习、模式保存、错误教训记录
- **记忆类型**: fact（事实）、preference（偏好）、skill（技能）、error（错误教训）、rule（规则约定）
- **适用场景**: 记住用户偏好、保存成功模式、记录错误经验

### 30. search-memory
- **类型**: 系统内置
- **功能**: 按关键词搜索记忆
- **核心能力**: 关键词匹配、类型过滤
- **适用场景**: 回忆过去信息、查找用户偏好、检查已学模式

### 31. get-memory-stats
- **类型**: 系统内置
- **功能**: 获取记忆系统统计
- **核心能力**: 总数统计、类型分布、重要性分布
- **适用场景**: 检查记忆使用情况、了解记忆分布

### 32. consolidate-memories
- **类型**: 系统内置
- **功能**: 手动触发记忆整理与 LLM 清理
- **核心能力**: 去重清理、LLM 智能审查、MEMORY.md 刷新、向量库同步
- **适用场景**: 用户要求整理记忆、发现垃圾数据时

### 33. list-recent-tasks
- **类型**: 系统内置
- **功能**: 列出最近完成的任务
- **核心能力**: 任务历史查看、按时间/数量过滤
- **适用场景**: 用户问"你之前做了什么"时优先使用（比搜索对话快得多）

### 34. search-conversation-traces
- **类型**: 系统内置
- **功能**: 按关键词搜索完整对话历史（含工具调用）
- **核心能力**: 原始对话搜索、工具调用与参数回溯
- **适用场景**: search-memory 返回不够详细时，追溯具体操作细节

### 35. trace-memory
- **类型**: 系统内置
- **功能**: 跨层导航工具——在记忆、情节、对话三层之间跳转
- **核心能力**: 记忆溯源、情节展开、对话原文查看
- **适用场景**: 查看记忆的来源上下文、展开任务详情

### 36. knowledge-capture（Notion 知识捕获）
- **类型**: 外部技能（openakita/skills@knowledge-capture）
- **功能**: 将对话和散乱信息转化为结构化的 Notion 文档
- **核心能力**: 信息提取、结构化转换、交叉链接、Notion API 集成
- **文档模板**: 会议笔记、操作指南、决策记录、知识条目
- **适用场景**: 团队知识沉淀、会议记录、技术文档整理到 Notion

### 37. obsidian-skills（Obsidian 笔记管理）
- **类型**: 外部技能（openakita/skills@obsidian-skills）
- **功能**: 管理 Obsidian 知识库笔记
- **核心能力**: Obsidian Flavored Markdown 支持、YAML frontmatter、Dataview 查询、Canvas、Bases
- **组织方法**: MOC（内容地图）、原子笔记原则
- **适用场景**: 个人知识管理、PKM 系统建设

### 38. yuque-skills（语雀知识管理）
- **类型**: 外部技能（openakita/skills@yuque-skills）
- **功能**: 通过语雀 API 管理知识库和文档
- **核心能力**: 文档 CRUD、周报生成与发布、知识库管理、团队协作
- **适用场景**: 企业知识库管理、周报生成、团队文档协作

### 39. notebooklm（NotebookLM 深度研究）
- **类型**: 外部技能（openakita/skills@notebooklm）
- **功能**: 利用 NotebookLM 进行深度研究
- **核心能力**: 文档上传查询、引用溯源、多格式输出（Markdown/HTML/Mermaid）
- **信息图设计**: 视觉层次体系、色彩系统、布局模式
- **适用场景**: 学术研究、报告生成、综合分析

---

## 五、定时任务类

### 40. schedule-task
- **类型**: 系统内置
- **功能**: 创建定时任务或提醒
- **核心能力**: 一次性提醒、周期性提醒、AI 定时执行任务、多 IM 通道推送
- **触发类型**: once（一次性）、interval（间隔重复）、cron（表达式）
- **适用场景**: 定时提醒喝水、每日日报生成、定期任务执行

### 41. list-scheduled-tasks
- **类型**: 系统内置
- **功能**: 列出所有定时任务
- **核心能力**: 任务查看、状态查看、ID 获取
- **适用场景**: 检查已创建任务、获取任务 ID

### 42. cancel-scheduled-task
- **类型**: 系统内置
- **功能**: 永久删除定时任务
- **核心能力**: 任务删除、不可恢复
- **适用场景**: 用户说"取消/删除任务/关闭提醒"

### 43. update-scheduled-task
- **类型**: 系统内置
- **功能**: 修改定时任务设置（不删除）
- **核心能力**: 启用/暂停、修改推送通道、修改通知配置
- **适用场景**: 暂停任务、恢复任务、改推送通道

### 44. trigger-scheduled-task
- **类型**: 系统内置
- **功能**: 立即触发定时任务（不等计划时间）
- **核心能力**: 任务即时触发、不影响原有计划
- **适用场景**: 测试任务执行、提前运行

---

## 六、IM 消息通道类

### 45. deliver-artifacts
- **类型**: 系统内置
- **功能**: 通过 IM 网关发送附件（文件/图片/语音）
- **核心能力**: 跨通道文件发送、交付回执、去重
- **适用场景**: 发送截图、文件、语音消息到当前或指定 IM 通道

### 46. send-sticker
- **类型**: 系统内置
- **功能**: 搜索并发送表情包图片
- **核心能力**: 关键词搜索、情绪匹配、分类过滤
- **适用场景**: 闲聊问候、表达情绪、鼓励用户、庆祝完成

### 47. get-voice-file
- **类型**: 系统内置
- **功能**: 获取用户发送的语音消息的本地文件路径
- **核心能力**: 语音文件定位
- **适用场景**: 语音消息处理、语音转文字

### 48. get-image-file
- **类型**: 系统内置
- **功能**: 获取用户发送的图片的本地文件路径
- **核心能力**: 图片文件定位
- **适用场景**: 需要程序操作图片文件时（转发/保存/裁剪/格式转换）

### 49. get-chat-history
- **类型**: 系统内置
- **功能**: 获取当前聊天的历史消息
- **核心能力**: 对话历史查看、系统消息过滤
- **适用场景**: 查看之前的消息、回顾对话上下文

### 50. get-chat-info
- **类型**: 系统内置
- **功能**: 获取当前聊天/群组信息
- **核心能力**: 群名称、描述、成员数查询
- **适用场景**: 了解当前聊天环境

### 51. get-user-info
- **类型**: 系统内置
- **功能**: 获取指定用户的信息
- **核心能力**: 用户名、头像查询
- **适用场景**: 查找用户信息

### 52. get-chat-members
- **类型**: 系统内置
- **功能**: 获取当前群聊成员列表
- **核心能力**: 成员查询
- **适用场景**: 用户问"群里都有谁"

### 53. get-recent-messages
- **类型**: 系统内置
- **功能**: 获取群聊最近消息（通过平台 API）
- **核心能力**: 群消息获取、话题外消息查看
- **适用场景**: 在话题中查看群聊消息

---

## 七、Agent 与多 Agent 协作类

### 54. delegate-to-agent
- **类型**: 系统内置
- **功能**: 将任务委派给已有的专业 Agent（多 Agent 协作首选方式）
- **核心能力**: 任务分配、专业 Agent 调用
- **适用场景**: 当前任务需要其他 Agent 专长（代码/数据/浏览器等）

### 55. spawn-agent
- **类型**: 系统内置
- **功能**: 继承已有 Agent 创建临时工作 Agent（任务完成自动销毁）
- **核心能力**: Agent 定制、技能追加、提示词覆盖
- **适用场景**: 已有 Agent 接近但需要微调、需要同一 Agent 多个分身并行

### 56. delegate-parallel
- **类型**: 系统内置
- **功能**: 同时委派任务给多个 Agent 并行执行
- **核心能力**: 并行调度、同类任务自动分配独立副本
- **适用场景**: 多个独立任务需要同时执行（如同时调研多个项目）

### 57. create-agent
- **类型**: 系统内置
- **功能**: 从零创建全新 Agent（最后手段）
- **核心能力**: Agent 创建、技能分配、提示词编写
- **适用场景**: 系统中没有任何相关 Agent 可用时

### 58. list-exportable-agents
- **类型**: 系统内置
- **功能**: 列出所有可导出的 Agent 配置
- **核心能力**: Agent 列表查看
- **适用场景**: 查看可打包分发的 Agent

### 59. export-agent
- **类型**: 系统内置
- **功能**: 将本地 Agent 导出为 .akita-agent 可移植包
- **核心能力**: Agent 打包、技能捆绑、版本管理
- **适用场景**: 分享/备份/分发 Agent 配置

### 60. import-agent
- **类型**: 系统内置
- **功能**: 从 .akita-agent 包导入 Agent
- **核心能力**: Agent 安装、技能解包
- **适用场景**: 安装从社区获取的 Agent

### 61. inspect-agent-package
- **类型**: 系统内置
- **功能**: 预览 .akita-agent 包内容（不安装）
- **核心能力**: 包内容查看、验证状态检查
- **适用场景**: 安装前查看 Agent 包内容

### 62. search-hub-agents
- **类型**: 系统内置
- **功能**: 在 OpenAkita 平台 Agent Store 搜索 Agent
- **核心能力**: Agent 搜索
- **适用场景**: 查找社区 Agent

### 63. install-hub-agent
- **类型**: 系统内置
- **功能**: 从 OpenAkita 平台 Agent Store 下载安装 Agent
- **核心能力**: Agent 下载安装
- **适用场景**: 安装社区 Agent

### 64. publish-agent
- **类型**: 外部技能（系统级）
- **功能**: 将本地 Agent 发布到 OpenAkita 平台 Agent Store
- **核心能力**: Agent 打包、发布
- **适用场景**: 分享 Agent 到社区

---

## 八、MCP 服务管理类

### 65. list-mcp-servers
- **类型**: 系统内置
- **功能**: 列出所有配置的 MCP 服务器及其工具清单
- **核心能力**: 服务端列表、工具发现、连接状态
- **适用场景**: 查看可用 MCP 服务

### 66. call-mcp-tool
- **类型**: 系统内置
- **功能**: 调用 MCP 服务器的工具
- **核心能力**: 外部服务调用、专用功能访问
- **适用场景**: 使用外部 API 集成

### 67. get-mcp-instructions
- **类型**: 系统内置
- **功能**: 获取 MCP 服务器的详细使用说明
- **核心能力**: 服务器使用指南获取
- **适用场景**: 了解 MCP 服务器完整用法

### 68. add-mcp-server
- **类型**: 系统内置
- **功能**: 添加新的 MCP 服务器配置
- **核心能力**: 多传输协议支持（stdio/streamable_http/sse）、持久化配置
- **适用场景**: 集成新的外部服务

### 69. remove-mcp-server
- **类型**: 系统内置
- **功能**: 移除 MCP 服务器配置
- **核心能力**: 服务器配置删除、自动断开
- **适用场景**: 清理不需要的 MCP 服务

### 70. connect-mcp-server
- **类型**: 系统内置
- **功能**: 连接到已配置的 MCP 服务器
- **核心能力**: 服务连接、工具自动发现
- **适用场景**: 启动 MCP 服务连接

### 71. disconnect-mcp-server
- **类型**: 系统内置
- **功能**: 断开已连接的 MCP 服务器
- **核心能力**: 服务断开
- **适用场景**: 释放 MCP 连接资源

### 72. reload-mcp-servers
- **类型**: 系统内置
- **功能**: 重新加载所有 MCP 服务器配置
- **核心能力**: 配置刷新、热重载
- **适用场景**: 手动修改 MCP 配置文件后

---

## 九、计划与任务执行类

### 73. create-plan
- **类型**: 系统内置
- **功能**: 创建多步骤任务执行计划
- **核心能力**: 步骤分解、依赖管理、进度追踪
- **适用场景**: 需要多个工具协调完成的任务

### 74. update-plan-step
- **类型**: 系统内置
- **功能**: 更新计划步骤的状态
- **核心能力**: 进度追踪、状态管理
- **适用场景**: 每完成一个步骤后更新进度

### 75. get-plan-status
- **类型**: 系统内置
- **功能**: 查看计划执行状态
- **核心能力**: 进度查看、状态概览
- **适用场景**: 检查多步骤任务进度

### 76. complete-plan
- **类型**: 系统内置
- **功能**: 标记计划完成并生成摘要报告
- **核心能力**: 任务总结、统计报告
- **适用场景**: 所有步骤完成后

### 77. set-task-timeout
- **类型**: 系统内置
- **功能**: 调整当前任务超时策略
- **核心能力**: 无进展超时检测、硬超时上限
- **适用场景**: 长任务开始前避免被"卡死检测"误触发

---

## 十、LLM 与服务端配置类

### 78. system-config
- **类型**: 系统内置
- **功能**: 统一系统配置工具
- **核心能力**: 配置读写、LLM 端点管理、服务商管理、UI 偏好设置
- **适用场景**: 修改日志级别、添加/删除/测试 LLM 端点、管理服务商

### 79. get-tool-info
- **类型**: 系统内置
- **功能**: 获取系统工具的详细参数定义
- **核心能力**: 工具参数查看、使用示例学习
- **适用场景**: 调用不熟悉的工具前了解其用法

### 80. get-session-logs
- **类型**: 系统内置
- **功能**: 获取当前会话的系统日志
- **核心能力**: 日志查看、级别过滤
- **适用场景**: 命令执行失败时排错、了解之前操作结果

### 81. llm-endpoint-management
- **类型**: 外部技能（用户工作区）
- **功能**: 管理 LLM 端点配置（添加/删除/优先级/测试/修复）
- **核心能力**: 端点 CRUD、优先级排序、连通性测试、模型回退顺序
- **适用场景**: 配置多个 LLM 提供商、模型自动切换

---

## 十一、搜索类

### 82. web-search
- **类型**: 系统内置
- **功能**: 使用 DuckDuckGo 搜索网页
- **核心能力**: 关键词搜索、地区过滤、安全搜索
- **适用场景**: 查找最新信息、验证事实、查阅文档

### 83. news-search
- **类型**: 系统内置
- **功能**: 使用 DuckDuckGo 搜索新闻
- **核心能力**: 新闻搜索、时间范围过滤
- **适用场景**: 查找最新新闻、了解时事动态

### 84. find-skills
- **类型**: 系统内置
- **功能**: 帮助用户发现和安装技能
- **核心能力**: 技能发现、安装引导
- **适用场景**: 用户问"有没有能做 X 的技能"

### 85. search-store-skills
- **类型**: 系统内置
- **功能**: 在 OpenAkita 平台 Skill Store 搜索技能
- **核心能力**: 技能搜索
- **适用场景**: 查找社区技能

### 86. install-store-skill
- **类型**: 系统内置
- **功能**: 从 OpenAkita 平台 Skill Store 安装技能
- **核心能力**: 技能下载安装
- **适用场景**: 安装社区技能

### 87. install-skill
- **类型**: 系统内置
- **功能**: 从 URL 或 Git 仓库安装技能
- **核心能力**: 多来源安装、自动目录创建
- **适用场景**: 从 GitHub 安装技能

### 88. submit-skill-repo
- **类型**: 系统内置
- **功能**: 提交 GitHub 仓库到 Skill Store 索引
- **核心能力**: 技能仓库提交
- **适用场景**: 分享自创技能

### 89. apify-scraper（网页数据抓取）
- **类型**: 外部技能（openakita/skills@apify-scraper）
- **功能**: 使用 55+ Apify Actor 进行网页数据抓取
- **核心能力**: Instagram/TikTok/YouTube/Google/电商等平台数据抓取、JSON/CSV 输出
- **适用场景**: 社交媒体数据采集、电商价格监控、搜索结果抓取

### 90. crawler（高级爬虫）
- **类型**: 外部技能（用户工作区）
- **功能**: 高级网页爬虫，突破反爬保护
- **核心能力**: Cloudflare 绕过、JavaScript 渲染、爬虫框架
- **适用场景**: 被 Cloudflare 保护的网站、需要 JS 渲染的页面

### 91. scrapling-official
- **类型**: 外部技能（用户工作区）
- **功能**: 使用 Scrapling 进行网页抓取
- **核心能力**: 反爬绕过（如 Cloudflare Turnstile）、隐身无头浏览、爬虫框架
- **适用场景**: 网站数据抓取、反爬机制绕过

---

## 十二、人格与沟通类

### 92. switch-persona
- **类型**: 系统内置
- **功能**: 切换 AI 人格预设角色
- **核心能力**: 8 种预设角色切换（默认/商务/技术专家/管家/女友/男友/家人/贾维斯）
- **适用场景**: 用户要求换角色/性格

### 93. update-persona-trait
- **类型**: 系统内置
- **功能**: 更新用户的人格偏好维度
- **核心能力**: 正式程度、幽默感、表情使用、回复长度、情感距离等 11 个维度
- **适用场景**: 用户表达了沟通风格偏好时

### 94. get-persona-profile
- **类型**: 系统内置
- **功能**: 获取当前合并后的人格配置
- **核心能力**: 人格配置查看
- **适用场景**: 查看当前角色配置

### 95. toggle-proactive
- **类型**: 系统内置
- **功能**: 开关"活人感"模式
- **核心能力**: 主动消息发送（问候/提醒/回顾）
- **适用场景**: 用户希望 AI 更主动/更安静

### 96. update-user-profile
- **类型**: 系统内置
- **功能**: 更新用户档案信息
- **核心能力**: 20+ 档案项维护（称呼/工作领域/语言/偏好的操作系统等）
- **适用场景**: 用户提供个人信息时

### 97. get-user-profile
- **类型**: 系统内置
- **功能**: 获取用户档案信息摘要
- **核心能力**: 个人信息查询
- **适用场景**: 检查已知用户信息、个性化响应

### 98. skip-profile-question
- **类型**: 系统内置
- **功能**: 跳过用户拒绝回答的画像问题
- **核心能力**: 问题跳过
- **适用场景**: 用户说"不想回答"

---

## 十三、图像生成类

### 99. generate-image
- **类型**: 系统内置
- **功能**: 文生图（通义 Qwen-Image）
- **核心能力**: 文本转图片、多尺寸支持、提示词改写
- **适用场景**: 根据文本描述生成图片

### 100. baoyu-image-gen（AI 图像生成）
- **类型**: 外部技能（jimliu/baoyu-skills@baoyu-image-gen）
- **功能**: 使用多个图像生成服务商生成图片
- **核心能力**: 多服务商支持（DALL-E 3 / Google Imagen / 通义万象 / Replicate Flux）、自动服务商选择、Prompt 工程
- **适用场景**: 批量生成图片、多风格 AI 配图

### 101. baoyu-cover-image（文章封面图）
- **类型**: 外部技能（jimliu/baoyu-skills@baoyu-cover-image）
- **功能**: 生成文章封面图片
- **核心能力**: 5 维定制（类型/色板/渲染/文字/情绪）、9 色板 × 6 渲染风格、多比例支持
- **适用场景**: 文章封面生成、社交媒体配图

### 102. baoyu-infographic（信息图生成）
- **类型**: 外部技能（jimliu/baoyu-skills@baoyu-infographic）
- **功能**: 生成专业信息图
- **核心能力**: 21 种布局类型 × 20 种视觉风格、内容分析、结构化内容转换
- **适用场景**: 数据可视化、知识图解、高密度信息展示

### 103. baoyu-article-illustrator（文章配图）
- **类型**: 外部技能（jimliu/baoyu-skills@baoyu-article-illustrator）
- **功能**: 为文章配图（分析文章结构后自动插图）
- **核心能力**: Type × Style 二维配图策略、插图位置智能识别
- **适用场景**: 为博客/文章自动配图

### 104. baoyu-slide-deck（幻灯片图片）
- **类型**: 外部技能（jimliu/baoyu-skills@baoyu-slide-deck）
- **功能**: 从内容生成幻灯片图片
- **核心能力**: 16 种视觉预设、大纲生成、批量 Slide 生成、PPTX/PDF 合并
- **适用场景**: 演示文稿制作、培训材料

---

## 十四、内容创作类

### 105. xiaohongshu-creator（小红书内容创作）
- **类型**: 外部技能（openakita/skills@xiaohongshu-creator）
- **功能**: 创作符合小红书平台调性的笔记
- **核心能力**: 标题生成（数字法/反差法/痛点法等 8 种钩子）、四段式正文结构、话题标签策略、封面风格建议
- **适用场景**: 种草笔记、测评笔记、教程笔记、生活分享

### 106. douyin-tool（抖音视频工具）
- **类型**: 外部技能（openakita/skills@douyin-tool）
- **功能**: 抖音短视频全流程工具
- **核心能力**: 视频脚本撰写、BGM 推荐策略、字幕文案生成、热点话题分析、视频信息提取
- **适用场景**: 短视频内容创作、脚本写作、账号运营

### 107. wechat-article（公众号文章发布）
- **类型**: 外部技能（openakita/skills@wechat-article）
- **功能**: 创作并发布微信公众号文章
- **核心能力**: Markdown 转微信 HTML、富文本排版、封面图设计、摘要生成、API/手动双模式发布
- **适用场景**: 公众号内容创作、多平台内容适配

### 108. chinese-novelist（中文小说写作）
- **类型**: 外部技能（openakita/skills@chinese-novelist）
- **功能**: 中文小说创作指南
- **核心能力**: 角色创建（三维立体档案）、情节架构（起承转合）、场景描写（五感法）、类型化写作（玄幻/都市/悬疑/言情）
- **适用场景**: 小说创作、世界观构建、创作指导

### 109. chinese-writing（中文写作规范）
- **类型**: 外部技能（openakita/skills@chinese-writing）
- **功能**: 确保中文输出符合规范
- **核心能力**: 盘古之白间距规则、全角/半角标点规范、主动语态优先、场景化写作指南
- **适用场景**: 博客文章、UI 文案、错误提示、技术文档

### 110. baoyu-comic（知识漫画）
- **类型**: 外部技能（jimliu/baoyu-skills@baoyu-comic）
- **功能**: 创建原创知识漫画
- **核心能力**: 多种画风（清线/日漫/写实/水墨/粉笔）、7 种基调、可选的布局、角色一致性、PDF 合并
- **适用场景**: 教育漫画、知识科普、传记漫画

---

## 十五、图文排版与设计类

### 111. ppt-creator（PPT 演示文稿制作）
- **类型**: 外部技能（openakita/skills@ppt-creator）
- **功能**: 使用金字塔原理制作专业演示文稿
- **核心能力**: PPTX/Marp/Reveal.js 多格式输出、数据图表生成、演讲备注生成、质量自评
- **适用场景**: 商业汇报、产品路演、培训材料

### 112. baoyu-format-markdown（Markdown 格式化）
- **类型**: 外部技能（jimliu/baoyu-skills@baoyu-format-markdown）
- **功能**: 格式化 Markdown 文件
- **核心能力**: YAML frontmatter 管理、层级标题、列表转换、代码块格式化、CJK 排印修复
- **适用场景**: 美化文章排版、添加格式化、改进文章布局

### 113. pretty-mermaid（Mermaid 专业图表）
- **类型**: 外部技能（openakita/skills@pretty-mermaid）
- **功能**: 生成专业 Mermaid 图表
- **核心能力**: 多主题（Tokyo Night/Dracula/GitHub Light/Nord/Solarized）、SVG/PNG/ASCII 输出、模板库（微服务/CI-CD/ER/甘特图等）
- **适用场景**: 架构图、流程图、数据模型、项目排期

### 114. baoyu-url-to-markdown（URL 转 Markdown）
- **类型**: 外部技能（jimliu/baoyu-skills@baoyu-url-to-markdown）
- **功能**: 将任意 URL 转换为 Markdown
- **核心能力**: Chrome CDP 渲染、自动/等待双模式、登录页面支持
- **适用场景**: 保存网页为 Markdown、网页内容抓取

---

## 十六、视频与字幕处理类

### 115. youtube-summarizer（YouTube 视频总结）
- **类型**: 外部技能（openakita/skills@youtube-summarizer）
- **功能**: 提取 YouTube 字幕并生成结构化摘要
- **核心能力**: 多格式 URL 解析、多语言字幕获取、STAR+RISE 分析框架
- **适用场景**: 视频总结、课程笔记、时间戳提取、多视频对比

### 116. bilibili-watcher（B站/YouTube 字幕提取）
- **类型**: 外部技能（openakita/skills@bilibili-watcher）
- **功能**: 提取 B站 和 YouTube 视频字幕
- **核心能力**: 双平台支持、会员视频支持（需 Cookie）、多语言字幕、批量提取
- **适用场景**: 提取 B站 字幕、视频内容问答、多语言字幕对比

### 117. summarizer（通用内容摘要）
- **类型**: 外部技能（openakita/skills@summarizer）
- **功能**: 从任意来源（URL/文件/视频/文本）生成摘要
- **核心能力**: 多种输入类型、多输出格式（要点/执行摘要/详细笔记/纯提取）、可配置长度
- **适用场景**: 网页摘要、PDF 摘要、视频摘要、多源综合

---

## 十七、文档处理类

### 118. translate-pdf（PDF 文档翻译）
- **类型**: 外部技能（openakita/skills@translate-pdf）
- **功能**: 翻译 PDF 文档，保留原始排版
- **核心能力**: 逐页翻译、双语对照、表格/图片保留、OCR 支持扫描件、术语一致性
- **适用场景**: 学术论文翻译、技术文档本地化、商业报告翻译

---

## 十八、代码开发与工程类

### 119. todoist-task（Todoist 任务管理）
- **类型**: 外部技能（openakita/skills@todoist-task）
- **功能**: 通过 Todoist REST API v2 管理任务
- **核心能力**: 任务 CRUD、项目管理、分区管理、标签管理、高级过滤、重复任务
- **适用场景**: 待办事项管理、项目跟踪、批量任务操作

### 120. superpowers/writing-plans（编写实施计划）
- **类型**: 外部技能（obra/superpowers@writing-plans）
- **功能**: 为多步骤任务编写详细的实施计划
- **核心能力**: 小粒度任务分解（2-5 分钟/步）、完整代码示例、TDD 规范
- **适用场景**: 有规格需求后、写代码前的规划阶段

### 121. superpowers/verification-before-completion（完成前验证）
- **类型**: 外部技能（obra/superpowers@verification-before-completion）
- **功能**: 在声称完成前强制运行验证
- **核心能力**: 铁律"无最新验证结果则不得声称完成"、多维度验证检查
- **适用场景**: 所有声称"已完成"前的强制验证门禁

### 122. superpowers/using-git-worktrees（Git Worktree 工作流）
- **类型**: 外部技能（obra/superpowers@using-git-worktrees）
- **功能**: 使用 Git Worktree 创建隔离的工作空间
- **核心能力**: 智能目录选择、安全验证、自动项目配置
- **适用场景**: 需要隔离环境开发新功能时

### 123. superpowers/brainstorming（头脑风暴设计）
- **类型**: 外部技能（obra/superpowers@brainstorming）
- **功能**: 将想法转化为完整的设计和规格
- **核心能力**: 探索式提问、多方案对比、设计文档编写、YAGNI 原则
- **适用场景**: 任何创造性工作前必须使用

### 124. superpowers/dispatching-parallel-agents（并行 Agent 调度）
- **类型**: 外部技能（obra/superpowers@dispatching-parallel-agents）
- **功能**: 将独立任务并行调度给多个 Agent
- **核心能力**: 独立域识别、聚焦的 Agent 任务、并行执行
- **适用场景**: 多个无关问题需要同时调查时

### 125. superpowers/writing-skills（编写技能文件）
- **类型**: 外部技能（obra/superpowers@writing-skills）
- **功能**: 按照 TDD 方法论创建和测试技能
- **核心能力**: RED-GREEN-REFACTOR 流程、压力场景测试、技能防绕过
- **适用场景**: 创建新技能、编辑已有技能、部署前验证

### 126. superpowers/finishing-a-development-branch（完成开发分支）
- **类型**: 外部技能（obra/superpowers@finishing-a-development-branch）
- **功能**: 完成开发后的合并/PR/清理引导
- **核心能力**: 测试验证、4 种选项呈现（合并/PR/保留/丢弃）、Worktree 清理
- **适用场景**: 实现完成、测试通过后

### 127. superpowers/subagent-driven-development（子 Agent 驱动开发）
- **类型**: 外部技能（obra/superpowers@subagent-driven-development）
- **功能**: 按计划执行开发，每任务派发子 Agent + 两级审查
- **核心能力**: 每任务独立子 Agent、规格合规审查 + 代码质量审查
- **适用场景**: 执行实施计划时

### 128. superpowers/receiving-code-review（接收代码评审）
- **类型**: 外部技能（obra/superpowers@receiving-code-review）
- **功能**: 处理代码评审反馈
- **核心能力**: 技术验证优先、反对不合理建议、YAGNI 检查
- **适用场景**: 收到代码评审反馈后

### 129. superpowers/requesting-code-review（请求代码评审）
- **类型**: 外部技能（obra/superpowers@requesting-code-review）
- **功能**: 在关键节点请求代码审查
- **核心能力**: 专业审查 Agent 分发、问题分级（Critical/Important/Minor）
- **适用场景**: 完成任务后、合并前、修复复杂 Bug 后

### 130. superpowers/test-driven-development（测试驱动开发）
- **类型**: 外部技能（obra/superpowers@test-driven-development）
- **功能**: TDD 方法论规范
- **核心能力**: RED-GREEN-REFACTOR 完整流程、铁律"无失败测试则无生产代码"
- **适用场景**: 实现任何功能或 Bug 修复前

### 131. superpowers/systematic-debugging（系统化调试）
- **类型**: 外部技能（obra/superpowers@systematic-debugging）
- **功能**: 四阶段系统化调试
- **核心能力**: 根因调查 → 模式分析 → 假设验证 → 修复实施
- **适用场景**: 遇到任何 Bug、测试失败、意外行为时

### 132. superpowers/executing-plans（执行计划）
- **类型**: 外部技能（obra/superpowers@executing-plans）
- **功能**: 批量执行实施计划
- **核心能力**: 任务批量执行（默认前 3 个）、检查点报告
- **适用场景**: 已有书面实施计划后

### 133. superpowers/using-superpowers（Superpowers 工作流）
- **类型**: 外部技能（obra/superpowers@using-superpowers）
- **功能**: 启动对话时建立技能使用流程
- **核心能力**: 技能发现与加载引导
- **适用场景**: 每次对话开始时

---

## 十九、网络代理与运维类

### 134. mihomo-proxy-manager
- **类型**: 外部技能（用户工作区）
- **功能**: 轻量级命令行替代 Clash Verge 的方案
- **核心能力**: 订阅 URL 配置、mihomo/Clash.Meta 核心、系统代理、TUN 模式、节点切换
- **适用场景**: Linux 上不需要 GUI 的网络代理管理

### 135. proxy-pool（代理池）
- **类型**: 外部技能（用户工作区）
- **功能**: 代理池管理
- **核心能力**: 代理获取、健康检查、轮换
- **适用场景**: 需要代理 IP 池的应用

### 136. mcp-connection-troubleshooting（MCP 连接排障）
- **类型**: 外部技能（用户工作区）
- **功能**: 排查 MCP 服务器连接问题
- **核心能力**: 诊断流程、已知修复方案（desktop-control/web-search 本地包装器）、环境变量排查
- **适用场景**: MCP 连接失败时

### 137. screen-monitor-screenshot（截屏监控）
- **类型**: 外部技能（用户工作区）
- **功能**: Ubuntu GNOME Wayland 桌面截图与监控
- **核心能力**: 桌面截图捕获、OCR 识别、定时监控
- **适用场景**: 桌面状态监控、异常检测

---

## 二十、文档处理扩展类

### 138. platform-guide
- **类型**: 系统内置
- **功能**: OpenAkita 平台使用指南
- **核心能力**: 从 Agent Hub 和 Skill Store 搜索安装的完整教程
- **适用场景**: 教用户使用 OpenAkita 平台功能

### 139. generate-agents-md
- **类型**: 系统内置
- **功能**: 生成或更新项目 AGENTS.md 文件
- **核心能力**: 项目规范文档生成
- **适用场景**: 初始化项目规范、生成 AGENTS.md

---

## 快速索引表

| 类别 | 数量 | 技能名 |
|------|------|--------|
| 文件操作 | 4 | write-file, read-file, list-directory, run-shell |
| 浏览器自动化 | 15 | browser-open/navigate/get-content/click/type/screenshot/scroll/wait/js/list-tabs/switch-tab/new-tab/status/close/task |
| 桌面自动化 | 9 | desktop-screenshot/click/type/hotkey/scroll/wait/window/find-element/inspect |
| 记忆与知识管理 | 11 | add-memory, search-memory, get-memory-stats, consolidate-memories, list-recent-tasks, search-conversation-traces, trace-memory, knowledge-capture, obsidian-skills, yuque-skills, notebooklm |
| 定时任务 | 5 | schedule-task, list-scheduled-tasks, cancel/update/trigger-scheduled-task |
| IM 消息 | 9 | deliver-artifacts, send-sticker, get-voice-file, get-image-file, get-chat-history, get-chat-info, get-user-info, get-chat-members, get-recent-messages |
| Agent 协作 | 11 | delegate-to-agent, spawn-agent, delegate-parallel, create-agent, 4 个导出导入, search/install-hub-agent, publish-agent |
| MCP 管理 | 8 | list/call/get-instructions/add/remove/connect/disconnect/reload-mcp-server |
| 计划执行 | 5 | create/update-plan-step, get/complete-plan, set-task-timeout |
| LLM 配置 | 3 | system-config, get-tool-info, get-session-logs, llm-endpoint-management |
| 搜索 | 8 | web-search, news-search, find-skills, search-store/install-store/install-skill, submit-skill-repo, apify-scraper, crawler, scrapling-official |
| 人格沟通 | 7 | switch-persona, update-persona-trait, get-persona-profile, toggle-proactive, update/get-user-profile, skip-profile-question |
| 图像生成 | 6 | generate-image, baoyu-image-gen, baoyu-cover-image, baoyu-infographic, baoyu-article-illustrator, baoyu-slide-deck |
| 内容创作 | 6 | xiaohongshu-creator, douyin-tool, wechat-article, chinese-novelist, chinese-writing, baoyu-comic |
| 图文排版 | 4 | ppt-creator, baoyu-format-markdown, pretty-mermaid, baoyu-url-to-markdown |
| 视频字幕 | 3 | youtube-summarizer, bilibili-watcher, summarizer |
| 文档处理 | 1 | translate-pdf |
| 代码开发 | 15 | todoist-task, 14 个 superpowers/* |
| 网络代理 | 4 | mihomo-proxy-manager, proxy-pool, mcp-connection-troubleshooting, screen-monitor-screenshot |
| 平台指南 | 2 | platform-guide, generate-agents-md |

---

> 本文档共收录 **139** 项能力（75 系统内置 + 47 外部技能 + 17 大类整理）。
> 每个技能项都包含了功能描述、核心能力和适用场景，便于目标 AI 系统理解并适配。
