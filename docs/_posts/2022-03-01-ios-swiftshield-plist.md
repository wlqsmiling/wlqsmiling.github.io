# ios swiftshield代码混淆问题和解决

## code obfuscation <https://github.com/rockbruno/swiftshield> <https://github.com/wlqsmiling/swiftshield.git>

- Requirements & Limitations
- 编译器选择iphoneos，不需要支持模拟器
- 同一个代码文件被多个target引用
- MKVideoItem继承了MediaItem protocol和NSObject
- GroupChatMessage 继承了BaseMessage和Codable
- storyboard中对应class，customClass="" 替换map表
- storboard中对应事件action selector="" 替换map表
- xib中对应事件action selector="" 替换map表
- xib中类名忽略掉，原因是代码加载资源需要文件名字