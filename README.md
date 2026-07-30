# LLM 批处理提示词评估器
轻量大模型批量 Prompt 评测工具，面向AI产品日常测试场景

## 技术栈
Python、pandas、requests、Jupyter Notebook
适配阿里云 DashScope、OpenAI 兼容接口

## 项目特色
- 批量读取 Excel 测试Prompt，自动调用 LLM 接口
- 分层异常捕获，单条任务失败不会终止整体流程，兼容网络波动、超时、接口异常
- 自动提取模型回答、输入/输出Token消耗
- 结果导出结构化Excel，预留 Bad Case 人工标注栏位
- 内置请求限流，防止接口调用超限

## 文件结构
- `test_prompt.xlsx` # 输入：测试Prompt列表（表头名称：prompt）
- `model_result.xlsx` # 输出：评测结果表，运行自动生成
- `textllm.ipynb` # Jupyter 执行脚本

## 快速入门
1. 安装依赖
```bash
pip install pandas openpyxl requests

2. 基础配置
在 test_prompt.xlsx 填写需要测试的提示词
打开 textllm.ipynb，填入接口地址、模型名称、API_KEY
⚠️ 安全提醒：公开仓库请勿填写真实密钥！

3. 运行项目
依次执行 Notebook 单元格，运行结束自动生成 model_result.xlsx
输出字段：提示词、模型回答、输入 token、输出 token、运行状态、评测备注

License
MIT
