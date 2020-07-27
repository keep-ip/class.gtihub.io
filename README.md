<%@ page language="java" contentType="text/html; charset=UTF-8"
	pageEncoding="UTF-8"%>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<title>用户注册</title>
<link rel="stylesheet"
	href="${pageContext.request.contextPath}/layui/css/layui.css"
	media="all">
<script src="${pageContext.request.contextPath}/layui/layui.js"
	charset="utf-8"></script>
<script type="text/javascript"
	src="${pageContext.request.contextPath}/js/jquery-3.3.1.min.js"></script>
<style type="text/css">
#carousel {
	position: absolute;
	left: 0px;
	top: 0px;
	z-index: -1
}
</style>
<script>
	//注意：导航 依赖 element 模块，否则无法进行功能性操作
	layui.use('element', function() {
		var element = layui.element;
	});
	/* 轮播 */
	layui.use('carousel', function() {
		var carousel = layui.carousel;
		carousel.render({
			elem : '#carousel',
			width : '100%',
			height : '100%',
			anim : 'fade',
			indicator : 'none',
			arrow : 'none'
		});
	});
</script>
</head>
<body style="text-align: center">
	<!--------------------------导航栏---------------------------->
	<ul class="layui-nav layui-bg-cyan">
		<li class="layui-nav-item"><a href="javascript:;">yun+</a></li>
		<li class="layui-nav-item"><a href="javascript:;">首页</a></li>
		<li class="layui-nav-item"><a
			href="${pageContext.request.contextPath}">登陆</a></li>
		<li class="layui-nav-item layui-this"><a href="javascript:;">注册</a></li>
		<li class="layui-nav-item"><a href="javascript:;">更多</a>
			<dl class="layui-nav-child">
				<dd>
					<a href="javascript:;">广告招租</a>
				</dd>
				<dd>
					<a href="javascript:;">广告招租</a>
				</dd>
				<dd>
					<a href="javascript:;">广告招租</a>
				</dd>
			</dl></li>
		<li class="layui-nav-item"><a href="javascript:;">社区</a></li>
		<li class="layui-nav-item"><i
			class="layui-icon layui-icon-cellphone"
			style="color: #FFFFFF; margin-left: 100px;"></i>热线电话：027-88689999</li>
	</ul>
	<!--------------------------轮播图---------------------------->
	<div class="layui-carousel" id="test1">
		<div carousel-item>
			<div>
				<img src="${pageContext.request.contextPath}/img/image1.jpg">
			</div>
			<div>
				<img src="${pageContext.request.contextPath}/img/image3.jpg">
			</div>
			<div>
				<img src="${pageContext.request.contextPath}/img/image4.jpg">
			</div>
			<div>
				<img src="${pageContext.request.contextPath}/img/image6.jpg">
			</div>
			<div>
				<img src="${pageContext.request.contextPath}/img/image7.jpg">
			</div>
		</div>
	</div>

	<!--------------------------登录框---------------------------->
	<div class="layui-row layui-col-space30" style="margin-top: -600px;">
		<!-- 占4格，往右移动4格（等于在中间），背景色灰色 -->
		<div
			class="layui-col-md4 layui-col-md-offset4 layui-bg-gray layui-anim layui-anim-scale">
			<!-- 标题占12格 -->
			<div class="layui-row">
				<div class="layui-col-md12">
					<h1>
						<i class="layui-icon layui-icon-release"
							style="font-size: 40px; color: #2F4056; margin-right: 10px;"></i>yun+
						Quick Register
					</h1>
				</div>
			</div>
			<!-- 两个占12格表单 -->
			<div class="layui-row layui-col-space10">
				<form class="layui-form layui-form-pane">
					<div class="layui-col-md12">
						<div class="layui-form-item">
							<label class="layui-form-label layui-icon layui-icon-username">用户名</label>
							<div class="layui-input-block">
								<input id="loginName" class="layui-input" type="text"
									placeholder="请输入用户名" name="loginName" autocomplete="off"
									lay-verify="username|required">
							</div>
						</div>
					</div>
					<div class="layui-col-md12">
						<div class="layui-form-item">
							<label class="layui-form-label layui-icon layui-icon-password">密&nbsp;码</label>
							<div class="layui-input-block">
								<input id="loginPwd" class="layui-input" type="password"
									placeholder="请输入登陆密码" autocomplete="off" name="loginPwd"
									lay-verify="password|required">
							</div>
						</div>
					</div>
					<div class="layui-col-md12">
						<div class="layui-form-item">
							<label class="layui-form-label">确认密码</label>
							<div class="layui-input-block">
								<input id="repassword" class="layui-input" type="password"
									placeholder="请重新输入登陆密码" autocomplete="off" name="repassword"
									lay-verify="repassword|required">
							</div>
						</div>
					</div>
					<div class="layui-col-md12">
						<div class="layui-form-item layui-col-md9">
							<label class="layui-form-label layui-icon layui-icon-cellphone"
								style="font-size: 14px;">手机号</label>
							<div class="layui-input-block">
								<input id="phone" class="layui-input" type="text"
									placeholder="请输入手机号" autocomplete="off" name="phone"
									lay-verify="required|phone|number">
							</div>
						</div>
						<input id="cellphone" type="button"
							class="layui-btn layui-col-md3 layui-bg-blue" value="发送验证码">
					</div>
					<input id="phoneCode" class="layui-input" type="hidden">
					<div class="layui-col-md12">
						<div class="layui-form-item">
							<label class="layui-form-label layui-icon layui-icon-vercode">验证码</label>
							<div class="layui-input-block">
								<input id="vercode" class="layui-input" type="text"
									name="vercode" placeholder="手机接收6位验证码" autocomplete="off"
									lay-verify="required|vercode">
							</div>
						</div>
					</div>
					<div class="layui-col-md12 ">
						<div class="layui-form-item">
							<div class="layui-col-md3">
								<input id="agree" type="checkbox" title="已同意" lay-filter="agree">
							</div>
							<label class="layui-col-inline" style="margin-top: 8px;">勾选即同意《yun+服务政策》和《yun+隐私政策》</label>
						</div>
					</div>
					<div class="layui-row layui-col-space10">
						<div class="layui-col-md12">
							<input id="register" type="submit"
								class="layui-btn layui-btn-fluid layui-btn-disabled" lay-submit
								lay-filter="formregister" value="注册">
						</div>
					</div>
				</form>
			</div>
		</div>
	</div>
	<!--------------------------登录框---------------------------->
	<div class="layui-container"
		style="background-color: #FFFFFF; margin-top: 235px;">
		<span class="layui-breadcrumb" lay-separator="|"> <a
			href="javascript:;">© yun+ 租房</a> <a href="javascript:;">娱乐</a> <a
			href="javascript:;">八卦</a> <a href="javascript:;">体育</a> <a
			href="javascript:;">搞笑</a> <a href="javascript:;">视频</a> <a
			href="javascript:;">游戏</a> <a href="javascript:;">综艺</a>
		</span>
	</div>
