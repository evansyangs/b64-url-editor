# BASE64格式订阅链接编辑器 (小火箭订阅链接编辑器)
一个可以生成和修改ShadowRocket (iOS)、v2rayNG (Android)订阅链接的给工具。

## 网址
<https://www.evansyangs.me/b64-url-editor>

## 支持的协议
+ [v2Ray](https://www.v2ray.com/index.html) (`vmess://...`)：支持TCP、WS、KCP三种传输协议
+ [Trojan-GFW](https://github.com/trojan-gfw/trojan) (`trojan://...`)
+ [Shadowsocks](https://en.wikipedia.org/wiki/Shadowsocks) (`ss://...`)：支持所有加密方式

## 功能
1. 导入格式：订阅链接、节点列表、BASE64文本
2. 修改节点名称、服务器地址、加密方式(ss)、密码(ss,trojan)、传输协议(v2ray)、TLS(v2ray)、WS域名与路径(v2ray)等
3. 新增、刪除节点
4. 合并节点列表
5. **生成二维码**
6. **生成订阅链接**
7. 当BASE64转换器用

## 用法
### 手动导入订阅链接
在API栏位中输入订阅链接，目前只支持导入一个
### 手动添加节点列表
在API或TEXT栏位中输入节点网址列表，支持添加多个节点，不同节点间使用换行(`\n`)、逗号(`,`)或分号(`;`)隔开。
### 手动添加BASE64密文
在BASE64栏位中输入BASE64文本。
### URL Query导入订阅链接
```
https://www.evansyangs.me/b64-url-editor?sub=[your subscrption links]
```
设置`qrcode=yes`可以自动显示二维码
```
https://www.evansyangs.me/b64-url-editor?sub=[your subscrption links]&qrcode=yes
```
### 生成订阅链接
1. 按`订阅链接`，会出现生成确认，点击确认继续生成步骤
2. 输入ID和密码，之后每次输入相同的ID与密码组合可以更新之前的链接内容

### 生成订阅链接注意事項
1. ID和密码不需认证，只要你觉得好记就行，乱打也是可以的。
2. 目前没有设计密码找回机制，若忘记密码请直接换一组新的。
3. ID可以重复，相同ID不同密码会生成不同链接。

### 单纯BASE64转换
+ **文字转BASE64 (encoding)**：URL栏位输入任意文字，切换至BASE64栏位即可看到转换结果。
+ **BASE64转文字 (decoding)**：BASE64栏位输入密文，切换至URL栏位即可看到转换结果。

## known issues
+ clipboard content only loaded once, need to add a listener for clipboard changes
+ adding a new shadowsocks profile may change the height of `operateTab`

## todo
+ [x] 新增节点
+ [x] 生成QR Code
+ [x] 生成订阅链接 (需要api与服务器)
+ [x] 完善URL Query
+ [ ] 完善一键粘贴
+ [ ] 调换节点顺序
+ [x] 多个订阅链接合并
+ [x] 完成README.md
+ [x] 写一篇博客文章
