# 播客日常工作流程

## 目录结构

```
podcast/
├── recording/
│   ├── MM_DD_YYYY/          # 每期录音文件夹，按日期命名
│   │   ├── 嘉宾缩写/        # 每位嘉宾的原始录音
│   │   │   └── *.m4a
│   │   └── *.band           # GarageBand 剪辑工程文件
│   └── TEMPLATE_MM_DD_YY/   # 新建期数时复制此模板
├── script/                  # 脚本和提纲
└── doc/                     # 文档
```

---

## 录制前

1. 复制 `recording/TEMPLATE_MM_DD_YY/` 文件夹，重命名为当期日期（如 `03_08_2026`）
2. 在 `script/` 里准备好本期提纲

## 录制中

- 每位嘉宾在自己的文件夹下录制，文件格式为 `.m4a`
- 命名规则：`主题_嘉宾缩写.m4a`（如 `音乐与人生_hyt.m4a`）

## 录制后

1. 将各嘉宾录音导入 GarageBand 工程文件（`.band`）进行剪辑混音
2. 导出成品音频

## 上传到 GitHub

```bash
git add .
git commit -m "Add recording MM/DD/YYYY: 本期主题"
git push
```

> **注意**：有版权的音乐文件（.ncm、.mp3、嘉宾分享的歌曲）不会被上传，已在 `.gitignore` 中排除。
