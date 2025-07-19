# Cursor与GitHub对话共享教程

## 📖 教程简介

本教程将指导团队成员如何通过Git和GitHub实现Cursor IDE的对话共享功能。通过学习本教程，您将能够：

- 配置Cursor IDE的对话导出功能
- 使用Git管理对话文件
- 通过GitHub与团队成员共享AI对话记录
- 建立高效的团队协作流程

## 🎯 学习目标

完成本教程后，您将能够：
- 独立安装和配置Git与Cursor IDE
- 设置Cursor的对话导出规则
- 使用Git命令管理对话文件
- 与团队成员协作共享AI对话

## 📋 前置要求

在开始本教程之前，请确保您具备以下条件：
- Windows 10或更高版本操作系统
- 稳定的网络连接
- 基本的计算机操作技能
- GitHub账户（团队使用同一个号就行）

## 📚 教程大纲

1. **环境准备** - 安装Git和Cursor IDE
2. **GitHub账户设置** - 创建账户和配置Git全局设置
3. **Git基础操作** - 克隆仓库和使用Cursor打开项目
4. **Cursor配置** - 设置对话导出规则
5. **对话共享流程** - 完整的协作工作流程
6. **具体实践** - 团队协作建议和注意事项

---

## 第一步：环境准备

### 1.1 安装Git

Git是分布式版本控制系统，是团队协作的基础工具。

#### 下载Git
1. 访问Git官方网站：https://git-scm.com/
2. 点击"Download for Windows"下载最新版本
3. 下载完成后，运行安装程序

#### 安装步骤
1. **许可协议**：阅读并接受Git许可协议
2. **安装位置**：建议使用默认安装路径（通常是`C:\Program Files\Git`）
3. **组件选择**：保持默认选项，确保选中以下组件：
   - Windows Explorer integration
   - Git Bash Here
   - Git GUI Here
   - Git LFS (Large File Support)
   - Associate .git* configuration files with the default text editor
   - Associate .sh files to be run with Bash
4. **开始菜单文件夹**：使用默认的"Git"文件夹
5. **默认编辑器**：建议选择"Use Visual Studio Code as Git's default editor"
6. **PATH环境**：选择"Git from the command line and also from 3rd-party software"
7. **HTTPS传输后端**：选择"Use the OpenSSL library"
8. **行尾符号处理**：选择"Checkout Windows-style, commit Unix-style line endings"
9. **终端模拟器**：选择"Use MinTTY"
10. **git pull行为**：选择"Default"
11. **凭证管理器**：选择"Git Credential Manager"
12. **额外选项**：保持默认设置
13. **实验性功能**：不勾选任何选项

#### 验证Git安装
安装完成后，打开PowerShell或命令提示符，输入以下命令验证：
```powershell
git --version
```

如果安装成功，您将看到**类似**以下的输出：
```
git version 2.35.0.windows.1
```

### 1.2 安装Cursor IDE

Cursor是基于AI的代码编辑器，内置了强大的AI编程助手功能。

#### 下载Cursor
1. 访问Cursor官方网站：https://cursor.com/
2. 点击"Download for Windows"下载最新版本
3. 下载完成后，运行安装程序

#### 安装步骤
1. **许可协议**：阅读并接受Cursor许可协议
2. **安装位置**：建议使用默认安装路径
3. **开始菜单**：选择是否创建开始菜单快捷方式
4. **桌面快捷方式**：建议勾选创建桌面快捷方式
5. **文件关联**：选择要关联的文件类型（建议保持默认）
6. **完成安装**：等待安装完成

#### 首次启动配置
1. **登录账户**：使用GitHub账户登录Cursor
2. **选择主题**：选择您喜欢的编辑器主题
3. **扩展推荐**：安装推荐的扩展（可选）
4. **AI设置**：配置AI助手偏好设置

#### 环境检查清单
- [ ] Git安装成功，版本号显示正常
- [ ] Cursor IDE启动正常

### 下一步

完成环境准备后，我们将进入第二步：GitHub账户设置和Git全局配置。

---

## 第二步：GitHub账户设置

### 2.1 登录GitHub

#### 通过Google账号登录GitHub

为了简化登录流程，我们推荐使用Google账号登录GitHub：

1. **登录Google账号**
   - 打开浏览器，访问 https://accounts.google.com/
   - 输入您的Google账号邮箱和密码
   - 完成双重验证（如果已启用）

2. **访问GitHub并选择Google登录**
   - 访问GitHub官网：https://github.com/
   - 点击右上角的"Sign in"按钮
   - 在登录页面选择"Continue with Google"选项

3. **授权GitHub访问**
   - 系统会跳转到Google授权页面
   - 确认授权GitHub访问您的Google账号信息
   - 完成授权后自动跳转回GitHub


### 2.2 配置Git全局设置

登录GitHub后，需要在本地配置Git的全局用户信息。团队将使用统一的账号进行协作：

#### 配置命令
在PowerShell或Cursor终端中运行以下命令：
```powershell
git config --global user.name "xiongdishangche"
git config --global user.email "xiongdishangche@gmail.com"
```

