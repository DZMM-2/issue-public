# 安全说明

## 自动化脚本安全

本仓库包含用于同步 GitHub Project 状态的脚本。

### ⚠️ 重要安全提示

1. **不要在 GitHub Actions 中运行外部脚本**
   - 本仓库是公开的，任何人都可以提交 PR
   - 恶意 PR 可能修改脚本内容
   
2. **推荐的安全做法**
   - 仅在本地或受信任的环境运行 `sync-project-labels.sh`
   - 如需自动化，使用内联脚本而非外部文件
   - 限制 workflow 仅在主分支运行
   - 使用最小权限原则

3. **手动运行方式**
   ```bash
   # 在本地安全环境运行
   ./sync-project-labels.sh
   ```

4. **如需设置自动化**
   - 使用私有服务器的 cron job
   - 或使用 `.github/workflows.example/sync-project-labels-secure.yml` 中的安全版本
   - 确保验证脚本完整性

## 报告安全问题

如发现安全漏洞，请发送邮件至：contact@dzmm.ai