#### 基础语法： $(selector).action()
		- 美元符号定义 jQuery
		- 选择符（selector）"查询"和"查找" HTML 元素
		- jQuery 的 action() 执行对元素的操作。
		
#### 文档就绪事件：所有 jQuery 函数都位于一个 document ready 函数中。
		$(document).ready(function(){
		 
		   // 开始写 jQuery 代码...
		 
		});
		
		简写：
		$(function(){
		 
		   // 开始写 jQuery 代码...
		 
		});
		
#### jQuery 选择器：
		- 元素选择器：jQuery 元素选择器基于元素名选取元素。
			<script>
			        $(function() {
			            $("button").click(function() {
			                $("p").hide();
			//所有 <p> 元素都隐藏
			            });
			        });
			    </script>
			</head>
			<body>
			    <h2>这是一个标题</h2>
			    <p class="o">这是一个段落。</p>
			    <p>这是第二个段落。</p>
			    <button>点我</button>
			</body>
			
		- #id 选择器 : 通过 HTML 元素的 id 属性选取指定的元素。
			<script>
			        $(function() {
			            $("button").click(function() {
			                $("#o").hide();
			            });
			        });
			//ID为o的元素被隐藏
			    </script>
			</head>
			<body>
			    <h2>这是一个标题</h2>
			    <p id="o">这是一个段落。</p>
			    <p>这是第二个段落。</p>
			    <button>点我</button>
			</body>
			
		- .class选择器：可以通过指定的 class 查找元素。
			<script>
			        $(function() {
			            $("button").click(function() {
			                $(".o").hide();
			            });
			        });
			//类名为o的元素被隐藏。
			    </script>
			</head>
			<body>
			    <h2>这是一个标题</h2>
			    <p class="o">这是一个段落。</p>
			    <p>这是第二个段落。</p>
			    <button>点我</button>
			</body>
			
		- 更多选择器：
			$("*")：选取所有元素。
			$(this)：选取当前 HTML 元素。
			$("p.intro")：选取 class 为 intro 的 <p> 元素。
			$("p:first")：选取第一个 <p> 元素。
			$("ul li:first")：选取第一个 <ul> 元素的第一个 <li> 元素	在线实例。
			$("ul li:first-child")：选取每个 <ul> 元素的第一个 <li> 元素。
			$("[href]")：选取带有 href 属性的元素	在线实例。
			$("a[target='_blank']")：选取所有 target 属性值等于 "_blank" 的 <a> 元素。
			$("a[target!='_blank']")：选取所有 target 属性值不等于 "_blank" 的 <a> 元素。
			$(":button")：选取所有 type="button" 的 <input> 元素 和 <button> 元素。
			$("tr:even")：选取偶数位置的 <tr> 元素。
			$("tr:odd")：选取奇数位置的 <tr> 元素。
			
#### jQuery 事件：页面对不同访问者的响应叫做事件。
		- $(document).ready()：允许我们在文档完全加载完后执行函数。
		- click()：当按钮点击事件被触发时会调用一个函数。
		- dblclick()：当双击元素时，会发生 dblclick 事件。
		- mouseenter()：当鼠标指针穿过元素时，会发生 mouseenter 事件。
		- mouseleave()：当鼠标指针离开元素时，会发生 mouseleave 事件。
		- mousedown()：当鼠标指针移动到元素上方，并按下鼠标按键时，会发生 mousedown 事件。
		- mouseup()：当在元素上松开鼠标按钮时，会发生 mouseup 事件。
		- hover()：用于模拟光标悬停事件。
		- focus()：当元素获得焦点时，发生 focus 事件。
		- blur()：当元素失去焦点时，发生 blur 事件。
		