#### 验证配置
运行以下命令确认配置成功：
```powershell
git config --global user.name
git config --global user.email
```

应该显示：
```
xiongdishangche
xiongdishangche@gmail.com
```

### 下一步

完成GitHub账户设置后，我们将进入第三步：学习Git基础操作。

---

## 第三步：Git基础操作

### 3.1 克隆GitHub仓库

现在我们将从GitHub拉取团队的项目仓库，这个仓库包含了预配置的Cursor设置和示例文件。

#### 克隆仓库
在PowerShell或命令提示符中运行以下命令：
```powershell
# 克隆已有仓库demo到本地
git clone https://github.com/xiongdishangche/demo.git
```

#### 命令说明
- `git clone`：克隆远程仓库到本地
- `https://github.com/xiongdishangche/demo.git`：团队项目的GitHub地址
- 默认会克隆 `main` 分支的内容

#### 克隆结果
克隆成功后，您将看到类似以下的输出：
```
Cloning into 'demo'...
remote: Enumerating objects: X, done.
remote: Counting objects: 100% (X/X), done.
remote: Compressing objects: 100% (X/X), done.
Unpacking objects: 100% (X/X), done.
```

### 3.2 使用Cursor打开项目

#### 打开项目
1. **启动Cursor IDE**
2. **将刚刚克隆的文件夹拖动到cursor中**

### 下一步

完成Git基础操作后，我们将进入第四步：配置Cursor的对话导出功能。

---

## 第四步：Cursor配置

### 4.1 打开Cursor设置界面

在配置对话导出规则之前，我们需要先打开Cursor的设置界面：

#### 打开设置步骤
1. **打开设置界面**
2. **导航到Rules & Memories**: 在左侧设置菜单中找到并点击 `Rules & Memories`

#### 找到User Rules部分
在Rules & Memories设置页面中，您会看到以下主要部分：
- **Memories Section**：用于管理AI记忆功能
- **User Rules Section**：这是我们需要的部分
- **Project Rules Section**：用于项目特定规则

### 4.2 添加对话导出规则

在User Rules部分，我们需要添加对话导出功能的配置规则：

#### 添加规则步骤
1. **点击"+ Add Rule"按钮**：在User Rules部分找到蓝色的"+ Add Rule"按钮
2. **输入规则内容**：将以下配置复制粘贴到规则文本框中
3. **保存规则**：规则会自动保存并生效

#### 配置内容
```yaml
---
alwaysApply: true
---
version: "1"
projectRules:
  - name: 导出对话
    description: |
      当用户发送 "导出对话" 指令时，
      将本次会话的完整内容导出为 Markdown 文件。
      文件名使用 PowerShell 获取的毫秒级时间戳。
    trigger:
      event: onCommand
      command: "导出对话"
    action:
      type: write_file
      config:
        # 输出到项目根目录下的 uncategorized 目录
        directory: "./uncategorized"
        # filename 支持模板：
        #   {{exec:...}} 会在写文件前执行对应的 PowerShell 命令
        #   {{summary}} 会渲染为 AI 对本次用户提问的简短总结
        filename: "{{exec:Get-Date -Format \"yyyyMMdd_HHmmss_fff\"}}-{{summary}}.md"
        content: |
          # 对话导出

          **导出时间**：{{date:YYYY-MM-DD HH:mm:ss.SSS}}

          ## 完整对话
          {{conversation}}
```

#### 配置说明
- **alwaysApply: true**：规则始终生效
- **trigger**：当用户输入"导出对话"时触发
- **action**：执行文件写入操作
- **directory**：文件保存到 `./uncategorized` 目录
- **filename**：使用时间戳和AI总结生成文件名
- **content**：定义导出文件的格式和内容

### 4.3 验证配置

#### 测试对话导出功能
1. **确保规则已保存**：在User Rules部分确认规则已正确添加
2. **开始与AI对话**：在Cursor中与AI助手进行一些问答
3. **输入导出命令**：在对话框中输入"导出对话"
4. **检查结果**：
   - 查看项目根目录下是否创建了 `uncategorized` 文件夹
   - 确认是否生成了带时间戳的Markdown文件
   - 验证文件内容是否包含完整的对话记录

#### 验证清单
- [ ] User Rules中已成功添加对话导出规则
- [ ] 输入"导出对话"命令后能正常响应
- [ ] 在 `uncategorized` 目录中生成了对话文件
- [ ] 文件名格式正确（时间戳-总结.md）
- [ ] 文件内容包含完整的对话记录

#### 常见问题解决
- **规则未生效**：检查User Rules部分是否正确保存了规则
- **文件未生成**：确认项目目录有写入权限
- **文件名异常**：检查PowerShell命令是否在Windows环境下正常运行

### 下一步

完成Cursor配置后，我们将进入第五步：对话共享流程。

---

## 第五步：对话共享流程

### 5.1 基本流程

对话共享的核心流程非常简单：每次与AI对话结束后，发送"导出对话"命令即可自动生成对应的对话文档。

