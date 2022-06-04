<!DOCTYPE html>
<html lang="zh-CN">
<head>
	<meta charset="UTF-8">
	<meta name="author" content="kyrieliu">
	<meta name="description" content="a im web app built by kyrieliu">
	<meta name="viewport" content="width=device-width,initial-scale=1,user-scalable=no">
	<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
	<title>KChat</title>
	<link rel="icon" href="http://kyrieliu.cn/kyrie.ico">

	<!-- 新 Bootstrap 核心 CSS 文件 -->
	<link rel="stylesheet" href="http://cdn.bootcss.com/bootstrap/3.3.0/css/bootstrap.min.css">
html,body,div,h1,h2,h3,h4,h5,h6,p,span{
	padding: 0;
	margin: 0;
	overflow: hidden;
}

body{
	padding-top: 10px;
	overflow: auto;
}


.chat-container{
	position: relative;
}

.banner{
	border: 1px solid black;
	height: 80px;

}

.historyMsg{
	border: 1px solid black;
	height: 400px;
	padding: 5px;
	position: relative;
	overflow: auto;
}

.newMsg{
	text-align: left;
	margin-top: 5px;
}

.nickname{
	font-weight: bold;
}

.timespan{
	color: #ddd;
}

.myMsg{
	text-align: right;
	margin-top: 5px;
}

/*系统消息*/
.system{
	text-align: center;
	background-color: grey;
	color: white;
	border-radius: 5px;
	opacity: 0.6;
	margin: 5px 10px;
}

.control{
	border: 1px solid black;
	height: 115px;
}

.control-row{
	margin-top: 10px;
}

.inputMsg{
	height: 50px !important;
	resize: none;
}

.sendBtn{
	height: 50px;
}

footer{
	text-align: center;
}

.loginWrapper{
	position: fixed;
	top: 0;
	right: 0;
	bottom: 0;
	left: 0;
	text-align: center;
	display: block;
	background-color: rgba(5,5,5,0.5);
	padding-top: 200px;
}

.info{
	color: white;
	font-size: 20px;
}

.nickWrapper{
	display: none;
}

/* Tablets: 768px */
@media screen and (max-width: 760px){

	.historyMsg{
		font-size: 10px;
		border: 0px;
		height: 330px;
		padding: 5px;
		position: relative;
		overflow: auto;
	}

	.banner{
		border: 0px;
		border-bottom: 1px solid gray;
	}

	.inputMsg{
		margin-bottom: 2px;
	}

	.control{
		border: 0px;
	}

	footer{
		font-size: 15px;
	}
}

</head>
<body>
	
	<div class="container chat-container">
		<!-- 标题header -->
		<div class="row">
			<div class="col-md-6 col-md-offset-3 col-sm-12 banner">
				<h1>KChat v1.0</h1>
				<span id="status">0</span>
				<span>人在线</span>
			</div>
		</div>
		
		<!-- 历史消息 -->
		<div class="row">
			<div class="col-md-6 col-md-offset-3 col-sm-12 historyMsg" id="historyMsg">
				<!-- <p class="newMsg">
					<span class="nickname">kyrieliu</span>
					<span class="timespan">(21:00:15):</span>
					去去去去去去去去去去去去去
				</p>

				<p class="myMsg">
					<span class="timespan">(22:12:11):</span>
					了了了了了了了了了了了了
				</p>


				<p class="system"><span class="nickname">kyrieliu</span>加入了群聊</p> -->
				
			</div>
		</div>
		
		<!-- 控制台 -->
		<div class="row">
			<div class="col-md-6 col-md-offset-3 col-sm-12 control">
				<div class="row control-row">
					<div class="col-md-8 col-sm-8">
						<textarea id="inputMsg" class="inputMsg form-control"></textarea>
					</div>
					<div class="col-md-4 col-sm-4">
						<button id="sendBtn" class="form-control sendBtn btn btn-primary">send</button>
					</div>
				</div>
			</div>
		</div>

		<div id="loginWrapper" class="loginWrapper">
			
			<p id="info" class="info">Connecting to kyrieliu's server...</p>
			
			<div id="nickWrapper" class="nickWrapper col-md-4 col-md-offset-4 col-sm-12">
				<input type="text" placeholder="input your nickname" id="nicknameInput" class="form-control" />
				<input type="button" class="btn btn-success" id="loginBtn" value="Login" />
			</div>
		</div>
	</div>



	<footer>
		<small>Designed and built by <a href="http://kyrieliu.cn" target="_blank">kyrieliu</a></small>
	</footer>
	

	<script src="/socket.io/socket.io.js"></script>
	<script src="script/kchat.js"></script>
	
	<!-- share 
	<script src="http://res.wx.qq.com/open/js/jweixin-1.0.0.js"></script>
	<script>
		//wechat moment
		wx.onMenuShareTimeline({
		    title: 'KChat|丑陋聊天室', // 分享标题
		    link: 'http://kyrieliu.cn:8080', // 分享链接
		    imgUrl: 'http://kyrieliu.cn/kyrie.jpg', // 分享图标
		    success: function () { 
		        // 用户确认分享后执行的回调函数
		    },
		    cancel: function () { 
		        // 用户取消分享后执行的回调函数
		    }
		});

		//wechat friends
		wx.onMenuShareAppMessage({
		    title: 'KChat|丑陋聊天室', // 分享标题
		    desc: 'Powered by kyrieliu', // 分享描述
		    link: 'http://kyrieliu.cn:8080', // 分享链接
		    imgUrl: 'http://kyrieliu.cn/kyrie.jpg', // 分享图标
		    type: 'link', // 分享类型,music、video或link，不填默认为link
		    dataUrl: '', // 如果type是music或video，则要提供数据链接，默认为空
		    success: function () { 
		        // 用户确认分享后执行的回调函数
		    },
		    cancel: function () { 
		        // 用户取消分享后执行的回调函数
		    }
		});
	</script>
	-->
</body>
</html>
