A mobile app that aggregates multiple social networks.

社交网络聚合器

WIKI用于放置服务端与客户端的详细通讯协议！与需求。
README 用于放置系统简介与API概览

#支持平台：
*新浪微博
*QQ空间
*朋友圈（部分）
*Instagram 

# 客户端需求列表：

## 共同功能（发送）：
* 文字（140字上限，ins似乎无上限）
* 图片（新浪微博和朋友圈9张上限，qq空间30张，ins1张）
* 点赞
* 转发（ins叫分享）
* @某人（ins模式有些不一样，但同样可用）
* 拍摄
* 从相册中选取

## 部分共同（发送）：
* 多数是ins不支持
* 位置
* 第三方应用（如微博的长微博，QQ空间的文章，朋友圈的链接分享）
* 分享到朋友圈
                 
## 功能列表：
### A：微博
文字，图片，转发，点赞，@某人，表情，拍摄，签到，点评，更多推送，朋友圈，有声照片，秒拍，定时删，长微博，收款

### B：qq空间
转发，点赞，@人没表情
说说：文字，时间，图片
权限设置：所有人可见，QQ好友可见，指定好友可见，仅自己可见
分享到QQ，分享到腾讯微博，水印相机，视频，签到
添加应用：拍照，语音，日志，位置，二维码，微视，表情说说，趣图，气泡，魅拍，创意相机，拍酷

### C：朋友圈
文字，图片，转发，点赞，@某人，表情，拍摄，文章，小游戏，发送给好友，分享到朋友圈，收藏，复制链接，在浏览器中打开，调整字体，投诉，发送邮件

### D：Instagram
文字，图片，转发，点赞，@某人，拍摄，从相册中选取

#服务器API概览：

##安全、保密项
###账号授权类：baseurl/auth/...
ps:系统安全之重！以后独立出来做个系统（当然是以后）
* 用户登录、注销。
* 用户注册（含使用社交平台账号注册）
* 社交平台授权
* 管理、使用token（每个用户拥有一个token，凭token来区别用户，和访问其他API）

##基本信息项
###用户信息类：baseurl/info/...

* 获取用户基本资料（头像、昵称，性别，年龄....等）
* 更新用户基本资料（同时提交完整的信息表单；如：更改昵称的同时还要提交性别，年龄等内容）

* 获取用户某社交网络的用户资料（包含关注数、粉丝数等较详细）
* 更新用户某社交网络的用户资料（改名，改头像，一键改名，一键统一头像等）

* 获取用户某社交网络的notification(一切notification如微博里面的@我、私信、系统通知整合到一块，自己整合；部分跳网页，部分内部处理)（社交聚合器也有自己的notification，如密码更改，平台更新，邀请用户参加体验报告等）（再说一句，微博的Notification比较复杂，比如评论里面@我会有两个Notification，这个还要再商量）
* 将某notification标记为未读/已读

###用户关系类：baseurl/relate/...
* 获取用户某社交网络的关注列表（返回简单信息。视情况而定，下同）
* 获取用户某社交网络的粉丝列表（QQ好友既是关注也是粉丝，两个API都可以获取好友！以此类推）

* 获取用户某关注/粉丝的详细信息（根据社交平台的不同，返回结果的结构也会不同）
* 操作用户某关注/粉丝（取消关注，拉黑？等待定）

*（待定）发私信，聊天接口？

##简讯处理、推荐系统、骚扰识别、广告屏蔽
###简讯收取操作类：baseurl/feeds/...
* 获取用户某社交网络的新简讯（返回一个能略看的信息）
* 获取用户某简讯的详细信息
* 获取用户某简讯的附件

* 点赞某简讯
* 评论某简讯
* 转发某简讯（若可能）

###简讯发送类：baseurl/publish/...
* 向某平台发送一条简讯（仅原创）