#### jQuery 效果：
		- 隐藏和显示：
			▪ $(selector).hide(speed,callback)；
			▪ $(selector).show(speed,callback)；
				Ø 可选的 speed 参数规定隐藏/显示的速度，可以取以下值："slow"、"fast" 或毫秒。
				Ø 可选的 callback 参数是隐藏或显示完成后所执行的函数名称。
			<script>
			        $(function() {
			            $("#hide").click(function() {
			                $("p").hide(1000);
			            });
			            $("#show").click(function() {
			                $("p").show(500);
			            });
			        });
			    </script>
			</head>
			<body>
			    <button id="hide">隐藏</button>
			    <button id="show">显示</button>
			    <p>这是个段落，内容比较少。</p>
			    <p>这是另外一个小段落</p>
			</body>
			
			▪ 可以使用 toggle() 方法来切换 hide() 和 show() 方法。
			<script>
			        $(function() {
			            $("button").click(function() {
			                $("p").toggle();
				Ø $(selector).toggle(speed,callback);
					® 可选的 speed 参数规定隐藏/显示的速度，可以取以下值："slow"、"fast" 或毫秒。
					® 可选的 callback 参数是隐藏或显示完成后所执行的函数名称。
			            });
			        });
			    </script>
			</head>
			<body>
			    <button>隐藏/显示</button>
			    <p>这是一个文本段落。</p>
			    <p>这是另外一个文本段落。</p>
			</body>
			
		- 淡入与淡出：
			▪ fadeIn()： 用于淡入已隐藏的元素。$(selector).fadeIn(speed,callback);  可选的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒，可选的 callback 参数是 fading 完成后所执行的函数名称。
				<script>
				        $(document).ready(function() {
				            $("button").click(function() {
				                $("#div1").fadeIn();
				                $("#div2").fadeIn("slow");
				                $("#div3").fadeIn(1000);
				            });
				        });
				</script>
				
			▪ fadeOut()：用于淡出可见元素。$(selector).fadeOut(speed,callback);  可选的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒，可选的 callback 参数是 fading 完成后所执行的函数名称。
				<script>
				        $(document).ready(function() {
				            $("button").click(function() {
				                $("#div1").fadeOut();
				                $("#div2").fadeOut("slow");
				                $("#div3").fadeOut(3000);
				            });
				        });
				</script>
				
			▪ fadeToggle()：可以在 fadeIn() 与 fadeOut() 方法之间进行切换。$(selector).fadeToggle(speed,callback);  可选的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒，可选的 callback 参数是 fading 完成后所执行的函数名称。
				<script>
				        $(document).ready(function() {
				            $("button").click(function() {
				                $("#div1").fadeToggle();
				                $("#div2").fadeToggle("slow");
				                $("#div3").fadeToggle(3000);
				            });
				        });
				</script>
				
			▪ fadeTo()：允许渐变为给定的不透明度（值介于 0 与 1 之间）。$(selector).fadeTo(speed,opacity,callback);  必需的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒。fadeTo() 方法中必需的 opacity 参数将淡入淡出效果设置为给定的不透明度（值介于 0 与 1 之间），可选的 callback 参数是该函数完成后所执行的函数名称。
				    <script>
				        $(document).ready(function() {
				            $("button").click(function() {
				                $("#div1").fadeTo("slow", 0.15);
				                $("#div2").fadeTo("slow", 0.5);
				                $("#div3").fadeTo("slow", 1);
				            });
				        });
				    </script>
				
		- 滑动：
			▪ slideDown()：用于向下滑动元素。$(selector).slideDown(speed,callback);  可选的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒，可选的 callback 参数是滑动完成后所执行的函数名称。
				 <script>
				        $(document).ready(function() {
				            $("#flip").click(function() {
				                $("#panel").slideDown(3000);
				            });
				        });
				</script>
				
			▪ slideUp()：用于向上滑动元素。$(selector).slideUp(speed,callback);  可选的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒，可选的 callback 参数是滑动完成后所执行的函数名称。
				<script>
				        $(document).ready(function() {
				            $("#flip").click(function() {
				                $("#panel").slideUp("slow");
				            });
				        });
				</script>
				
			▪ slideToggle()：可以在 slideDown() 与 slideUp() 方法之间进行切换。$(selector).slideToggle(speed,callback);  可选的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒，可选的 callback 参数是滑动完成后所执行的函数名称。
				    <script>
				        $(document).ready(function() {
				            $("#flip").click(function() {
				                $("#panel").slideToggle("slow");
				            });
				        });
				    </script>
				
		- 动画：
			▪ animate()：用于创建自定义动画。$(selector).animate({params},speed,callback);  必需的 params 参数定义形成动画的 CSS 属性，可选的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒，可选的 callback 参数是动画完成后所执行的函数名称。
				<script>
				        $(document).ready(function() {
				            $("button").click(function() {
				                $("div").animate({
				                    right: '300px'
				                });
				            });
				        });
				</script>
				
			▪ animate() - 操作多个属性：当使用 animate() 时，必须使用 Camel（驼峰） 标记法书写所有的属性名，比如，必须使用 paddingLeft 而不是 padding-left，使用 marginRight 而不是 margin-right，等等。
				<script>
				        $(function() {
				            $("button").click(function() {
				                $("div").animate({
				                    left: '250px',
				                    opacity: '0.25',
				                    height: '150px',
				                    width: '150px'
				                });
				            });
				        });
				</script>
				
			▪ animate() - 使用相对值：可以定义相对值（该值相对于元素的当前值），需要在值的前面加上  +=  或  -= 
				<script>
				        $(document).ready(function() {
				            $("button").click(function() {
				                $("div").animate({
				                    left: '250px',
				                    height: '-=50px',
				                    width: '-=50px'
				                });
				            });
				        });
				</script>
				
			▪ animate() - 使用预定义的值：可以把属性的动画值设置为 "show"、"hide" 或 "toggle"。
				 <script>
				        $(document).ready(function() {
				            $("button").click(function() {
				                $("div").animate({
				                    width: 'toggle'
				                });
				            });
				        });
				</script>
				
			▪ animate() - 使用队列功能：jQuery 提供针对动画的队列功能。
				 <script>
				        $(document).ready(function() {
				            $("button").click(function() {
				                var div = $("div");
				                div.animate({
				                    height: '300px',
				                    opacity: '0.2'
				                }, "slow");
				                div.animate({
				                    width: '300px',
				                    opacity: '0.4'
				                }, "slow");
				                div.animate({
				                    height: '100px',
				                    opacity: '0.6'
				                }, 'slow');
				                div.animate({
				                    width: '100px',
				                    opacity: '1'
				                }, "slow");
				            });
				        });
				</script>
				
		- 停止动画：
			▪ stop() ：用于停止动画或效果，在它们完成之前，stop() 方法适用于所有 jQuery 效果函数，包括滑动、淡入淡出和自定义动画$(selector).stop(stopAll,goToEnd);  可选的 stopAll 参数规定是否应该清除动画队列。默认是 false，即仅停止活动的动画，允许任何排入队列的动画向后执行，可选的 goToEnd 参数规定是否立即完成当前动画。默认是 false。
				<script>
				        $(document).ready(function() {
				            $("#flip").click(function() {
				                $("#panel").slideToggle(3000);
				            });
				            $("#stop").click(function() {
				                $("#panel").stop();
				            });
				        });
				</script>
				
		- Callback 方法：Callback 函数在当前动画 100% 完成之后执行。
			 <script>
			        $(document).ready(function() {
			            $("#flip").click(function() {
			                $("#panel").hide("slow",function(){
			                    alert("动作完成！");
			                });
			            });
			        });
			</script>
			
		- jQuery 方法链接：允许我们在相同的元素上运行多条 jQuery 命令，一条接着另一条。
			<script>
			        $(document).ready(function() {
			            $("button").click(function() {
			                $("#p1").css("color", "red").slideUp(2000).slideDown(2000);
			            });
			        });
			</script>
		
