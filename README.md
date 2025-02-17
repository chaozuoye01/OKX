OKX 批量提现脚本

项目简介

本项目是一个 Python 脚本，支持从 Excel 文件读取提现地址和金额，并通过 OKX API 实现批量提现 （默认ETH 到 base 链）。

特性

批量提现：支持从 Excel 文件导入多个地址和提现金额。

随机时间间隔：每次提现后随机等待一段时间，增强操作的随机性。

API 签名：使用 HMAC-SHA256 生成 OKX API 请求签名。

依赖项

请确保已安装以下 Python 库：

pip install pandas requests openpyxl

使用方法

配置 API 信息

在代码中填写你的 OKX API Key、Secret 和 Passphrase。

准备 Excel 文件

Excel 文件需包含 Address 和 Amount 两列。

确保路径正确，例如 C:\Users\你的用户名\Desktop\OKX\withdraw_list.xlsx

运行脚本

直接运行 python script.py

参数说明

参数

说明

CHAIN_NAME

提现目标链（默认 ETH-Base，可修改为 ETH、ETH-Arbitrum One 等）

MIN_SLEEP_TIME

最小间隔时间（秒）

MAX_SLEEP_TIME

最大间隔时间（秒）

fee

提现手续费（需根据 OKX 最新规则调整）

免责声明

本项目仅供学习和研究使用，使用时请确保 API 权限和资金安全，开发者不对任何损失负责。

版权所有 (c) 2025 [作业借你抄 @chaozuoye]推特主页：https://x.com/chaozuoye
