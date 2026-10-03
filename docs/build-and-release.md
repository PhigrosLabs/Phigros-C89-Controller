# 构建与发布

## 私有仓库本地验证

使用 Flutter 3.44.1 / Dart 3.12.1：

```sh
flutter pub get
flutter analyze
flutter test
flutter build apk --debug
```

Windows 需要 Visual Studio C++ 桌面开发工作负载、CMake 和对应工具链的 ATL；不得提交本机 SDK/头文件绝对路径。Linux 安装 GTK3、libsecret 开发包。Android 使用 JDK 17 与 Flutter 要求的 Android SDK。Apple 平台需 macOS/Xcode；目前不配置 Apple 签名证书。

## 自动构建

私有仓库 push / pull_request / 手动运行触发 GitHub Actions。测试通过后分别构建 Android、Windows、Linux、macOS、iOS；普通提交生成 Debug，发布提交生成 Release，并使用 `--obfuscate --split-debug-info`。混淆不是保密保证，也不是反调试实现。

构建产物保存在私有 Actions artifacts。`private-symbols-*` 仅供维护者还原堆栈，不上传公开仓库。桌面与 Apple 产物用 tar.gz 保留目录结构和权限；Android 另外提供 APK。默认 Android debug 签名不需要上传 keystore，但不同 runner 的密钥可能不同。

## 公开发布

创建形如 `v1.6.7` 的 Git tag，或在提交信息中使用：

```text
feat: 发布新版本

本次更新说明。
[release ver="v1.6.7",pre=false,draft=false]
```

首行为 Release 标题，余下内容去掉标记后作为正文。带后缀的 tag 默认预发布；标记可显式指定 pre/draft。tag 与标记同时存在时版本必须相同。不要将同一版本以分支提交和 tag 重复触发发布；已存在的 Release 不自动覆盖。

发布任务使用 `public-release` 环境。维护者应配置审批人与仅受信任分支/tag 可发布的限制。在私有仓库设置 `PUBLIC_RELEASE_TOKEN`：使用仅能访问公开仓库、具有 Contents write 权限的 fine-grained PAT，或等效 GitHub App token。默认 `GITHUB_TOKEN` 没有跨仓库发布权限。本机 CLI 登录凭据不应直接复制为 Actions secret。

公开仓库仅人工同步经过审核的 `README.md` 和 `docs/build-and-release.md`，绝不推送私有仓库的 Git 历史、notes、源码或 symbols。工作流只将 app-* 产物上传公开 Release。

iOS 输出未签名 .app，不是可直接安装的 IPA；需要开发者自己的签名和分发流程。macOS 尚未公证。实际云端构建与平台安装成功前，不应宣布正式可用。