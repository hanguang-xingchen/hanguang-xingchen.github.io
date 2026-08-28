---
name: office-reader
description: Extract text from Word (.docx), Excel (.xlsx), and PowerPoint (.pptx) files. Use when the user asks to read, summarize, or analyze Office documents.
---

# Office Document Reader

When the user asks to read, summarize, or analyze a `.docx`, `.xlsx`, or `.pptx` file:

1. **Run the extraction script:**

   ```bash
   python3 .qwen/skills/office-reader/scripts/extract_office.py <absolute-path-to-file>
   ```

2. **Parse the JSON output** to get the extracted text content.

3. **Answer the user's question** based on the extracted content.

## Supported formats

| Format | Extension | Notes |
|--------|-----------|-------|
| Word   | `.docx`   | Paragraphs + tables |
| Excel  | `.xlsx`   | All sheets, cell values with coordinates |
| PowerPoint | `.pptx` | Slide-by-slide text + tables |

## Examples

- "帮我读一下这个文档" → 运行脚本 → 总结内容
- "这个 Excel 里有什么数据？" → 运行脚本 → 概述 sheet 和关键数据
- "这个 PPT 讲了什么？" → 运行脚本 → 按 slide 总结要点

## Limitations

- 不支持旧格式 `.doc` `.xls` `.ppt`（需用户另存为 .docx/.xlsx/.pptx）
- Excel 输出为单元格坐标=值格式，大文件可能输出很长
- 图片中的文字、图表图形等无法提取
