# ios security

## code obfuscation <https://github.com/rockbruno/swiftshield>

- Requirements & Limitations
- example:XiaoiceiOSLibrary,xeva,
- Error1: xeva:ld: (UMSocialGlobal.o), building for iOS Simulator, but linking in object file built for iOS <https://stackoverflow.com/questions/63607158/xcode-12-building-for-ios-simulator-but-linking-in-an-object-file-built-for-io>
- ExtensionTarget忽略，然后对着映射表修改
- package 忽略
- typealias 不能用
- storyboard中对应class未修改,手动修改
- 必须实现的重写方法被混淆@resultBuilder，buildBlock方法
- 文件名依然可见
- ignore-public问题，重写父类的方法，子类public方法名字未混淆
- symbol(s) not found for architecture x86_64 #if TARGET_IPHONE_SIMULATOR #else #endif
- <https://stackoverflow.com/questions/63267897/building-for-ios-simulator-but-the-linked-framework-framework-was-built>

## string obfuscation

- 字符串常量混淆，防止被窃取 <https://medium.com/swift2go/increase-the-security-of-your-ios-app-by-obfuscating-sensitive-strings-swift-c915896711e6>
- 代码中的字符串字面量混淆,防止搜索到关键代码位置 <https://syrion.me/blog/ios-strings-obfuscation-in-swift/>

## IOSSecuritySuite <https://github.com/securing/IOSSecuritySuite>

### JailbreakChecker(amIJailbroken)

- 检查是否安装越狱工具，系统文件权限等

### DebuggerChecker(denyDebugger)

- PT_DENY_ATTACH ptrace 禁止依附进程

### EmulatorChecker(amIRunInEmulator)

- 检查processinfo,enviroment

### ReverseEngineeringToolsChecker(amIReverseEngineered)

- 检查是否安装逆向工具

### IntegrityChecker(amITampered)

- 检查bundleID,mobileProvision,machO

### ProxyChecker(amIProxied)

- CFNetworkCopySystemProxySettings

### RuntimeHookChecker(amIRuntimeHook)

- 检查某个类的函数是否被hook

## performance

- 20几毫秒

## 数据保护

- <https://medium.com/@ankurvekariya/ios-app-security-tips-and-tricks-42cdf9301181>

- <https://quickbirdstudios.com/blog/ios-app-security-best-practices/>

### 网络数据

- 取消代理，防止中间人

### 存储数据

- 不重要的数据userdefault里面
- 重要数据 Keychain 加密存储

## 其他

- <https://developer.apple.com/security/>
- <https://wwdcbysundell.com/2021/security-and-privacy-at-wwdc21/#application-security-101-for-app-developers>