# Mika 镜像说明（非上游官方仓库）

本仓库是 **[wangzan101/Mika](https://github.com/wangzan101/Mika)** 标签 `v0.1.38` 的**只读镜像备份**，
用于在国内网络环境下稳定获取源码与安装包。所有代码版权归上游作者，许可为 **Apache-2.0**（见 `LICENSE` / `NOTICE`）。

- 上游仓库：https://github.com/wangzan101/Mika
- 上游官网：https://mikaphone.com
- 镜像抓取时间：2026-11-09
- 镜像对应上游提交：`main` @ 2026-11-07T17:30:06Z（`fix: 按 UTF-8 读取二维码页面测试`）

## 下载（本仓库 Release `v0.1.38`）

| 文件 | 大小 | SHA-256 |
|---|---|---|
| `Mika-v0.1.38-arm64.apk` | 81,553,435 B | `cecb36d22e3ed604489b950f9bdb891b3a269c9135eac6789195cd3a2d9538f0` |
| `Mika-v0.1.38.apk`（通用） | 94,149,578 B | `f9e13f1da821a49026bbe611474614682b9cc7efc46ce67ebecfcd1e61d1fe12` |
| `mika-src-v0.1.38.tar.gz` | 50,806,276 B | `360790b6016d5e3147308bba01f49b9a646685fdb8e83eda0f3a4a70bdd917a6` |

三个文件均与上游 GitHub 发布物 **字节级一致**（SHA-256 由 GitHub Release API 回传的 digest 交叉核对）。

## 安装前须知

- APK 由上游作者签名，**本镜像未重新打包**。安装时若提示"未知来源"，属正常。
- 需要 **Android 11+**（聊天/网页/文件）；**操作其他 App 需 Android 12+，推荐 14+**；Linux 沙箱需 **arm64**。
- 首次使用要在设置里填**自己的模型 API Key**（或登录 ChatGPT / xAI / OpenRouter 账号），作者不提供任何模型额度。
- 操作第三方 App 可能违反其服务条款，重要操作建议用 Ask 模式逐笔确认。

## 源码目录速览

| 目录 | 内容 | 体积 |
|---|---|---|
| `app/` | Android 应用主体（Kotlin + Jetpack Compose） | 38.8 MB |
| `core/` | 核心逻辑（agent 循环、无障碍操作、浏览器） | 6.7 MB |
| `docs/` | 文档与演示 GIF | 14.3 MB |
| `tools/` `eval/` | 辅助工具与评测 | 0.5 MB |

其中 `app/src/main/assets/runtime/rootfs.tar.xz`（31.5 MB）是 Linux 沙箱根文件系统，
`app/src/main/jniLibs/arm64-v8a/libproot.so` 是 proot 二进制——这两者占了仓库体积的一半以上。
