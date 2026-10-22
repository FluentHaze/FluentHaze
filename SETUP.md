# FF 主页安装说明

## 安装

1. 登录 liuhui9，创建公开仓库 `liuhui9`。如果已存在，请先备份原 README 和工作流，再合并这些文件。
2. 将本目录内容放进仓库根目录，保持结构：

   ```text
   README.md
   assets/
     header.svg
     snake-pending.svg
   .github/
     workflows/
       profile-snake.yml
   ```

3. `.github` 是隐藏目录，务必一并上传。网页上传时若未包含它，使用 Add file → Create new file，文件名填写 `.github/workflows/profile-snake.yml`，粘贴对应内容。
4. 打开仓库 Actions → Generate contribution snake → Run workflow，等待成功。首次上传工作流到 main/master 通常也会自动触发。
5. 成功后会生成 `output` 分支；访问 https://github.com/liuhui9 查看效果。图片可能有缓存，需要稍等再刷新。

## 功能

- 自带动态 SVG 封面：轨道粒子、闪烁光标；不依赖图片生成服务。
- 循环打字标题、统一配色徽章、仓库入口、关注人数。
- GitHub 公开统计与语言分布：通过第三方图片服务生成。
- 贡献贪吃蛇：按系统浅色/深色偏好选择动画，每日北京时间约 09:17 更新。GitHub 定时任务可能延迟。
- 静态封面主体及动画替代文本在动画不可用时仍可阅读；封面尊重减少动态效果偏好。

## 发布前调整

展示名为 FF，GitHub 账号、仓库名、图片数据源仍使用 liuhui9。由于本次未能读取个人公开资料，介绍与工程关注点是可编辑文案，技术徽章是可编辑模板，未填写职业、邮箱、履历或具体项目。请根据真实情况编辑 README 的介绍和技术区。

可在 GitHub 主页 Customize your pins 中置顶真实项目，不必手工维护项目卡片数据。

## 故障排查

- 贪吃蛇：检查 Actions 是否启用，运行是否成功，以及 output 分支是否有两个 SVG 文件。配置已有 `contents: write`；组织策略禁止时需要仓库管理员允许工作流写入。
- 如果 README 所在分支既不是 main 也不是 master，请修改工作流 push 分支列表；手动触发和定时运行仍以默认分支上的工作流为准。
- 首次运行前，浅色/深色 source 指向尚未生成的文件，可能显示替代文本；这不是已有贡献数据。工作流成功后才有真实动画。
- 打字、徽章或统计无法显示：第三方服务可能限流或不可用，文字和 GitHub 原生仓库入口仍可使用。未设置任何付费服务或私人 Token。
- 仓库长期没有活动时，GitHub 可能暂停定时工作流；到 Actions 页面重新启用。

## 参考与验证范围

- Profile README：https://docs.github.com/en/account-and-profile/how-tos/profile-customization/managing-your-profile-readme
- 打字 SVG：https://github.com/DenverCoder1/readme-typing-svg
- 统计卡片：https://github.com/stats-organization/github-stats-extended
- 贡献动画：https://github.com/Platane/snk
- 发布 Action：https://github.com/peaceiris/actions-gh-pages

已提供本地文件与工作流配置。真正的 GitHub 渲染、图片服务可用性和 Actions 执行结果，需要上传到同名仓库后验证。本次没有执行 git commit、git push 或修改远程仓库。