#### 流程步骤
1. **进行AI对话**：在Cursor中与AI助手进行问答交流
2. **结束对话**：完成当前话题的讨论
3. **导出对话**：在对话框中输入"导出对话"
4. **自动生成**：系统自动创建带时间戳的Markdown文件
5. **团队共享**：通过Git提交和推送分享给团队成员

### 5.2 使用"导出对话"命令

#### 命令触发
- **触发词**：在对话框中输入"导出对话"
- **触发时机**：对话进行中或结束后均可
- **响应方式**：AI助手会自动执行导出操作

#### 生成的文件
- **文件位置**：项目根目录下的 `uncategorized` 文件夹
- **文件命名**：`YYYYMMDD_HHMMSS_fff-对话总结.md`
- **文件内容**：包含完整的对话记录和导出时间

#### 示例输出
```
uncategorized/
└── 20250719_203545_999-关于正十七边形构造的讨论.md
```

### 5.3 团队协作流程

#### 个人操作流程
1. **开始对话**：在Cursor中与AI进行编程讨论
2. **完成讨论**：解决当前问题或完成阶段性工作
3. **导出对话**：输入"导出对话"命令
4. **提交更改**：使用Git提交新生成的对话文件
5. **推送到远程**：将对话文件推送到GitHub仓库，直接通过IDE的GUI操作（具体操作观看视频）

#### 团队共享效果
- **实时同步**：团队成员可以立即看到新的对话记录
- **知识积累**：所有有价值的对话都被保存和共享
- **问题解决**：团队成员可以查看历史对话解决类似问题
- **经验传承**：新成员可以通过对话记录快速学习

### 下一步

完成对话共享流程学习后，我们将进入最后一步：最佳实践和注意事项。

---

## 第六步：具体实践

### 6.1 团队协作规范

为了确保团队协作的顺利进行，请严格遵守以下规范：

#### 📁 文件夹管理规范
- **一人一个文件夹**：每个团队成员使用自己的专属文件夹
- **不要乱添加**：不要在其他成员的文件夹中创建或修改文件
- **文件夹命名**：使用自己的姓名或用户名作为文件夹名称
- **示例结构**：
  ```
  demo/
  ├── test-a/
  │   └── 对话文件...
  ├── test-b/
  │   └── 对话文件...
  └── uncategorized/
      └── 默认导出对话的公共文件夹，未分类文件...
  ```

#### 🔄 Git操作规范
- **导出后立即提交**：每次导出对话完成后，建议立即提交文件变更
- **先拉取再推送**：推送前必须先拉取最新代码，避免冲突
- **提交信息规范**：使用清晰的提交信息，如"添加对话：关于XXX的讨论"

#### 标准操作流程（如果学会通过GUI操作，可以不用使用命令）
1. **导出对话**：完成AI对话后输入"导出对话"
2. **检查文件**：确认文件已正确生成在指定位置
3. **拉取最新代码**：`git pull origin main`
4. **提交变更**：`git add .` 然后 `git commit -m "添加对话：具体内容描述"`
5. **推送到远程**：`git push origin main`

### 6.2 常见问题与解决方案

#### 文件冲突处理
- **冲突原因**：多人同时修改同一文件
- **解决方法**：
  1. 先拉取最新代码：`git pull origin main`
  2. 解决冲突：手动编辑冲突文件
  3. 重新提交：`git add .` 然后 `git commit -m "解决冲突"`
  4. 推送：`git push origin main`

#### 文件夹权限问题
- **问题表现**：无法在指定文件夹创建文件
- **解决方法**：
  1. 检查文件夹是否存在
  2. 确认当前用户有写入权限
  3. 联系管理员获取必要权限

### 6.3 最佳实践建议

#### 对话管理
- **定期整理**：定期整理和归档重要的对话记录
- **分类存储**：按主题或项目对对话进行分类
- **及时分享**：有价值的对话及时分享给团队成员

#### 团队协作
- **沟通协调**：在修改公共文件前先与团队沟通
- **版本控制**：充分利用Git的版本控制功能
- **备份重要**：重要对话建议本地备份

### 6.4 注意事项总结

⚠️ **重要提醒**：
1. **严格遵循一人一文件夹原则**，不要在其他成员的文件夹中操作
2. **每次导出对话后必须提交变更**，确保内容不会丢失
3. **推送前必须先拉取**，避免代码冲突和覆盖
4. **使用清晰的提交信息**，便于团队理解变更内容
5. **定期同步代码**，保持本地与远程仓库的一致性

### 下一步

恭喜！您已经完成了Cursor与GitHub对话共享教程的学习。现在可以开始使用这套系统进行团队协作了。

---

## 📚 附录

### 常用Git命令速查
```bash
# 查看状态
git status

# 拉取最新代码
git pull origin main

# 添加所有变更
git add .

# 提交变更
git commit -m "提交信息"

# 推送到远程
git push origin main

# 查看提交历史
git log --oneline
```

### 联系支持
如果在使用过程中遇到问题，请联系团队管理员或查看项目文档。 