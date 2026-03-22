# 播客日常工作流程

## 目录结构

```
podcast/
├── recording/
│   ├── MM_DD_YYYY/          # 每期录音文件夹，按日期命名
│   │   ├── 嘉宾缩写/        # 每位嘉宾的素材（录音、图片等）
│   │   └── 工程文件/        # 剪辑工程文件（GarageBand .band / Audition .sesx 等）
│   └── TEMPLATE_MM_DD_YY/   # 新建期数时复制此模板
├── script/                  # 脚本和提纲
└── doc/                     # 文档
```

---

## 分支命名规则

每期对应一个独立分支，格式为：

```
ep/MM-DD-YYYY
```

示例：`ep/03-08-2026`

---

## Sprint Captain 工作流

> **每期由 Sprint Captain 负责创建分支和初始化目录结构。**

```bash
# 1. 切换到最新的 main
git checkout main
git pull

# 2. 创建新一期的分支
git checkout -b ep/MM-DD-YYYY

# 3. 复制 template 文件夹，重命名为当期日期
cp -r recording/TEMPLATE_MM_DD_YY recording/MM_DD_YYYY

# 4. 提交初始结构
git add recording/MM_DD_YYYY/
git commit -m "Init episode MM/DD/YYYY"
git push -u origin ep/MM-DD-YYYY
```

---

## 组员工作流

> **各组员在对应期数的分支下，将素材放入自己的文件夹后 push。**

```bash
# 1. 拉取并切换到当期分支
git fetch origin
git checkout ep/MM-DD-YYYY

# 2. 将录音、图片等素材放入 recording/MM_DD_YYYY/自己的缩写文件夹/

# 3. 提交并推送
git add recording/MM_DD_YYYY/自己的缩写/
git commit -m "Add [自己的名字] materials for MM/DD/YYYY"
git push
```

---

## 收尾（所有素材齐全后）

由 Sprint Captain 发起 Pull Request，将 `ep/MM-DD-YYYY` 合并回 `main`。

---

> **注意**：有版权的音乐文件（.ncm、.mp3、嘉宾分享的歌曲）不会被上传，已在 `.gitignore` 中排除。
