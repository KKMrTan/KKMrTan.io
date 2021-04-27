---
title: webSocket-使用socketIO实现点对点连接
date: 2017-09-28 15:07:42
tags: WEBSOCKET
---
# 效果
<iframe frameborder="0" src="https://v.qq.com/txp/iframe/player.html?vid=r0555hscry0" allowFullScreen="true" width="100%" height="400" style="margin-bottom: 15px;"></iframe>
* 实现思路:
	- 首先在被控制端打开时通过websocket连接到服务器,成功后获取到socketID,这里是把id拼接到get参数上让控制端获取被控制端的socketID
	- 控制端打开链接后获取到被控制端的socketID,然后告诉服务器已经连接到了这个socketID的被控制端,服务器再广播到这个被控制端
	- 后面就是控制端操作后把操作发送到服务器,服务器再转发到被控制端 从而实现client A -> Server -> client B 这个过程

### [源码地址:https://github.com/KKMrTan/socketIO](https://github.com/KKMrTan/socketIO)