#### jQuery DOM 操作：
		- 获得内容：
			▪ text() - 设置或返回所选元素的文本内容：
			▪ html() - 设置或返回所选元素的内容（包括 HTML 标记）：
				<script>
				$(document).ready(function(){
				  $("#btn1").click(function(){
				    alert("Text: " + $("#test").text());
				  });
				  $("#btn2").click(function(){
				    alert("HTML: " + $("#test").html());
				  });
				});
				</script>
				
			▪ val() - 设置或返回表单字段的值：
				<script>
				        $(document).ready(function() {
				            $("button").click(function() {
				                alert("值为：" + $("#test").val());
				            });
				        });
				</script>
				
		- 获取属性：
			▪ attr() - 方法用于获取属性值。
				  <script>
				        $(document).ready(function() {
				            $("button").click(function() {
				                alert("获取属性：" + $("#runoob").attr("href"));
				            });
				        });
				</script>
				
		- 设置内容：
			▪ text() - 设置或返回所选元素的文本内容：
			▪ html() - 设置或返回所选元素的内容（包括 HTML 标记）：
				<script>
				        $(document).ready(function() {
				            $("#btn1").click(function() {
				                $("#test1").text(function(i, origText) {
				                    return "旧文本：" + origText + "新文本：牛逼！(index:" + i + ")";
				                });
				            });
				            $("#btn2").click(function() {
				                $("#test2").html(function(i, origText) {
				                    return "旧文本：" + origText + "新文本：牛逼！(index:" + i + ")";
				                });
				            });
				        });
				</script>
				
			▪ val() - 设置或返回表单字段的值：
			
		- 设置属性：
			▪ attr() - 方法用于设置/改变属性值。
				<script>
				        $(document).ready(function() {
				            $("button").click(function() {
				                $("#runoob").attr("href", "http://www.baidu.com");
				            });
				        });
				</script>
				
			▪ 同时修改多个属性：
				 <script>
				        $(document).ready(function() {
				            $("button").click(function() {
				                $("#runoob").attr({
				                    "href": "http://www.baidu.com",
				                    "title": "noob"
				                });
				                title = $("#runoob").attr('title');
				                $("#runoob").html(title);
				            });
				        });
				</script>
				