</body>
<script>
	//注意：导航 依赖 element 模块，否则无法进行功能性操作
	layui.use('element', function() {
		var element = layui.element;
	});
	/* 轮播 */
	layui.use('carousel', function() {
		var carousel = layui.carousel;
		carousel.render({
			elem : '#test1',
			width : '100%',
			height : '700px',
			anim : 'fade',
			indicator : 'none',
			arrow : 'none'
		});
	});
	/* 用户名框失去焦点  */
	$("#loginName")
			.blur(
					function() {
						var loginName = $("#loginName").val();
						$
								.ajax({
									data : {
										"loginName" : loginName
									},
									type : "post",
									dataType : 'json',
									url : "${pageContext.request.contextPath}/UserController/checkLoginName",
									success : function(data) {
										if (data.code == 1) {
											layer.tips("该用户已存在", '#loginName',{tips : 1})
											$("#loginName").val("")
											$("#register").addClass(
													'layui-btn-disabled')

										} else {
											if (loginName == "") {
												layer.tips("用户名不能为空",
														'#loginName', {
															tips : 1
														})
											} else {
												layer.tips("用户名可用",
														'#loginName', {
															tips : 1
														})
											}

										}
									}
								})

					})
	/* 确认密码框失去焦点  */
	$("#repassword").blur(function() {
		var pwd = $("#loginPwd").val();
		var repwd = $("#repassword").val();
		if (pwd != repwd) {
			layer.tips("两次密码不一致", '#repassword', {
				tips : 1
			})
			$("#repassword").val("")
		}
	})

	var InterValObj;//timer变量，控制时间
	var count = 60;//间隔函数，1秒执行
	var curCount;//当前剩余秒数
	$("#cellphone").on("click", function() {
		curCount = count; // 设置button效果，开始计时
		$("#cellphone").attr("class","layui-btn layui-col-md3 layui-btn-disabled");//设置按钮为禁用状态
		$("#cellphone").val("请在" + curCount + "后再次获取");//更改按钮文字
		InterValObj = window.setInterval(SetRemainTime, 1000); // 启动计时器timer处理函数，1秒执行一次 // 向后台发送处理数据
		var phone = $("#phone").val();
		$.ajax({
			url : "${pageContext.request.contextPath}/UserController/cellPhone",
			data : {
				"Numbers" : phone
			},
			type : "post",
			dataType : 'json',
			success : function(data) {
				if (data.status==200) {
					$("#phoneCode").val(data.code);
				}else if (data.status==404) {
					alert(data.message)
				}
			}
		})
	})
	/* 验证码失去焦点  */
	$("#vercode").blur(function() {
		var vercode = $("#vercode").val();
		var phoneCode = $("#phoneCode").val();
		if (vercode != phoneCode) {
			layer.tips("两次验证码不一致", '#vercode', {
				tips : 1
			})
			$("#vercode").val("")
		}
	})


	//timer处理函数
	function SetRemainTime() {
		if (curCount == 0) {
			window.clearInterval(InterValObj);// 停止计时器
			$("#cellphone").attr("class","layui-btn layui-col-md3");//移除禁用状态改为可用
			$("#cellphone").val("重新发送验证码");
		} else {
			curCount--;
			$("#cellphone").val("请在" + curCount
					+ "秒后再次获取");
		}
	}
	/* 注册方法 */
	layui.use([ 'layer', 'form' ],function() {
		var layer = layui.layer;//加载layer模块
		var form = layui.form;//加载表单模块
		form.on('submit(formregister)',function(data) {
			var formData = data.field;
			$.ajax({
					data : formData,
					type : "post",
					dataType : 'json',
					url : "${pageContext.request.contextPath}/UserController/addUser",
					success : function(data) {
							if (data.row == 1) {
									window.location.href = "${pageContext.request.contextPath}";
												}
										}
								})
				return false;//必须带上
});

						/* 复选框监听  */
						form.on('checkbox(agree)', function(data) {
							if (data.elem.checked) {
								$("#register")
										.removeClass('layui-btn-disabled')
								$("#register").addClass('layui-btn-normal')
							} else {
								$("#register").addClass('layui-btn-disabled')
							}

						});

						/* 验证与正则  */
						form.verify({
							username : function(value, item) { //value：表单的值、item：表单的DOM对象
								if (!new RegExp(
										"^[a-zA-Z0-9_\u4e00-\u9fa5\\s·]+$")
										.test(value)) {
									return '用户名不能有特殊字符';
								}
								if (/(^\_)|(\__)|(\_+$)/.test(value)) {
									return '用户名首尾不能出现下划线\'_\'';
								}
								if (/^\d+\d+\d$/.test(value)) {
									return '用户名不能全为数字';
								}
							}
							//我们既支持上述函数式的方式，也支持下述数组的形式
							//数组的两个值分别代表：[正则匹配、匹配不符时的提示文字]
							,
							password : [ /^[\S]{6,12}$/, '密码必须6到12位，且不能出现空格' ],
							repassword : function(value, item) {
								var pwd = $("#loginPwd").val();
								if (pwd != value) {
									return '两次输入的密码不一致';
								}
							},
							vercode : [ /^[\S]{6}$/, '请输入正确的六位验证码 ' ]
						});
					});
</script>
</html>
