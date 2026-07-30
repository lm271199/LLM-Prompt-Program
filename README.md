LLM Batch Prompt Evaluator
轻量大模型批量 Prompt 评测工具，面向 AI 产品日常测试场景
Tech Stack
Python pandas requests Jupyter Notebook
适配阿里云 DashScope OpenAI 兼容接口
Features
批量读取 Excel 测试 Prompt，自动调用 LLM 接口
分层异常捕获，单条失败不终止整体任务，兼容网络波动、超时、接口异常
自动提取模型回答、输入 / 输出 Token 消耗
结果导出结构化 Excel，预留 Bad Case 人工标注栏位
请求限流，防止接口调用超限
File Structure
plaintext
├── test_prompt.xlsx      # 输入：测试Prompt列表（表头名称：prompt）
├── model_result.xlsx     # 输出：评测结果表，运行自动生成
└── eval.ipynb            # Jupyter 执行脚本
Quick Start
安装依赖
bash
pip install pandas openpyxl requests
配置test_prompt.xlsx，填入待测试提示词
修改脚本配置区：填入 API Key、接口地址、模型名称
⚠️ 禁止公开泄露真实 API 密钥
运行脚本，自动生成model_result.xlsx
Output Columns
prompt | 模型返回内容 | 输入 token 数 | 输出 token 数 | 调用状态 | 评测标签 | 评测备注 | 是否 BadCase
Future Plan
失败用例自动重试
LLM 自动评测打分
多模型横向对比
Bad Case 筛选导出 & 统计可视化
License
MIT