#### jQuery - 添加元素：
		- append() - 在被选元素的结尾插入内容：
			<script>
			        $(document).ready(function() {
			            $("#btn1").click(function() {
			                $("p").append("<b>noob</b>.");
			            });
			            $("#btn2").click(function() {
			                $("ol").append("<li>pfect</li>");
			            });
			        });
			</script>
			
		- prepend() - 在被选元素的开头插入内容：
			<script>
			        $(document).ready(function() {
			            $("#btn1").click(function() {
			                $("p").prepend("<b>noob</b>.");
			            });
			            $("#btn2").click(function() {
			                $("ol").prepend("<li>pfect</li>");
			            });
			        });
			</script>
			
			 <script>
			        function appendText() {
			            var txt1 = "<p>noob</p>";//使用html标签创建
			            var txt2 = $("<p></p>").text("noob");//使用Jquery创建
			            var txt3 = document.createElement("p")；//使用DOM创建
			            txt3.innerHTML = "noob";
			            $("body").append(txt1, txt2, txt3);//追加新元素
			        }
			</script>
			
		- after() - 在被选元素之后插入内容：
		- before() - 在被选元素之前插入内容：
			<script>
			        $(document).ready(function() {
			            $("#btn1").click(function() {
			                $("img").before("noob");
			            });
			            $("#btn2").click(function() {
			                $("img").after("noob");
			            });
			        });
			</script>
			
			<script>
			        function afterText() {
			            var txt1 = "<b>I </b>";//使用HTML标签创建
			            var txt2 = $("<i></i>").text("love ");//使用Jquery创建
			            var txt3 = document.createElement("big")；//使用DOM创建
			            txt3.innerHTML = " Jquery";
			            $("img").after(txt1, txt2, txt3);//追加元素
			        }
			</script>
			
#### jQuery - 删除元素：
		- remove() - 删除被选元素（及其子元素）：
			 <script>
			        $(document).ready(function() {
			            $("button").click(function() {
			                $("#demo").remove();
			            });
			        });
			</script>
			
		- empty() - 从被选元素中删除子元素：
			<script>
			        $(document).ready(function() {
			            $("button").click(function() {
			                $("#div1").empty();
			            });
			        });
			</script>
			
			对被删元素进行过滤：
			<script>
			        $(document).ready(function() {
			            $("button").click(function() {
			                $("p").remove(".italic");//删除class="italic"的元素
			            });
			        });
			</script>
			
