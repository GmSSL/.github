# GmSSL

GmSSL 是围绕国产商用密码算法、SSL/TLS/TLCP 协议、多语言接口和密码应用集成工具建设的开源项目组。

GmSSL 核心密码库由北京大学自主开发，主仓库位于
[guanzhi/GmSSL](https://github.com/guanzhi/GmSSL)。核心库以 C 语言实现国密算法、X.509 证书、数字信封、TLCP 1.1、TLS 1.2、TLS 1.3 及 RFC 8998 国密套件，提供命令行工具，并支持 SDF、SKF 等典型国产密码硬件接口。

`github.com/GmSSL` 组织主要承载 GmSSL 生态仓库，帮助开发者在不同编程语言和应用环境中使用 GmSSL。

## 当前状态

GmSSL 生态仓库以 [guanzhi/GmSSL](https://github.com/guanzhi/GmSSL) 的最新 Release 作为默认集成基线。截至 2026 年 6 月，组织内主要语言绑定和应用集成项目已完成 GmSSL 3.2.0 适配，并在默认 GitHub Actions 配置中通过构建和测试。

当前已验证的项目包括 Java、Python、PHP、Go、Rust、Node.js 语言接口，SoftSDF 软件密码设备接口，以及面向应用集成的 [nginx-gmssl](https://github.com/GmSSL/nginx-gmssl) 和 [curl-gmssl](https://github.com/GmSSL/curl-gmssl)。

## 仓库总览

### 多语言接口

| 仓库 | 说明 |
| --- | --- |
| [GmSSL-Java](https://github.com/GmSSL/GmSSL-Java) | 以 JNI 方式实现的 Java 语言接口。 |
| [GmSSL-Python](https://github.com/GmSSL/GmSSL-Python) | GmSSL 的 Python 语言接口。 |
| [GmSSL-PHP](https://github.com/GmSSL/GmSSL-PHP) | 以 PHP 扩展方式实现的 PHP 语言接口。 |
| [GmSSL-Go](https://github.com/GmSSL/GmSSL-Go) | 以 cgo 方式实现的 Go 语言接口。 |
| [gmssl-rs](https://github.com/GmSSL/gmssl-rs) | 面向 Rust 的 GmSSL 封装，覆盖 SM2、SM3、SM4、SM9、ZUC、X.509 等功能。 |
| [GmSSL-Nodejs](https://github.com/GmSSL/GmSSL-Nodejs) | 面向 Node.js 的国密算法接口。 |

### 集成和测试

| 仓库 | 说明 |
| --- | --- |
| [SoftSDF](https://github.com/GmSSL/SoftSDF) | SDF 密码设备接口的软件实现，适合在没有硬件密码设备时进行开发和测试。 |
| [nginx-gmssl](https://github.com/GmSSL/nginx-gmssl) | 集成 GmSSL 的 Nginx 分支，用于验证和部署 TLCP、TLS 1.2、TLS 1.3 及国密套件服务端能力。 |
| [curl-gmssl](https://github.com/GmSSL/curl-gmssl) | 集成 GmSSL 的 curl 分支，用于命令行和客户端场景下的国密 TLS/TLCP 访问测试。 |

## 生态能力

GmSSL 生态覆盖常见国密应用开发场景：

* 国密算法：SM2 加密和签名、SM3 哈希、SM4 分组密码及多种工作模式、SM9 标识密码、ZUC 序列密码。
* 证书和数字信封：X.509 证书、CRL、CSR、加密私钥、SM2 数字信封。
* 安全通信协议：TLCP 1.1、TLS 1.2、TLS 1.3 及国密套件。
* 跨平台部署：Linux、macOS、Windows、Android、iOS、OpenHarmony 和嵌入式环境。
* 密码硬件接入：支持 SDF、SKF 等密码硬件接口，并可通过 SoftSDF 做软件化测试。
* 多语言开发：Java、Python、PHP、Go、Rust、Node.js 项目可以通过对应接口调用 GmSSL。
* 应用集成：可以通过 nginx-gmssl 和 curl-gmssl 验证服务端、客户端和命令行工具中的国密 TLS/TLCP 使用场景。

## 上手路径

1. 从 [guanzhi/GmSSL](https://github.com/guanzhi/GmSSL) 获取核心库源码，完成编译、测试和安装。
2. 根据项目语言选择对应的绑定仓库。
3. 按照绑定仓库 README 和示例配置头文件路径、库路径和运行时加载路径。
4. 如需开发或测试 SDF 密码硬件接口，可使用 [SoftSDF](https://github.com/GmSSL/SoftSDF)。
5. 如需测试服务端或客户端协议集成，可参考 [nginx-gmssl](https://github.com/GmSSL/nginx-gmssl) 和 [curl-gmssl](https://github.com/GmSSL/curl-gmssl)。

## 核心库特性

GmSSL 3 的设计重点包括：

* 超轻量：降低内存需求和二进制体积，核心设计不依赖动态内存，适合 MCU、SOC 等环境。
* 更合规：可以配置为仅包含国密算法和 TLCP 协议，便于满足国密应用和产品检测要求。
* 更安全：支持 TLS 1.3 和 RFC 8998 国密套件，并支持密钥加密保护等安全能力。
* 跨平台：采用 CMake 构建系统，支持桌面、服务器、移动端和特殊平台编译部署。

## 相关链接

* 核心库：[guanzhi/GmSSL](https://github.com/guanzhi/GmSSL)
* 项目组：[github.com/GmSSL](https://github.com/GmSSL)
* 问题反馈：请在相关仓库的 issue tracker 中提交。
