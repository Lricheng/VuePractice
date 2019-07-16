##数组得some方法 如果里面的表达式是正确就会继续执行
###数组得splice方法，如果拿到了id的索引，直接调用数组的splice方法，就可以根据索引和想要删减得长度遍历删除数组中得长度

<hr>代码如下
some方法 如果里面的表达式是正确就会继续执行
			
			this.list.some((item,i)=>{//es6写法
			 	if (item.id==id) {
				this.list.splice(i,1)
				在数组的some方法中，如果retrun true，就会立即终止这个数组的后续循环
				return true;
					}
				 })

<hr>
##数组得findIndex方法。可以遍历查找索引，内部需要传递一个回调函数，返回布尔值，但后在根据此布尔值所对应得item查到到他得索引，同时在与数组得splice方法一起使用得话就可以实现点击特定删除事件
<hr> 代码如下

		var index= this.list.findIndex(item=>{
							if (item.id==id) {
								return true
							}
						})
						console.log(index)	
						this.list.splice(index,1)			
					},

<hr>


##数组的forEach()方法，增强行遍历，里面可以传递一个回调函数，
###字符串的indexOf(arg)方法,如果匹配到了得话就会返回其第一个字的索引值，找不到的话就会返回-1，所以可以根据indexOf()返回是否是-1来确定是否有包含

<hr>代码如下


						var newList=[]
						this.list.forEach(item=>{
							if (item.name.indexOf(keywords) !=-1) {
								//如果找不到就等于-1
						return newList
						v		newList.push(item)
							}
						})
						return newList


##数组的filter()方法，可以传递回调函数，遍历每个元素，回调函数返回true的item就会被过滤掉，遍历完后返回一个新的数组

<hr> 代码如下

					var newList= this.list.filter(item=>{
							// if (item.name.indexOf(keywords)=-1)方法1

							//方法二 includes（es6中提供得）
							//如果字符串包含得话就返回true
							if (item.name.includes(keywords)) {
								return item;
							}
						})




##字符串的replace(arg1，arg2)方法，第一个参数可以定义一个字符串/正则表达式，同时存在正则表达式修饰符第二个参数是要替代的字符串
###正则表达式的修饰符
	修饰符 可以在全局搜索中不区分大小写:

	修饰符	描述
	i	执行对大小写不敏感的匹配。
	g	执行全局匹配（查找所有匹配而非在找到第一个匹配后停止）。
	m	执行多行匹配。

<hr>代码如下


		Vue.filter('dcFilter',function(data,arg){
			//字符串的repalce方法，第一个参数，除了可以写一个字符串之外，还能定义一个正则
			return data.replace(/单纯/g,arg)
		})




##字符串的padStart(arg1,arg2) es6的填充方法 参数一代表占几位，参数而代表空的要替代成生命字符

<hr> 代码如下

	var ss=dt.getSeconds().toString().padStart(2,'0')
	如果返回的时间的秒数是1的话ss就是01