#### jQuery - 获取并设置 CSS 类：
		- addClass() - 向被选元素添加一个或多个类：
			    <script>
			        $(document).ready(function() {
			            $("button").click(function() {
			                $("h1,h2,p").addClass("blue");
			                $("div").addClass("important");
			            });
			        });
			    </script>
			
			可以在 addClass() 方法中规定多个类：
			    <script>
			        $(document).ready(function() {
			            $("button").click(function() {
			                $("#div1").addClass("important blue");
			            });
			        });
			    </script>
			
		- removeClass() - 从被选元素删除一个或多个类：
			    <script>
			        $(document).ready(function() {
			            $("button").click(function() {
			                $("h1,h2,p").removeClass("blue");
			            });
			        });
			    </script>
			
		- toggleClass() - 对被选元素进行添加/删除类的切换操作：
			   <script>
			        $(document).ready(function() {
			            $("button").click(function() {
			                $("h1,h2,p").toggleClass("blue");
			            });
			        });
			    </script>
			
		- css() - 设置或返回样式属性：
		
			返回CSS属性
			 <script>
			        $(document).ready(function() {
			            $("button").click(function() {
			                alert("背景颜色：" + $("p").css("background-color"));
			            });
			        });
			    </script>
			
			设置CSS属性
			 <script>
			        $(document).ready(function() {
			            $("button").click(function() {
			                "背景颜色：" + $("p").css("background-color", "yellow");
			            });
			        });
			</script>
			
			同时设置多个属性
			 <script>
			        $(document).ready(function() {
			            $("button").click(function() {
			                $("p").css({
			                    "background-color": "yellow",
			                    "font-size": "200%"
			                });
			            });
			        });
			</script>
			
#### jQuery 尺寸：
		- width()：
		- height()：
			 <script>
			        $(document).ready(function() {
			            $("button").click(function() {
			                var txt = "";
			                txt += "div的宽度是：" + $("#div1").width() + "</br>";
			                txt += "div的高度是：" + $("#div1").height();
			                $("#div1").html(txt);
			            });
			        });
			</script>
			
		- innerWidth()：
		- innerHeight()：
		- outerWidth()：
		- outerHeight()：
			   <script>
			        $(document).ready(function() {
			            $("button").click(function() {
			                var txt = "";
			                txt += "div的宽度是：" + $("#div1").width() + "</br>";
			                txt += "div的高度是：" + $("#div1").height() + "</br>";
			                txt += "div的宽度，包含内间距：" + $("#div1").innerWidth() + "</br>";
			                txt += "div的高度，包含内间距：" + $("#div1").innerHeight() + "</br>";
			                txt += "div的高度，包含外间距：" + $("#div1").outerWidth() + "</br>";
			                txt += "div的高度，包含外间距：" + $("#div1").outerHeight() + "</br>";
			                $("#div1").html(txt);
			            });
			        });
			    </script>
			
#### jQuery 遍历：用于根据其相对于其他元素的关系来"查找"（或选取）HTML 元素。
		- 向上遍历 DOM 树：
			▪ parent()：返回被选元素的直接父元素，该方法只会向上一级对 DOM 树进行遍历。
				<script>
				        $(document).ready(function() {
				            $("span").parent().css({
				                "color": "red",
				                "border": "2px solid red"
				            });
				        });
				</script>
				
			▪ parents()：返回被选元素的所有祖先元素，它一路向上直到文档的根元素 (<html>)。
				<script>
				        $(document).ready(function() {
				            $("span").parents().css({
				                "color": "red",
				                "border": "2px solid red"
				            });
				        });
				</script>
				
			▪ parentsUntil()：返回介于两个给定元素之间的所有祖先元素。
				  <script>
				        $(document).ready(function() {
				            $("span").parentsUntil("div").css({
				                "color": "red",
				                "border": "1px solid red"
				            });
				        });
				</script>
				
		- 向下遍历 DOM 树：
			▪ children()：返回被选元素的所有直接子元素。
				<script>
				        $(function() {
				            $("div").children().css({
				                "color": "red",
				                "border": "2px solid red"
				            });
				        });
				</script>
				
			▪ find()：返回被选元素的后代元素，一路向下直到最后一个后代。
				 <script>
				        $(document).ready(function() {
				            $("div").find("*").css({
				                "color": "red",
				                "border": "2px solid red"
				            });
				        });
				</script>
				
		- 水平遍历 DOM 树：
			▪ siblings()：返回被选元素的所有同胞元素。
				<script>
				        $(document).ready(function() {
				            $("h2").siblings().css({
				                "color": "red",
				                "border": "2px solid red"
				            });
				        });
				</script>
				
			▪ next()：返回被选元素的下一个同胞元素。
				<script>
				        $(document).ready(function() {
				            $("h2").next().css({
				                "color": "red",
				                "border": "2px solid red"
				            });
				        });
				</script>
				
			▪ nextAll()：返回被选元素的所有跟随的同胞元素。
				 <script>
				        $(document).ready(function() {
				            $("h2").nextAll().css({
				                "color": "red",
				                "border": "2px solid red"
				            });
				        });
				</script>
			
			▪ nextUntil()：返回介于两个给定参数之间的所有跟随的同胞元素。
				 <script>
				        $(document).ready(function() {
				            $("p").nextUntil("p").css({
				                "color": "red",
				                "border": "2px solid red"
				            });
				        });
				</script>
				
			▪ prev()：返回被选元素的前一个同胞元素。
			▪ prevAll()：返回被选元素之前的所有同胞元素。
			▪ prevUntil()：返回介于两个给定参数之间的所有跟随的同胞元素（向前）。
			
		- jQuery 遍历- 过滤：
			▪ first()：返回被选元素的首个元素。
				    <script>
				        $(document).ready(function() {
				            $("div p").first().css({"background-color": "red"});//首个div的首个p元素
				        });
				    </script>
				
			▪ last() ：返回被选元素的最后一个元素。
				 <script>
				        $(document).ready(function() {
				            $("div p").last().css({"background-color": "red"});//最后一个div的最后一个p元素
				        });
				</script>
				
			▪ eq()：返回被选元素中带有指定索引号的元素。
				    <script>
				        $(document).ready(function() {
				            $("p").eq(2).css("background-color", "yellow");
				        });
				    </script>
				
			▪ filter()：允许您规定一个标准。不匹配这个标准的元素会被从集合中删除，匹配的元素会被返回。
				    <script>
				        $(document).ready(function() {
				            $("p").filter(".c").css("background-color","red")
				        });
				    </script>
				
			▪ not() ：返回不匹配标准的所有元素。
				    <script>
				        $(document).ready(function() {
				            $("p").not(".c").css("background-color", "red");
				        });
				    </script>
				
