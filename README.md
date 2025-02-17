# OKX 批量提现脚本

> **功能**  
> 本项目通过 Python 脚本，从 Excel 文件批量读取提现地址和金额，调用 OKX API 自动执行批量提现（默认提现ETH到 Base，也可根据需求修改为其他链）。

---

## 特性

- **批量提现**：一次性读取 Excel 中所有地址和提现金额并执行批量操作。
- **随机时间间隔**：每次提现后随机等待一段时间（可配置），降低操作频率的规律性。
- **API 签名**：使用 HMAC-SHA256 生成 OKX API 请求签名，保证交易安全。

---

## 目录

- [环境依赖](#环境依赖)
- [使用说明](#使用说明)
- [配置参数](#配置参数)
- [许可证](#许可证)
- [免责声明](#免责声明)

---

## 环境依赖

本脚本需要以下 Python 库，请确保在运行前安装：

```bash
pip install pandas requests openpyxl
```

---

## 使用说明

1. **克隆或下载本项目**  
   将本项目的所有文件放到同一目录中。

2. **配置 API 信息**  
   在脚本中填写你的 OKX API 配置信息，例如：
   ```python
   API_KEY = 'API密钥'
   API_SECRET = 'API Secret'
   API_PASSPHRASE = 'API密码'
   ```

3. **准备 Excel 文件并填写参数**  
   - **Address**：提现地址  
   - **Amount**：提现金额
   -  ![1739786522946](https://github.com/user-attachments/assets/8ea8e1f4-cb57-45c9-9956-c9132481e75f)


4. **运行脚本**  
   进入脚本所在目录，执行：
   ```bash
   python your_script_name.py
   ```
   （将 `your_script_name.py` 替换为实际脚本文件名）

5. **查看执行结果**  
   脚本会在命令行中打印每次提现的结果以及随机等待的时间。  
   若出现错误，请根据提示信息进行排查。

---

## 配置参数

在脚本开头，你可以根据需要自定义以下参数：

| 参数名           | 含义                                                     | 默认值         |
| ---------------- | -------------------------------------------------------- | -------------- |
| `CHAIN_NAME`     | 提现目标链（如 `ETH-Base`、`ETH`、`ETH-Arbitrum One` 等） | `ETH-Base`     |
| `MIN_SLEEP_TIME` | 每次提现后最小等待时间（秒）                             | `120`          |
| `MAX_SLEEP_TIME` | 每次提现后最大等待时间（秒）                             | `1800`         |
| `fee`            | 提现手续费（需根据 OKX 最新规则进行调整）                | `0.002`（示例）|

---

## 许可证

版权所有 (c) 2025 [作业借你抄 @chaozuoye]  
推特主页：[https://x.com/chaozuoye](https://x.com/chaozuoye)

本代码基于 MIT 许可证开源发布。  
您可以自由使用、复制、修改、合并、发布、分发、再许可和/或销售本代码的副本，  
但须遵守以下条件：

1. 在任何分发或衍生作品中，必须明确提及原作者（[作业借你抄]）并给予适当的署名。  
2. 在分发代码或衍生作品时，必须包含本许可的完整内容。

本代码按“现状”提供，不附带任何明示或暗示的担保，包括但不限于对特定用途的适用性或适销性的担保。

---

## 免责声明

- 本项目仅供学习和研究使用，使用者需自行承担因使用本脚本带来的任何风险或损失。  
- 开发者不对任何因使用此脚本而产生的直接或间接损失负责。  
- 请合理使用 API 权限，并确保资金安全。
