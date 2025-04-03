# ollama-translator
[English](https://github.com/needforspeed/ollama-translator/blob/main/README.md) [中文版](https://github.com/needforspeed/ollama-translator/blob/main/README-CN.md)

ollama-translator 翻译器是一个基于 Python 的命令行工具，设计用来使用本地的 Ollama API 模型翻译 Markdown 文件。这个工具支持多种语言，能够在翻译过程中保持 Markdown 文档的格式完整性。

## 特点

- **语言支持**：能够在多种语言之间翻译 Markdown 文件，同时保留原始的 Markdown 格式。
- **API 集成**：使用 Ollama API 进行准确可靠的翻译。
- **递归目录处理**：能够递归处理目录，一次处理多个文件。
- **灵活的输出选项**：允许用户将翻译后的文件保存在源文件的同一目录中或在指定的输出目录中。

## 支持的语言

以下语言代码可用于此工具，对应其完整的语言名称：

```plaintext
zh-CN: 简体中文
zh-TW: 繁体中文
ru: 俄语
de: 德语
es: 西班牙语
fr: 法语
ja: 日语
pt: 葡萄牙语
vi: 越南语
ar: 阿拉伯语
en: 英语
```

## 安装

克隆仓库：

```bash
git clone https://github.com/needforspeed/ollama-translator.git
cd ollama-translator
```

确保系统已安装 Python 3，并安装所需的包：

```bash
pip install -r requirements.txt
```

## 使用方法

要使用 Ollama 翻译器，导航到包含 `ollama-translator.py` 的目录，并运行以下命令：

```bash
python ollama-translator.py --base-lang [base_language_code] --target-lang [target_language_code] --input-dir [input_directory] [--output-dir [output_directory]] [--recursive]
```

### 命令行参数

- `--base-lang`: 要翻译的 Markdown 文件的基础语言代码。默认为 'en'。
- `--target-lang`: 目标语言代码。这个参数是必需的。
- `--input-dir`: 包含输入 Markdown 文件的目录路径。若不设置 `--recursive`，不会递归子目录。
- `--recursive`: 若设置此参数，将递归处理 `--input-dir` 指定的目录及其子目录中的所有 Markdown 文件。
- `--output-dir`: 将输出文件保存的目录路径。如果未提供，文件将保存在原文件旁。
- `--output-origin`: 如果设置，将输出文件保存在源文件的同一目录中。

## 示例

### 基本示例
将特定目录中的所有 Markdown 文件从英语翻译为西班牙语，包括子目录中的文件：

```bash
python ollama-translator.py --base-lang en --target-lang es --input-dir /path/to/input --output-dir /path/to/output --recursive
```

### 多语言示例
从中文简体翻译到英文，递归处理所有子目录：

```bash
python ollama-translator.py --base-lang zh-CN --target-lang en --input-dir /path/to/input --output-dir /path/to/output --recursive
```

## 错误处理

遇到的常见错误可能包括：

- **API 密钥缺失**：确保在环境变量中设置了正确的 API 密钥。
- **网络问题**：检查您的网络连接，确保 API 服务器可达。
- **文件权限问题**：确保 Python 脚本有权访问指定的文件夹和文件。

## 贡献

欢迎贡献！请按照以下步骤：

1. Fork 仓库。
2. 在您的分支上进行更改。
3. 确保遵守代码规范并进行了足够的测试。
4. 提交一个 Pull Request。

## 许可证

该项目根据 MIT 许可证授权 - 详情见 [LICENSE.md](LICENSE.md) 文件。
## 致谢

该项目的灵感来源于并分支自 [GPT Translator](https://github.com/daqing/gpt-translator)，一个致力于使用 GPT 模型翻译文本的项目。

### 注意事项:
- 请在使用文档或代码时，添加来源 URL (`https://github.com/wolfreka/ollama-translator.git`)。
- 根据您的环境需要，如果需要不同的解释器，如 `python3`，请根据需要调整命令。
- 确保管理依赖关系的 `requirements.txt` 文件是最新的。