#### jQuery - AJAX ：
		- jQuery load() ：$(selector).load(URL,data,callback); 从服务器加载数据，并把返回的数据放入被选元素中。
			▪ URL 参数规定您希望加载的 URL；
			▪ 可选的 data 参数规定与请求一同发送的查询字符串键/值对集合；
			▪ 可选的 callback 规定当 load() 方法完成后所要允许的回调函数；
				Ø responseTxt - 包含调用成功时的结果内容；
				Ø statusTXT - 包含调用的状态；
				Ø xhr - 包含 XMLHttpRequest 对象；
					 <script>
					        $(document).ready(function() {
					            $("button").click(function() {
					                $("div1").load("/try/ajax/demo_test.txt", function(responseTxt, stasusTxt, xhr) {
					                    if (stasusTxt == "success")
					                        alert("外部内容加载成功！");
					                    if (stasusTxt == "error")
					                        alert("Error:" + xhr.status + ":" + xhr.statusText);
					                });
					            });
					        });
					    </script>
					
		- jQuery $.get() ：$.get(URL,callback);  通过 HTTP GET 请求从服务器上请求数据。
			<script>
			        $(document).ready(function() {
			            $("button").click(function() {
			                $.get("/try/ajax/demo_test.php"", function(data, status) {
			                    alert("数据：" + data++"\n状态：" + status);
			                });
			            });
			        });
			</script>
			
		- jQuery $.post() ：$.post(URL,data,callback);  通过 HTTP POST 请求向服务器提交数据。
			    <script>
			        $(document).ready(function() {
			            $("button").click(function() {
			                $.post("/try/ajax/demo_test_post.php", {
			                        name: "菜鸟教程",
			                        url: "http://www.runoob.com"
			                    },
			                    function(data, status) {
			                        alert("数据: \n" + data + "\n状态: " + status);
			                    });
			            });
			        });
			    </script>
			
#### jQuery - noConflict() 方法：会释放对 $ 标识符的控制，解决与其他框架的冲突。
		- 创建自己的简写：
			    <script>
			        var nb = $.noConflict();
			        nb(document).ready(function() {
			            nb("button").click(function() {
			                nb("p").text("noob");
			            });
			        });
			    </script>
			
		-  $ 符号作为变量传递给 ready 方法：这样就可以在函数内使用 $ 符号了 - 而在函数外，依旧不得不使用 "jQuery"：
			 <script>
			        $.noConflict();
			        jQuery(document).ready(function($) {
			            $("button").click(function() {
			                $("p").text("noob");
			            });
			        });
			</script>
