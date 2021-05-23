# Quantumult X 解锁 TikTok 看国际抖音不拔卡规则

### 操作步骤<br>
1、下载 Quantumult X 和 TikTok，需要用美区AppleID下载，下载完先不要打开TikTok。<br>
- 注册美国AppleID教程：https://github.com/kjfx/AppleID<br>

2、打开 Quantumult X<br>
3、打开 <code>重写</code> 和 <code>MitM</code> 开关<br>
4、在MitM选项下，点击生成证书 → 配置证书 → 安装描述文件 → 信任证书设置<br>
5、在 <strong><code>[rewrite_local]</code></strong> 中添加以下重写代码<br>

    (?<=_region=)CN(?=&) url 307 JP
    (?<=&mcc_mnc=)4 url 307 2
    ^(https?:\/\/(tnc|dm)[\w-]+\.\w+\.com\/.+)(\?)(.+) url 302  $1$3
    (?<=\d\/\?\w{7}_\w{4}=)1[6-9]..(?=.?.?&) url 307 17


6、在 <strong><code>[mitm]</code></strong> 中添加以代码<br>

    hostname = *.tiktokv.com, *.byteoversea.com, *.tik-tokapi.com

7、Quantumult X 添加节点，开启科学上网<br>
8、打开TikTok<br><br>

### 温馨提示：
默认是日本区，可以更改这行代码最后面的JP  <code>(?<=_region=)CN(?=&) url 307 JP</code><br>
美国示例：(?<=_region=)CN(?=&) url 307 US<br>
英文简写 JP（日本）｜KR（韩国）｜UK（英国）｜US（美国）｜TW（台湾）<br>
