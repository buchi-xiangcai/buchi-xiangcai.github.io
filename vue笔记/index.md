# vue基础


#    push() pop() shift() splice() sort() reverse() filter()

1. push() 方法可向数组的末尾添加一个或多个元素，并返回新的长度。

```
new Vue({
   		 data:{
   			arr:  ['苹果','香蕉','橙子']
   		  },
	     methods:{
		    	addData(){
		    		this.arr.push("石榴");
		    	}
	    	}
	})
console.log(arr) 苹果，香蕉，橙子，石榴
```

2. pop() 方法用于删除最后一位元素并返回数组的最后一个元素。

```
 new Vue({
	 	 data:{
	   		arr:  ['苹果','香蕉','橙子']
	     },
	      methods:{
		    	moveData(){
		    		this.arr.pop();
		    	}
	    	}
	})
console.log(arr) 苹果，香蕉
```

3. shift() 方法用于把数组的第一个元素从其中删除，并返回第一个元素的值。

```
 new Vue({
	      data:{
	       		arr:  ['苹果','香蕉','橙子']
	         },
          methods:{
    	    	moveData(){
    	    		this.arr.shift();
    	    	}
        	}
	})
console.log(arr) 香蕉，橙子
```

4. unshift() 方法可向数组的开头添加一个或更多元素，并返回新的长度.

```
 new Vue({
	      data:{
	       		arr:  ['苹果','香蕉','橙子']
	         },
          methods:{
    	    	addData(){
    	    		this.arr.unshift("石榴","枇杷");
    	    	}
        	}
	})  
石榴,枇杷,苹果，香蕉，橙子
```

5. splice() 方法向/从数组中添加/删除项目，然后返回被删除的项目。

   splice(　index,　len,　[item]) 用来删除/替换/添加数组内某一个或者几个值（该方法会改变原始数组）。

   参数：index：数组开始下标

   len：替换/删除的长度

   item：替换的值，删除操作的话item为空

   删除：

   //删除起始下标为1，长度为1的一个值（len设置1，如果为0，则数组不变）

```
例:splice(1);保留前一个元素之后的全部删除，splice(2);保留前两个元素之后的全部删除

let arr = ['a', 'b', 'c', 'd']
arr.splice(2)
console.log(arr) //["a", "b"]
```

```
例:splice(2, 1) 从索引位置(index:2)删除，删除一个元素

let arr = ['a', 'b', 'c', 'd']
arr.splice(2, 1)
console.log(arr) // ["a", "b", "d"]
```

```
例:splice(1,2,‘a’,‘b’) 从索引位置(index:1)删除，删除2个元素，并添加2个新元素来替代被删除的元素

let arr = ['a', 'b', 'c', 'd']
arr.splice(1, 2, '1', '2')
console.log(arr) // ["a", "1", "2", "d"]
```

```
 删除
 new Vue({
		      data:{
		       		arr:  ['a','b','c','d']
		         },
	          methods:{
	    	    	moveData(){
	    	    		this.arr.splice(1,1);
	    	    	}
	        	}
    	})  
    	
【‘a’,‘c’,‘d’】
```

```
 替换
 new Vue({
		      data:{
		       		arr:  ['a','b','c','d']
		         },
	          methods:{
	    	    	replaceData(){
	    	    		this.arr.splice(1,1,'ttt');
	    	    	}
	        	}
    	})  
[‘a’,‘ttt’,‘c’,‘d’]
```

```
添加
new Vue({
		      data:{
		       		arr:  ['a','b','c','d']
		         },
	          methods:{
	    	    	addData(){
	    	    		this.arr.splice(1,0,'ttt');
	    	    	}
	        	}
    	})   
[‘a’,‘ttt’,‘b’,‘c’,‘d’]
```

```
例:splice(1,0,‘a’)从索引位置(index:1)添加，添加两个元素

let arr = ['a', 'b', 'c', 'd']
arr.splice(1, 0, '1', '2')
console.log(arr) // ["a", "1", "2", "b", "c", "d"]
```

6. sort() 方法用于对数组的元素进行排序。

```
new Vue({
    		      data:{
    		       		arr: [
		                    {"id":0,"title":"11111","cont":"99999"},
		                    {"id":1,"title":"22222","cont":"22222"},
		                    {"id":2,"title":"33333","cont":"33333"},
		                ]
		         },
	          methods:{
    	    	    	sortData(){
							this.list.sort((a,b)=>a.cont-b.cont);		
					}
	        	}
    	})  

```

<img src="https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-02-24%2015.24.07.png" alt="截屏2023-02-24 15.24.07" style="zoom:50%;" />

```
大小排序

function sortNumber (a, b) {
  return a - b
}
let arr = [10,5,40,25,1000,1]
arr.sort(sortNumber)
console.log(arr) // [1, 5, 10, 25, 40, 1000]
```

7. reverse() 方法用于颠倒数组中元素的顺序。

```
new Vue({
    		      data:{
    		       		arr: [
		                    {"id":0,"title":"11111","cont":"99999"},
		                    {"id":1,"title":"22222","cont":"22222"},
		                    {"id":2,"title":"33333","cont":"33333"},
		                    {"id":3,"title":"44444","cont":"44444"},
		                    {"id":4,"title":"55555","cont":"55555"},
		                    {"id":5,"title":"66666","cont":"66666"},
		                    {"id":6,"title":"77777","cont":"77777"},
		                    {"id":7,"title":"77777","cont":"88888"}
		         
		                ]
		         },
	          methods:{
    	    	    	reverserData(){
							this.list.reverse();
						}
	        	}
    	})  

```

![截屏2023-02-24 15.24.43](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-02-24%2015.24.43.png)

替换数组
filter() 方法创建一个新的数组，新数组中的元素是通过检查指定数组中符合条件的所有元素。

```
 <el-input placeholder="输入关键字进行过滤" v-model="filterText">
 <el-tree
          :data="treeData"
          :props="defaultProps"
          default-expand-all
          ref="tree"
          @node-click="handleNodeClick"
          :filter-node-method="filterNode"
          class="text_2"
        >
</el-tree>
filterText: "",
  
 watch: {
    filterText(val) {
      this.$refs.tree.filter(val);
    },
  },
```

concat() 方法用于连接两个或多个数组。

split() 方法用于把一个字符串分割成字符串数组。

```
 <div>{{ tips }} 反转的结果是：{{ tips.split('').reverse().join('') }}</div>
 data: {
        tips: '请输入用户名',
      }
      
      //名户用入输请
```

#  v-html v-text

```
<body>
    <div id="div">
	    <!--示例：使用3种方式设置span标签体的内容-->
        <div>方式1：<span>{{msg}}</span></div>
        <div>方式2：<span v-text="msg"></span></div>
        <div>方式3：<span v-html="msg"></span></div>
    </div>
</body>
<script src="js/vue.js"></script>
<script>
    //目标：给视图标签体绑定数据
    //方式1：{{变量名}} 插入值表达式，标签体绑定文本字符串，类似于innerText的功能
    //方式2：v-text="变量名"，与{{变量名}}功能一样
    //方式3：v-html="变量名"，标签体绑定html代码字符串，类似于innerHTML的功能
    //       v-html 或 v-text 都是设置在视图标签的属性位置
    new Vue({
        el:"#div",
        data:{
            msg:"<h1>Hello Vue</h1>"
        }
    });
</script>
```

```
<body>
  <!-- 希望 Vue 能够控制下面的这个 div，帮我们在把数据填充到 div 内部 -->
  <div id="app">
    <p v-text="username"></p>
    <p v-text="gender">性别：</p>
    <hr>

    <p>姓名：{{ username }}</p>
    <p>性别：{{ gender }}</p>
    <hr>

    <div v-text="info"></div>
    <div>{{ info }}</div>
    <div v-html="info"></div>
  </div>

  <!-- 1. 导入 Vue 的库文件，在 window 全局就有了 Vue 这个构造函数 -->
  <script src="./lib/vue-2.6.12.js"></script>
  <!-- 2. 创建 Vue 的实例对象 -->
  <script>
    // 创建 Vue 的实例对象
    const vm = new Vue({
      // el 属性是固定的写法，表示当前 vm 实例要控制页面上的哪个区域，接收的值是一个选择器
      el: '#app',
      // data 对象就是要渲染到页面上的数据
      data: {
        username: 'zhangsan',
        gender: '女',
        info: '<h4 style="color: red; font-weight: bold;">欢迎大家来学习 vue.js</h4>'
      }
    })
  </script>
</body>
</html>
```

![截屏2023-02-24 14.53.46](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-02-24%2014.53.46.png)





https://blog.csdn.net/weixin_30516243/article/details/102324037

#   属性绑定组件 v-bind :

```
<body>
    <div id="div">
        <!--
            注意：插件表达式不能写在属性中，。例如： <标签 属性名="{{变量名}}"> 
			示例1：使用插入值表达式设置a标签的href属性绑定模型数据url，测试插入值表达式在属性值中是否有效
        -->
        <a href="{{url}}">百度一下</a>

        <br>
        <!--
            示例2：使用完整模式（<标签 v-bind:属性名="变量名">）给href属性绑定模型数据url
        -->
        <a v-bind:href="url">百度一下</a>
        <br>
        <!--
            示例3：使用简化模式（<标签 :属性名="变量名">）给href属性绑定模型数据url
        -->
        <a :href="url">百度一下</a>
        <br>
        <!--
            示例4：使用简化模式给class属性绑定模型数据cls
        -->
        <div :class="cls">我是div</div>
    </div>
</body>
<script src="js/vue.js"></script>
<script>
    /*
    * 目标：使用vue中指令v-bind给标签属性绑定数据
    * 语法1：完整模式
    *       <标签 v-bind:属性名="变量名">
    * 语法2：简化模式
    *       <标签 :属性名="变量名">   //v-bind可以省略
    * 注意： <标签 属性名="{{变量名}}"> 这是不可以的，插入值表达式{{变量名}} 只能放在标签体内
    * */
    new Vue({
        el:"#div",
        data:{
            url:"https://www.baidu.com",
            cls:"my"
        }
    });
</script>

```

```
2、v-bind动态绑定class（对象）

<div id="app">
      <!--第一个class没有使用动态绑定，则不能直接删除，两个class会合并处理-->
    <h2 class="NotChange" :class="{active:  isActive,line: isLine}">{{message}}</h2>
    <button @click="changeColor">点击变色</button>
</div>

 data: {
        message: 'hello World!',
        isActive: true,
        isLine: true
      },
      methods: {
        changeColor:  function(){
          this.isActive = !this.isActive;
        }
      }      
 <style>
    .active{
      color: red;
    }
  </style>
```

```
3、v-bind动态绑定class（数组）

使用[类名A，类名B]传入多个类名。
使用[‘字符串A’，‘字符串B’]传入多个字符串。
在methods内使用getClasses()返回上述两种。

 <div id="app">
    <h2 class="NotChange" :class="['active','line']">{{message}}</h2>
    <h2 class="NotChange" :class="[isActive,isLine]">{{message}}</h2>
    <h2 class="NotChange" :class="getClasses()">{{message}}</h2>
    <button @click="changeColor">点击变色</button>
  </div>

  <script>
    const app = new Vue({
      el: '#app',
      data: {
        message: 'hello World!',
        isActive: 'active',
        isLine: 'line'
      },
      methods: {
        changeColor:  function(){
          this.isActive = !this.isActive;
        },getClasses: function(){
          return [this.isActive,this.isLine];
        }
      }
    });
  </script>
```

```
v-bind动态绑定style（对象）
使用方式为{key(属性名),value(值)}
key可以使用驼峰命名法(font-size==>fontSize)，不使用则需要加上单引号，否则 - 会转义。
可以将动态style抽离，使用一个方法返回。

   <div id="app">
      <!-- <h2 :style="{fontSize:finalSize,color:finalColor}">{{message}}</h2> -->
      <h2 :style="{fontSize:finalSize + 'px',color:finalColor}">{{message}}</h2>
      <h2 :style="{'font-size':finalSize + 'px',color:finalColor}">{{message}}</h2>
      <h2 :style="getStyle()">{{message}}</h2>
    </div>
  
    <script>
      let vm = new Vue({
        el: '#app',
        data: {
          message:  '你好世界！',
          // finalSize:'50px',
          finalSize:50,
          finalColor:'yellow',
        },
        methods: {
          getStyle:function(){
            return {'font-size':this.finalSize + 'px',color:this.finalColor};
          }
        }
      });
    </script>

```

![截屏2023-02-27 10.53.41](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-02-27%2010.53.41.png)

```
5、v-bind动态绑定style（数组）
多个对象的集合

    <div id="app">
      <h2 :style="[style1,style2]">{{message}}</h2>
    </div>
  
    <script>
      let vm = new Vue({
        el: '#app',
        data: {
          message:  '你好',
          style1:{fontSize:'40px'},
          style2:{backgroundColor:'green'}
        },
        methods: {}
      });
    </script>
```

![截屏2023-02-27 10.54.21](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-02-27%2010.54.21.png)

#       V-if 条件渲染 v-show

```
<body>
    <div id="div">
        <!--
		示例1：使用v-if控制div标签是否显示
		    判断num的值，对3取余
            余数为0显示div1
            余数为1显示div2
            余数为2显示div3 -->
        <div v-if="num%3==0">div1</div>
        <div v-else-if="num%3==1">div2</div>
        <div v-else>div3</div>

        <!--
        示例2：使用v-show控制div显示与隐藏
        -->
        <div v-show="flag">div4</div>

    </div>
</body>
<script src="js/vue.js"></script>
<script>
    /*
    * 目标：讲解if条件表达式
    * if语法：
    *   <标签名 v-if="条件">标签体</标签名>  条件成立标签存在，否则整个标签会被删除
    *   <标签名 v-else-if="条件">标签体</标签名>  条件成立标签存在，否则整个标签会被删除
    *   <标签名 v-else="条件">标签体</标签名>  上面的条件都不成立就会这个成立，这个标签就会存在，否则整个标签会被删除
	* show语法：      
	*	<标签名 v-show="true">标签体</标签名>  设置标签显示
    *    <标签名 v-show="false">标签体</标签名> 设置标签不显示
	*	
    * v-if与v-show区别：
	*	相同点：都是控制元素是否显示
	*	不同点：底层原理不一样
	*		v-if 如果条件为false，页面中根本没有这个元素
	*		v-show如果条件为false，页面中有这个元素只不过它的display属性值为none
    * */
    new Vue({
        el:"#div",
        data:{
            num:1,
           flag:true
        }
    });
</script>
```

```
 <div v-if="type === 'A'">优秀</div>
    <div v-else-if="type === 'B'">良好</div>
    <div v-else-if="type === 'C'">一般</div>
    <div v-else>差</div>
data: {
        type: 'A'
      }
```



#    v-for 列表渲染

```
<div id="div">
    <ul>
         <!--
          v-for：列表渲染，遍历容器的元素或者对象的属性。
          【环展现数据方式1：遍历数组】
          语法：<标签名 v-for="element in 数组">{{element}}</标签名>
               element含义：遍历的数组中每个元素对象
          含义：控制当前标签进行循环展现数据

          示例：遍历的数组：names:["张三","李四","王五"]，输出打印格式：姓名：xxx
         -->
        <li v-for="name in names">
            元素:{{name}}
        </li>
		
		<hr>

        <!--
        【环展现数据方式2：遍历普通对象的属性值】
          语法：<标签名 v-for="element in 对象">{{element}}</标签名>
          	<标签名 v-for="(value,key,index) in 对象">{{element}}</标签名>
               element含义：遍历对象中每个属性的对应值
          示例：遍历的对象：student:{name:"张三", age:23},输出打印格式：属性值：张三等
        -->
        <li v-for="(value,key,index) in student">
            {{key}}:{{value}}:{{index}}
        </li>
		<hr>

        <!--
         【环展现数据方式3：遍历数组带有循环索引】
         语法：<标签名 v-for="(element,i) in 数组">{{element}}</标签名>
              element含义：遍历的数组中每个元素对象
              i含义：循环的索引
         示例：遍历的数组：names:["张三","李四","王五"]，输出打印格式：姓名0：张三等
        -->
        <li v-for="(name,i) in names">
            元素{{i}}:{{name}}
        </li>
		 <hr>

        <!--
        【环展现数据方式4：使用slice遍历数组部分元素循环】
        语法：<标签名 v-for="element in 数组.slice(索引开始值,索引结束值)">{{element}}</标签名>
             element含义：遍历的数组中每个元素对象
        遍历的数组：names:["张三","李四","王五"]
        示例：遍历数组从第0个位置开始，到索引结束值（不包含索引结束值）
       -->
        <li v-for="name in names.slice(0,2)">
            元素:{{name}}
        </li>
	    <hr>


        <!--
       【环展现数据方式5：使用if遍历数组部分元素循环】
       语法：<标签名 v-for="(element,i) in 数组" v-if="控制i的值表达式">{{element}}</标签名>
       遍历的数组：names:["张三","李四","王五"]
       示例：遍历数组前2个元素
      -->
        <li v-for="(name,i) in names" v-if="i<2">
            元素{{i}}:{{name}}
        </li>
	   <hr>

        <!--
         【环展现数据方式6：控制次数循环】
       语法：<标签名 v-for="num in count">{{num}}</标签名>
       示例：输出5遍hello world
      -->
	  <span v-for="num in 5">
          hello
      </span>
	  <hr>
    </ul>
</div>
</body>
<script src="js/vue.js"></script>
<script>
    new Vue({
        el:"#div",
        data:{
            names:["张三","李四","王五"],
            student:{
                name:"张三",
                age:23
            }
        }
    });
</script>
```

#   v-on 事件绑定

```
<body>
    <div id="div">
        <div>{{name}}</div>
		<!--老方式绑定事件【了解】-->
        <button onclick="demo()">单击_改变div的内容</button>
        <!--
            v-on：为 HTML 标签绑定事件
            完整语法：<标签名 v-on:事件名="vue中methods里面的函数名()"></标签>
            简写语法：<标签名 @事件名="vue中methods里面的函数名()"></标签>
        -->
        <button v-on:click="change">单击_改变div的内容</button>
        <button v-on:dblclick="change()">双击_改变div的内容</button>

        <button @click="change">简写单击_改变div的内容</button>
    </div>
</body>
<script src="js/vue.js"></script>
<script>
    new Vue({
        el:"#div",
        data:{
            name:"halulu"
        },
        methods:{
            change(){
                this.name = "halulu加强版"
            }
        }
    });
	
	function demo(){
        alert("demo");
        //在vue的外部调用模型数据：vm.name
    }
</script>

```

#    v-model表单form绑定

```
<body>
    <div id="div">
        <form autocomplete="off">
			<!--
                单向绑定: model数据改变了  ==》 视图的数据也会变
                         视图的数据改变了，Model不会被影响
            -->
            姓名_单向绑定：<input type="text" name="username" :value="username">
            <br>
			<!--
                双向绑定：model数据改变了 《==》 视图的数据也会变
                        视图的数据改变了，Model会被影响
            -->
            姓名_双向绑定：<input type="text" name="username" v-model="username">
			<br>

        </form>
		
        <hr>
		<h3>{{username}}</h3>
    </div>
</body>
<script src="js/vue.js"></script>
<script>
    /*
    * 目标：使用v-model实现MVVM双向数据绑定
    *      注意：不用v-model就是单向，使用就是双向
    * */
    new Vue({
        el:"#div",
        data:{
            username:"张三",

        }
    });
</script>

```

#  渲染表数据

```
<body>
    <!-- 希望 Vue 能够控制下面的这个 div，帮我们把数据填充到 div 内部 -->
    <div id="app">
        <!-- 边框  鼠标放上去高亮  隔行变色 -->
        <table class="table table-bordered table-hover table-striped">
            <thead>
                <th>索引</th>
                <th>Id</th>
                <th>姓名</th>
            </thead>
            <tbody>
                <!-- 官方建议：只要用到了 v-for 指令，那么一定要绑定一个 :key 属性 -->
                <!-- 而且，尽量把 id 作为 key 的值 -->
                <!-- 官方对 key 的值类型，是有要求的：字符串或数字类型 -->
                <!-- key 的值是千万不能重复的，否则会终端报错：Duplicate keys detected -->
                <tr v-for="(item, index) in list" :key="item.id">
                    <td>{{ index }}</td>
                    <td>{{ item.id }}</td>
                    <td>{{ item.name }}</td>
                </tr>
            </tbody>
        </table>
    </div>

    <!-- 1. 导入 Vue 的库文件，在 window 全局就有了 Vue 这个构造函数 -->
    <script src="./lib/vue-2.6.12.js"></script>
    <!-- 2. 创建 Vue 的实例对象 -->
    <script>
        // 创建 Vue 的实例对象
        const vm = new Vue({
            // el 属性是固定的写法，表示当前 vm 实例要控制页面上的哪个区域，接收的值是一个选择器
            el: '#app',
            // data 对象就是要渲染到页面上的数据
            data: {
                list: [{
                    id: 1,
                    name: '张三'
                }, {
                    id: 2,
                    name: '李四'
                }, {
                    id: 3,
                    name: '王五'
                }, {
                    id: 4,
                    name: '张三'
                }, ]
            }
        })
    </script>
</body>
```

![image-20230227132434456](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/image-20230227132434456.png)

```
<body>
  <!-- 在页面中声明一个将要被 vue 所控制的 DOM 区域 -->
  <div id="app">
    <!-- 添加用户的区域 -->
    <div>
      <input type="text" v-model="name">
      <button @click="addNewUser">添加</button>
    </div>
    <!-- 用户列表区域 -->
    <ul>
      <li v-for="(user, index) in userlist" :key="user.id">
        <input type="checkbox" />
        姓名：{{user.name}}
      </li>
    </ul>
  </div>

  <script src="./lib/vue-2.6.12.js"></script>
  <script>
    const vm = new Vue({
      el: '#app',
      data: {
        // 用户列表
        userlist: [
          { id: 1, name: 'zs' },
          { id: 2, name: 'ls' }
        ],
        // 输入的用户名
        name: '',
        // 下一个可用的 id 值
        nextId: 3
      },
      methods: {
        // 点击了添加按钮
        addNewUser() {
          this.userlist.unshift({ id: this.nextId, name: this.name })
          this.name = ''
          this.nextId++
        }
      },
    })
  </script>
```

![截屏2023-02-27 13.29.09](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-02-27%2013.29.09.png)

#   过滤器（vue3取消）

```
<body>
  <div id="app">
    <p>message 的值是：{{ message | capi }}</p>
  </div>

  <script src="./lib/vue-2.6.12.js"></script>
  <script>
    const vm = new Vue({
      data: {
        message: 'hello vue.js'
      },
      // 过滤器函数，必须被定义到 filters 节点之下
      // 过滤器本质上是函数
      filters: {
        // 注意：过滤器函数形参中的 val，永远都是“管道符”前面的那个值
        capi(val) {
          // 字符串有 charAt 方法，这个方法接收索引值，表示从字符串中把索引对应的字符，获取出来
          // val.charAt(0)
          const first = val.charAt(0).toUpperCase()
          // 字符串的 slice 方法，可以截取字符串，从指定索引往后截取
          const other = val.slice(1)
          // 强调：过滤器中，一定要有一个返回值
          return first + other
        }
      }
    })
  </script>
</body>
```

#    watch 监听器

```
<body>
  <div id="app">
    <input type="text" v-model="username">
  </div>

  <script>
    const vm = new Vue({
      data: {
        username: 'admin'
      },
      // 所有的侦听器，都应该被定义到 watch 节点下
      watch: {
        // 侦听器本质上是一个函数，要监视哪个数据的变化，就把数据名作为方法名即可
        // 新值在前，旧值在后
        username(newVal) {
          if (newVal === '') return
          // 1. 调用 jQuery 中的 Ajax 发起请求，判断 newVal 是否被占用！！！
          $.get('https://www.escook.cn/api/finduser/' + newVal, function (result) {
            console.log(result)
          })
        }
      }
    })
  </script>
</body>
```

#   Computed 计算属性

```
<body>
  <div id="app">
    <div>
      <span>R：</span>
      <input type="text" v-model.number="r">
    </div>
    <div>
      <span>G：</span>
      <input type="text" v-model.number="g">
    </div>
    <div>
      <span>B：</span>
      <input type="text" v-model.number="b">
    </div>
    <hr>

    <!-- 专门用户呈现颜色的 div 盒子 -->
    <!-- 在属性身上，: 代表  v-bind: 属性绑定 -->
    <!-- :style 代表动态绑定一个样式对象，它的值是一个 {  } 样式对象 -->
    <!-- 当前的样式对象中，只包含 backgroundColor 背景颜色 -->
    <div class="box" :style="{ backgroundColor: rgb }">
      {{ rgb }}
    </div>
    <button @click="show">按钮</button>
  </div>

  <script>
    // 创建 Vue 实例，得到 ViewModel
    var vm = new Vue({
      el: '#app',
      data: {
        // 红色
        r: 0,
        // 绿色
        g: 0,
        // 蓝色
        b: 0
      },
      methods: {
        // 点击按钮，在终端显示最新的颜色
        show() {
          console.log(this.rgb)
        }
      },
      // 所有的计算属性，都要定义到 computed 节点之下
      // 计算属性在定义的时候，要定义成“方法格式”
      computed: {
        // rgb 作为一个计算属性，被定义成了方法格式，
        // 最终，在这个方法中，要返回一个生成好的 rgb(x,x,x) 的字符串
        rgb() {
          return `rgb(${this.r}, ${this.g}, ${this.b})`
        }
      }
    });

    console.log(vm)
  </script>
</body>
```

![截屏2023-02-27 13.48.18](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-02-27%2013.48.18.png)

#    组件通讯

##    1. 父->子

- 方式：通过子组件`props`属性来传递数据 props是一个数组
- 注意：属性的值必须在组件中通过`props`属性显示指定，否则，不会生效
- 说明：传递过来的`props`属性的用法与`data`属性的用法相同

```
<div id="app">
  <!-- 如果需要往子组件总传递父组件data中的数据 需要加v-bind="数据名称" -->
  <hello v-bind:msg="info"></hello>
  <!-- 如果传递的是字面量 那么直接写-->
  <hello my-msg="abc"></hello>
</div>

<!-- js -->
<script>script">
  new Vue({
    el: "#app",
    data : {
      info : 15
    },
    components: {
      hello: {
        // 创建props及其传递过来的属性
        props: ['msg', 'myMsg'],
        template: '<h1>这是 hello 组件，这是消息：template-variable">{{msg}} --- template-variable">{{myMsg}}</h1>'
      }
    }
  })
</script>
```

##  2. 子->父

方式：父组件给子组件传递一个函数，由子组件调用这个函数

- 说明：借助vue中的自定义事件（v-on:cunstomFn="fn"）

步骤:

- 1、在父组件中定义方法 parentFn
- 2、在子组件 组件引入标签 中绑定自定义事件 v-on:自定义事件名="父组件中的方法" ==> @pfn="parentFn"
- 3、子组件中通过`$emit()`触发自定义事件事件 this.$emit(pfn,参数列表。。。)

```
<hello @pfn="parentFn"></hello>

<script>script">
  Vue.component('hello', {
    template: '<button @click="fn">按钮</button>',
    methods: {
      // 子组件：通过$emit调用
      fn() {
        this.$emit('pfn', '这是子组件传递给父组件的数据')
      }
    }
  })
  new Vue({
    methods: {
      // 父组件：提供方法
      parentFn(data) {
        console.log('父组件：', data)
      }
    }
  })
</script>
```

##   3.非父子组件

- `$on()`：绑定自定义事件

```
var bus = new Vue()

// 在组件 B 绑定自定义事件
bus.$on('id-selected', function">function (id) {
  // ...
})
// 触发组件 A 中的事件
bus.$emit('id-selected', 1)
```

- 示例：组件A ---> 组件B

```
<!-- 组件A： -->
<com-a></com-a>
<!-- 组件B： -->
<com-b></com-b>

<script>script">
  // 中间组件
  var bus = new Vue()
  // 通信组件
  var vm = new Vue({
    el: '#app',
    components: {
      comB: {
        template: '<p>组件A告诉我：{{msg}}</p>',
        data() {
          return {
            msg: ''
          }
        },
        created() {
          // 给中间组件绑定自定义事件 注意:如果用到this 需要用箭头函数
          bus.$on('tellComB', (msg) => {
            this.msg = msg
          })
        }
      },
      comA: {
        template: '<button @click="emitFn">告诉B</button>',
        methods: {
          emitFn() {
            // 触发中间组件中的自定义事件
            bus.$emit('tellComB', '土豆土豆我是南瓜')
          }
        }
      }
    }
  })
</script>
```

##  4. slot

- 通过<slot></slot> 标签指定内容展示区域

```
<!-- html代码 -->
<div id="app">
  <hello>
    <!-- 如果只有一个slot插槽 那么不需要指定名称 -->
    <p slot="插槽名称">我是额外的内容</p>
  </hello>
</div>
```

```
// js代码
new vue({
  el : "#app",
  components : {
    hello : {
      template : `
          <div>
            <p>我是子组件中的内容</p>
            <slot name="名称"></slot>
          </div>
        `
    }
  }
})
```

## 5. 获取组件/元素refs

- 说明：`vm.$refs` 一个对象，持有已注册过 ref 的所有子组件（或HTML元素）
- 使用：在 HTML元素 中，添加`ref`属性，然后在JS中通过`vm.$refs.属性`来获取
- 注意：如果获取的是一个子组件，那么通过ref就能获取到子组件中的data和methods

```
<div id="app">
  <div ref="dv"></div>
  <my res="my"></my>
</div>

<!-- js -->
<script>script">
  new Vue({
    el : "#app",
    mounted() {
      this.$refs.dv //获取到元素
      this.$refs.my //获取到组件
    },
    components : {
      my : {
        template: `<a>sss</a>`
      }
    }
  })
</script>
```

#   路由守卫

```
// src/router/index.js 就是当前项目的路由模块
// 1.导入 Vue 和VueRouter的包
import Vue from 'vue'
import VueRouter from 'vue-router'

// 导入需要的组件
import Home from '@/components/Home.vue'
import Movie from '@/components/Movie.vue'
import About from '@/components/About.vue'

import Tab1 from '@/components/tabs/Tab1.vue'
import Tab2 from '@/components/tabs/Tab2.vue'

import Login from '@/components/Login.vue'
import Main from '@/components/Main.vue'

// 把 VueRouter 安装为 Vue 项目的插件
// Vue.use() 函数的作用，就是来安装插件的
// 2.调用Vue.use()函数 把VueRouter安装为Vue的插件
Vue.use(VueRouter)

// 3.创建路由的实例对象
const router = new VueRouter({
    // routes 是一个数组，作用：定义 “hash 地址” 与 “组件” 之间的对应关系
    routes: [
        // 重定向的路由规则
        { path: '/', redirect: '/home' },
        // 路由规则
        { path: '/home', component: Home },
        // 需求：在 Movie 组件中，希望根据 id 的值，展示对应电影的详情信息
        // 可以为路由规则开启 props 传参，从而方便的拿到动态参数的值
        { path: '/movie/:mid', component: Movie, props: true },
        {
            path: '/about',
            component: About,
            // redirect: '/about/tab1',
            children: [
                // 子路由规则
                // 默认子路由：如果 children 数组中，某个路由规则的 path 值为空字符串，则这条路由规则，叫做“默认子路由”
                { path: '', component: Tab1 },
                { path: 'tab2', component: Tab2 }
            ]
        },
        { path: '/login', component: Login },
        { path: '/main', component: Main }
    ]
})

// 为 router 实例对象，声明全局前置导航守卫
// 只要发生了路由的跳转，必然会触发 beforeEach 指定的 function 回调函数
router.beforeEach(function(to, from, next) {
    // to 表示将要访问的路由的信息对象
    // from 表示将要离开的路由的信息对象
    // next() 函数表示放行的意思
    // 分析：
    // 1. 要拿到用户将要访问的 hash 地址
    // 2. 判断 hash 地址是否等于 /main。
    // 2.1 如果等于 /main，证明需要登录之后，才能访问成功
    // 2.2 如果不等于 /main，则不需要登录，直接放行  next()
    // 3. 如果访问的地址是 /main。则需要读取 localStorage 中的 token 值
    // 3.1 如果有 token，则放行
    // 3.2 如果没有 token，则强制跳转到 /login 登录页
    if (to.path === '/main') {
        // 要访问后台主页，需要判断是否有 token
        const token = localStorage.getItem('token')
        if (token) {
            next()
        } else {
            // 没有登录，强制跳转到登录页
            next('/login')
        }
    } else {
        next()
    }
})

// 4.向外共享路由的实例对象
export default router
```



#   数据类型转换

```
/整数/parseInt(string)

/分数/parseFloat(string)

/Number/Number(val)

保留几位小数在方法后面加.toFixed()，比如去分数保留2位小数parseFloat(string).toFixed(2)；
```

#   登陆前后 页面显示不同

(1)在父组件App.vue的底部导航栏组件渲染标签处引入<v-show>或者<v-if>标签实现导航栏的显示与隐藏状态【<bottom-nav v-show="showNav"></bottom-nav>】，首先设置一个showNav标志，未登录时showNav值为false【showNav: false】，导航栏不显示。

![截屏2023-02-27 15.30.20](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-02-27%2015.30.20.png)

（2）在子组件Login.vue页面，当登录成功，设置showNav值为true，【this.$parent.showNav = true;】导航栏显示。

![截屏2023-02-27 15.30.40](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-02-27%2015.30.40.png)

（3）另外，在登录成功之后跳转的每一个页面中的【created】中设置showNav值为true

![截屏2023-02-27 15.31.09](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-02-27%2015.31.09.png)

实际项目

```
<template>
  <div class="top-nav">
    <div class="log" @click="gotoHome" title="去首页">
      <img style="width: 50px; height: 50px" src="@/assets/images/logo.png" />
      深地探测科学数据中心
    </div>
    <el-menu
      :active-text-color="variables.menuActiveText"
      :default-active="activeMenu"
      mode="horizontal"
      @select="handleSelect"
    >
      <div v-for="item in routes" :key="item.path" class="nav-item">
        <app-link :to="resolvePath(item)">
          <el-menu-item v-if="!item.hidden" :index="item.path">{{
            item.meta ? item.meta.title : item.children[0].meta.title
          }}</el-menu-item>
        </app-link>
      </div>
    </el-menu>

    <div class="right-menu" style="margin-right: 20px">
      <img
        style="width: 30px; height: 30px"
        src="@/assets/images/user.png"
        class="user-avatar"
      />
      <el-dropdown v-if="token" class="avatar-container" trigger="click">
        <div class="avatar-wrapper">
          <span style="color: #fff; cursor: pointer">{{ username }}</span>
          <i class="el-icon-arrow-down" style="cursor: pointer" />
        </div>
        <el-dropdown-menu slot="dropdown" class="user-dropdown">
          <!-- <router-link @click.native="toHome" to="/">
            <el-dropdown-item>进入首页</el-dropdown-item>
          </router-link> -->
          <!-- <router-link @click.native="toPersonalCenter" to="/user">
            <el-dropdown-item>个人资料</el-dropdown-item>
          </router-link> -->
          <router-link
            v-show="token"
            @click.native="toApplit"
            to="/user/fetch-list"
          >
            <el-dropdown-item>申请列表</el-dropdown-item>
          </router-link>
          <el-dropdown-item divided @click.native="logout">
            <span style="display: block"> 退出登录 </span>
          </el-dropdown-item>
        </el-dropdown-menu>
      </el-dropdown>
      <template v-else>
        <el-button type="text" @click="goLogin"> 登录 </el-button>
        <el-button type="text" @click="goRegister"> 注册 </el-button>
      </template>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapState, mapActions } from "vuex";
import AppLink from "./Sidebar/Link";
import { constantRoutes } from "@/router";
import variables from "@/styles/variables.scss";
import { getToken, getName, setName, setToken } from "@/utils/auth";
import bus from "@/utils/bus.js";
import { isExternal } from "@/utils/validator";

export default {
  name: "Topbar",
  components: {
    AppLink,
  },
  data() {
    return {
      menuStr: "",
      routes: JSON.parse(JSON.stringify(constantRoutes)),
    };
  },
  computed: {
    ...mapState("user", {
      token: (state) => {
        return getToken() ? getToken() : state.token;
      },
      username: (state) => {
        return getName() ? getName() : state.username;
      },
      phoneMobile: (state) => {
        return state.phoneMobile;
      },
    }),
    activeMenu() {
      const route = this.$route;
      const { meta, path } = route;
      // if set path, the sidebar will highlight the path you set
      if (meta.activeMenu) {
        return meta.activeMenu;
      }
      // 如果是首页，首页高亮
      if (path === "/home-page") {
        return "/";
      }
      // 如果不是首页，高亮一级菜单
      const activeMenu = "/" + path.split("/")[1];
      return activeMenu;
    },
    variables() {
      return variables;
    },
    sidebar() {
      return this.$store.state.app.sidebar;
    },
    ...mapGetters(["avatar"]),
  },
  mounted() {
    this.getMenu();
    this.initCurrentRoutes();
  },
  methods: {
    ...mapActions("user", {
      GetUserMenu: "GetUserMenu",
    }),
    // 跳转首页
    gotoHome() {
      this.$router.push("/");
    },
    // 菜单过滤
    menuFilter(route) {
      let res = [];
      if (route) {
        route.forEach((item) => {
          // if (item.meta && item.meta.title == "数据管理") {
          //   res.push(item);
          //   return;
          // }
          if (item.meta && this.menuStr.indexOf(item.meta.title) > -1) {
            this.$set(item, "hidden", false);
            if (item.children) {
              this.menuFilter(item.children);
            }
          } else {
            this.$set(item, "hidden", true);
          }
          res.push(item);
        });
      }
      return res;
    },
    getUserMenuList() {
        this.GetUserMenu().then((response) => {
        this.menuStr = JSON.stringify(response.data);
        this.routes = this.menuFilter(this.routes);
      });
    },
    // 获取菜单
    getMenu() {
      getToken() ? this.getUserMenuList() : "";
    },
    // 去首页
    toHome() {
      this.handleSelect("/");
    },
    // 去往申请列表
    toApplit() {
      if (!this.token) {
        this.$confirm("此操作需要登录, 是否继续?", "提示", {
          confirmButtonText: "去登录",
          cancelButtonText: "取消",
          type: "warning",
        })
          .then(() => {
            this.$router.push("/login");
          })
          .catch(() => {
            this.$message({
              type: "info",
              message: "已取消",
            });
          });
      } else {
        this.handleSelect("/user");
      }
    },
    // 去个人中心
    toPersonalCenter() {
      this.handleSelect("/user");
    },
    // 通过当前路径找到二级菜单对应项，存到store，用来渲染左侧菜单
    initCurrentRoutes() {
      const { path } = this.$route;
      let route = this.routes.find(
        (item) => item.path === "/" + path.split("/")[1]
      );
      // 如果找不到这个路由，说明是首页
      if (!route) {
        route = this.routes.find((item) => item.path === "/");
      }
      this.$store.commit("permission/SET_CURRENT_ROUTES", route);
      this.setSidebarHide(route);
    },
    // 判断该路由是否只有一个子项或者没有子项，如果是，则在一级菜单添加跳转路由
    isOnlyOneChild(item) {
      if (item.children && item.children.length === 1) {
        return true;
      }
      return false;
    },
    resolvePath(item) {
      // 如果是个完成的url直接返回
      if (isExternal(item.path)) {
        return item.path;
      }
      // 如果是首页，就返回重定向路由
      if (item.path === "/") {
        const path = item.redirect;
        return path;
      }

      // 如果有子项，默认跳转第一个子项路由
      let path = "";
      /**
       * item 路由子项
       * parent 路由父项
       */
      const getDefaultPath = (item, parent) => {
        // 如果path是个外部链接（不建议），直接返回链接，存在个问题：如果是外部链接点击跳转后当前页内容还是上一个路由内容
        if (isExternal(item.path)) {
          path = item.path;
          return;
        }
        // 第一次需要父项路由拼接，所以只是第一个传parent
        if (parent) {
          path += parent.path + "/" + item.path;
        } else {
          path += "/" + item.path;
        }
        // 如果还有子项，继续递归
        if (item.children) {
          getDefaultPath(item.children[0]);
        }
      };

      if (item.children) {
        getDefaultPath(item.children[0], item);
        return path;
      }

      return item.path;
    },
    handleSelect(key, keyPath) {
      if (!this.token && key == "/user") {
        this.$router.push("/login");
        return;
      }
      // 把选中路由的子路由保存store
      const route = this.routes.find((item) => item.path === key);
      // if (!this.token && key == "/user") {
      //   this.$confirm("此操作需要登录, 是否继续?", "提示", {
      //     confirmButtonText: "去登录",
      //     cancelButtonText: "取消",
      //     type: "warning",
      //   })
      //     .then(() => {
      //       this.$router.push("/login");
      //     })
      //     .catch(() => {
      //       this.$message({
      //         type: "info",
      //         message: "已取消",
      //       });
      //     });
      // } else {
      this.$store.commit("permission/SET_CURRENT_ROUTES", route);
      this.setSidebarHide(route);
      // }
    },
    // 设置侧边栏的显示和隐藏
    setSidebarHide(route) {
      if (!route.children || route.children.length === 1) {
        this.$store.dispatch("app/toggleSideBarHide", true);
      } else {
        this.$store.dispatch("app/toggleSideBarHide", false);
      }
    },
    goLogin() {
      this.$router.push(`/login?redirect=${this.$route.fullPath}`);
    },
    async logout() {
      await this.$store.dispatch("user/logout");
      history.pushState(history.state.key, "首页", "#/home-page");
      this.$nextTick(() => {
        setName("");
        setToken("");
        this.$router.push(`/login?redirect=${this.$route.fullPath}`);
      });
    },
    goRegister() {
      this.$router.push({
        name: "login",
        params: {
          register: true,
        },
      });
    },
  },
  beforeMount() {
    this.routes = JSON.parse(JSON.stringify(constantRoutes));
  },
};
</script>
<style scoped>
.log {
  cursor: pointer;
}
</style>

```

```
{
  path: '/statistic',
  component: Layout,
  hidden: true,
  name: 'statistic',
  meta: {
    title: '数据管理',
    icon: 'example'
  },
},
```



#      111111111111111111111111111111111



#   安装element-ui   element-plus

npm install --save element-plus



npm i element-ui -S

1. 在 main.js 中写入以下内容：

   ```
   import ElementUI from 'element-ui'; 
   
   import 'element-ui/lib/theme-chalk/index.css';
   
   Vue.use(ElementUI);
   ```

#   登陆页面

1. App.vue

```
<template>
  <div id="app">
    <router-view/>
  </div>
</template>
```

2. Index.js

```
import Login from '../views/Login.vue'

const routes = [
  {
    path: '/',
    name: 'Login',
    component: Login
  }
]
```

2. Login.vue

```
<template>
  <div>
    <el-form :ref="loginForm" :model="loginForm" class="loginContainer">
      <h3 class="loginTitle">系统登陆</h3>
      <el-form-item>
        <el-input type="text" auto-complete="false" v-model="loginForm.username"
                  placeholder="请输入用户名"></el-input>
      </el-form-item>
      <el-form-item>
        <el-input type="password" auto-complete="false" v-model="loginForm.password"
                  placeholder="请输入用户密码"></el-input>
      </el-form-item>
      <el-form-item>
        <el-input type="text" auto-complete="false" v-model="loginForm.code"
                  placeholder="点击图片更换验证码" style="width: 250px"></el-input>
        <img :src="captchaUrl">
      </el-form-item>
      <el-checkbox v-model="checked" class="loginRemember">记住我</el-checkbox>
      <el-button type="primary" @click="onSubmit" style="width: 100%">登陆</el-button>
    </el-form>
  </div>
</template>

<script>
export default {
  name: "Login",
  data() {
    return {
      captchaUrl: '',
      loginForm: {
        username: 'admin123',
        password: '123456',
        code: ''
      },
       // 默认记住我 是确认的
      checked: true
    }
  },
  created() {
  },
  methods: {}
}
</script>

<style>
.loginContainer{
  background: #fff;
  /*背景延伸到边框外沿*/
  background-clip: padding-box;
  border-radius: 15px;
  /*form表单居中*/
  margin: 180px auto;
  width: 350px;
  padding: 15px 35px 15px 35px;
  border: 1px solid #eaeaea;
  box-shadow: 0 0 25px #eaeaeacac6c6;
}
.loginRemember{
  text-align: left;
  margin: 0px 0px 15px 0px;
}
.loginTitle{
  margin: 10px auto 30px auto;
  /*文字居中*/
  text-align: center;
}
</style>
```

3. 给form表单 添加验证规则

```
<el-form :rules="rules" ref="loginForm" :model="loginForm" class="loginContainer">
 <el-form-item prop="username">
        。。。
      <el-form-item prop="password">
      。。。
      <el-form-item prop="code">
        。。。
      </el-form-item>
// 这是表单的验证规则对象
//验证规则是与  prop="username"  相关的
      rules: {
        // 验证用户名是否合法
        username: [
          {required: true, message: '请输入登陆名称', trigger: 'blur'},
          {min: 3, max: 10, message: '长度在 3 到 10个字符', trigger: 'blur'}
        ],
        // 验证密码是否合法
        password: [
          {required: true, message: '请输入登陆密码', trigger: 'blur'},
          {min: 6, max: 15, message: '长度在 6 到 15个字符', trigger: 'blur'}
        ],
        code: [
          {required: true, message: '请输入验证码', trigger: 'blur'},
          {min: 3, max: 10, message: '长度在 3 到 10个字符', trigger: 'blur'}
        ],
```

4. 添加登陆的点击事件

```
submitForm(formName) {
  this.$refs.loginForm.validate((valid) => {
    if (valid) {
      alert('submit!');
    } else {
      alert("123")
    }
  }
 );
```

5. 安装axios  调用后端接口

```
 npm i axios
```

#   基础语法

```
<template>
<div>
  <h1>hello world!</h1>
   <p v-text="name"></p>
   <!-- v-text的简写 -->
   <p>{{name}}</p>
    <!-- v-html -->
    <p>{{info}}</p>
    <p v-html="info"></p>
    <!-- v-bind:属性名="变量名"绑定动态的标签属性   简写：  :属性名="变量名"--> 
    <p v-bind:data="dataVal">我有属性data</p>
    <!-- class类名绑定  可以叠加使用 -->
    <p class="text" :class="{'red':!isRed}">我是红色的</p>
    <!-- 判断语句  v-if   false的时候 是元素未渲染在页面-->
    <!-- v-show :false的时候 是样式上的隐藏 -->
    <p v-if="!isTrue">我是if存在</p>
    <p v-show="!isTrue">我是show展示</p>

    <p v-if="isFalse">if</p>
    <p v-else>else</p> 
    <!-- for循环 -->
    <ul>
      <!-- 循环此数组userList  -->
      <!-- v-for="(每一个对象的变量,下标) in 数组"  -->
      <li v-for="(item,index) in userList" :key="index">
        学生姓名：{{item.username}}
        学生年龄：{{item.userage}}
      </li>
    </ul>
  </div>
</template>

<script>
  import {reactive,toRefs} from "vue"
  export default{
    name:"home",
    setup() {
      // beforeCreate和created 两个生命周期
      const data = reactive({
        name:"小红",
        age:20,
        info:"<i>我是斜体字</i>",
        dataVal:20,
        isRed:true,
        isTrue:true,
        isFalse:false, 
        userList:[
          {
            username:"小红",
            userage:10
          },
          
          {
            username:"小明",
            userage:12
          },
          {
            username:"小李",
            userage:13
          },
          {
            username:"小蓝",
            userage:14
          },
          {
            username:"杰克",
            userage:11
          }
        ]
      })
      return{
        ...toRefs(data)
      }
    }
  }
</script>
<style >
  .red{
    color: red;
  }
</style>

```

##    生命周期

```
<template>
  <div>
    <h2>vue3的生命周期</h2>
    <div id="dom">{{ msg }}--{{ num }}</div>
    <!-- v-on:事件名="事件方法" 绑定事件 简写@:事件名="事件方法" -->
    <!-- 事件及方法直接声明在 setup内-->
    <button v-on:click="handleClick">click me</button>
    <hr />
    <!-- v-model 双向绑定 -->
    <!-- input：输入事件 
        blur:失去焦点
        focus:获取焦点
        change：内容更改
    -->
    <input type="text" placeholder="请输入姓名" v-model="userName" /><br />
    <input
      type="text"
      placeholder="请输入电话"
      v-model="userPhone"
      @focus="handleFocus"
      @blur="handleBlur"
      @input="handleInput"
      @change="handleChange"
    /><br />
    <textarea
      placeholder="请输入您的建议"
      cols="30"
      rows="10"
      v-model="userInput"
    ></textarea>
    <p>{{ userName }}---{{ userInput }}</p>
    <button @click="submit">提交</button>
  </div>
</template>
<script>
import {
  reactive,
  toRefs,
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated
} from 'vue'
export default {
  name: 'about',
  setup() {
    const data = reactive({
      msg: '你好！',
      msg2: 'hello world',
      num: 0,
      userName: '',
      userInput: '',
      userPhone: ''
    })
    // 数据渲染前
    onBeforeMount(() => {
      console.log('onBeforeMount', document.querySelector('#dom'))
    })
    // 数据渲染后
    onMounted(() => {
      console.log('onMounted', document.querySelector('#dom'))
      setTimeout(() => {
        data.msg = 'hello'
        // data.msg2="hello"
      }, 2000)
    })
    // dom更新前
    onBeforeUpdate(() => {
      console.log('onBeforeUpdate')
    })
    // dom更新前
    onUpdated(() => {
      console.log('onUpdated')
      // data.num+=1;//出发死循环
    })
    // 事件及方法
    const handleClick = () => {
      alert('你好')
    }
    const submit = () => {
      alert(`${data.userName}的建议是${data.userInput}`)
    }
    const handleFocus = () => {
      console.log('获取焦点了')
    }
    const handleBlur = () => {
      return
    }
    const handleInput = () => {
      //  正则验证手机号
      return
    }
    const handleChange = () => {
      //  正则验证手机号
      if (!/^[1][3,4,5,7,8][0-9]{9}$/.test(data.userPhone)) {
        console.log('不符合手机号')
      } else {
        console.log('符合手机号')
      }
    }
    return {
      ...toRefs(data),
      handleClick,
      submit,
      handleFocus,
      handleBlur,
      handleInput,
      handleChange
    }
  }
}
</script>

```

#  生命周期

Vue生命周期函数就是vue实例在某一个时间点会自动执行的函数

1. beforeCreate（）{}：Vue创建前，此阶段为实例初始化之后，this指向创建的实例，数据观察,数据监听事件机制都未形成，不能获得DOM节点。data，computed，watch，methods 上的方法和数据均不能访问，注：date和methods的数据都还未初始化。

   当Vue对象创建之前触发的函数（beforeCreate）

2. Created（）{}：  已经在内存中创建好了，data和methods都可以使用 但还没有编译模版

   Vue创建后，此阶段为实例初始化之后，data、props、computed的初始化导入完成， 注：要调用methods中的方法，或者操作data中的数据，最早只能在Created中操作能访问 data computed watch methods 上的方法和数据，初始化完成时的事件写这个里面，此阶段还未挂载DOM。

​       Vue对象创建完成触发的函数(Created)

3. beforeMount（）{}: Vue载入前，阶段执行时，  模板已经在内存中编译好了，但是未挂载到页面中，（页面还是旧的）

注：这个阶段是过渡性的，一般一个项目只能用到一两次。

​     当Vue对象开始挂载数据的时候触发的函数(beforeMount)

4. Mounted（）{}：编译好模版 挂载到了页面指定的容器中显示数据

   Vue载入后，(完成创建vm.$el，和双向绑定)； 只要执行完mounted,就表示整个Vue实例已经初始化完成了，此时组件已经脱离里了创建阶段， 进入到了运行阶段。

​       当Vue对象挂载数据的完成的时候触发的函数(Mounted)

5. beforeUpdate（）{}:Vue更新前， 当执行beforeUpdate的时候，页面中显示的数据还是旧的，此时date数据是最新的，页面尚未和最新数据数据保持同步。但是DOM中的数据会改变，这是vue双向数据绑定的作用，可在更新前访问现有的DOM，如手动移出添加的事件监听器。

​        Vue对象中的data数据发生改变之前触发的函数 (beforeUpdate)

6. Updated（）{}：Vue更新后， Updated执行时数据已经保持同步了，都是最新的，完成虚拟DOM的重新渲染和打补丁。
   组件DOM已完成更新，可执行依赖的DOM操作。

    Vue对象中的data数据发生改变完成触发的函数(Updated)

注意：不要在此函数中操作数据（修改属性），否则就会陷入死循环。

7. beforeDestroy（）{}：（Vue销毁前，可做一些删除提示，比如：您确定删除****吗？）当执行beforeDestroy的时候，Vue实例就已经从运行阶段进入到销毁阶段了。实例上的所有date和methods以及过滤器和指令都是处于可用状态，此时还没有真正的执行销毁过程。

​      Vue对象销毁之前触发的函数 (beforeDestroy)

8. Destroyed（）{}：Vue销毁后, 当执行到destroted函数的时候，组件已经完全销毁（渣都不剩），此时组件中的所有的数据，方法，指令，过滤器...都已经销毁（不可用了）。

   Vue对象销毁完成触发的函数(Destroy)

1. 建立前后

```
<div id="root"></div>
<script type="text/javascript">
var vm=new Vue({
el:"#root",
beforeCreate:function(){//01 建立之前
console.log("before create");
},
created:function(){
console.log("created");//02 建立之后
}
})
</script>

```

2. 有模板的渲染情况(按模板渲染)

```
<div id="root"></div>
<script type="text/javascript">
var vm=new Vue({
el:"#root",
data:{},
beforeCreate:function(){
console.log("before create");
},
created:function(){
console.log("created");
},
template:'<h1>123</h1>',//如果有模板的话模板替换 EL
})
</script>

```

3. 02-1 无模板的渲染情况(按挂载元素渲染)

```
<div id="root">{{message}}</div>
<script type="text/javascript">
var vm=new Vue({
el:"#root",
data:{
message:"hello vue!"
},
beforeCreate:function(){
console.log("before create");
},
created:function(){
console.log("created");
},
//如果无模板则用默认的 el 作为挂载点的模板
/*template:'<h1>123</h1>',*/ 
})

```

4. 挂载前后

```
<div id="root"></div>
<script type="text/javascript">
//备注：没有模板无论是挂载前还是挂载后均显示原有 el 的结构
var vm=new Vue({
el:"#root",
data:{},
beforeCreate:function(){
console.log("before create");
},
created:function(){
console.log("created");
},
beforeMount:function(){//挂载之前
console.log(this.$el);
console.log("before mount")
},
mounted:function(){
console.log(this.$el);
console.log("mounted")
}
})
</script>

```

5. 销毁前后

```
<div id="root">{{message}}</div>
<script type="text/javascript">
//备注：有模板情情况显示的是模板
var vm=new Vue({
el:"#root",
data:{
message:"未挂载模板之前的显示"
},
template:"<h1>This is h1 template</h1>",
beforeCreate:function(){
console.log("before create");
},
created:function(){
console.log("created");
},
beforeMount:function(){//挂载之前
console.log(this.$el);
console.log("before mount")
},
mounted:function(){
console.log(this.$el);
console.log("mounted")
},
//以下两个在控制台并不能被打印出来，执行完 vm.$destroy()即可以打印
beforeDestroy:function(){
console.log("before destroy");
},
destroyed:function(){
console.log("destoryed");
}
})
</script>

```

6. 更新前后

```
<div id="root">{{message}}</div>
<script type="text/javascript">
//备注：有模板情情况显示的是模板
var vm=new Vue({
el:"#root",
data:{
message:"This is a message"
},
//template:"<h1>This is h1 template</h1>",
beforeCreate:function(){
console.log("before create");
},
created:function(){
console.log("created");
},
beforeMount:function(){//挂载之前
console.log(this.$el);
console.log("before mount")
},
mounted:function(){
console.log(this.$el);
console.log("mounted")
},
//以下两个在控制台并不能被打印出来，执行完 vm.$destroy()即可以打印
beforeDestroy:function(){
console.log("before destroy");
},
destroyed:function(){
console.log("destoryed");
},

```

//beforeUpdate 与 updated 并不能打印输出，只有在控制台输入 vm.$data.message="新值后"才可以看到结果

```
//更新前
beforeUpdate:function(){
console.log("beforeUpdate");
},

//更新后
updated:function(){
console.log("updated")
}
})

```

![截屏2023-02-24 14.26.11](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-02-24%2014.26.11.png)

#   router/index.js

```
import { createRouter, createWebHashHistory } from 'vue-router'
import LayOut from '../views/LayOut/LayOut' 
import store from "../store/index.js"
// 路由配置
const routes = [
  // 登陆页面
  {
    path:"/login",
    name:"login",
    component:()=>import("../views/pages/login.vue")
  },
 {
    path:"/",
    name:"layout",
    component:LayOut,
    redirect:"/index",
    // 子路由/嵌套路由
    children:[
      {
        path:"/index",
        name:"index",
        component:()=>import("../views/pages/index.vue")
      }, 
      {
        path:"/goods",
        name:"goods",
        component:()=>import("../views/pages/goodsList.vue")
      }
    ]
 }
]
// 生成hash路由对象
const router = createRouter({
  history: createWebHashHistory(),
  routes
})

//路由守卫
router.beforeEach((to,form,next)=>{
  /**
   * to:从哪个页面
   * from:到哪个页面
   * next:只有执行next()页面才会进行跳转
   */
  // 判断用户是否登录
  console.log("store",store.state.uInfo)
  const uInfo = store.state.uInfo.userInfo  
  if(!uInfo.username){ 
    // 未登录,跳转到login 
    if(to.path==="/login"){
      next()
      return
    }
    next("/login")
  }else{
    next()
  }
})
// 暴露路由对象
export default router

```

##    router-view   router-link

```
  <!-- 相当a标签,to="路由path" -->
  <!-- <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav> -->
  <!-- router-view:展示路由对应的组件内容 -->
  <router-view/> 
```

#    main.js

```
import { createApp } from 'vue'
import App from './App.vue'
import router from './router'
import store from './store'
import ElementPlus from 'element-plus'
import 'element-plus/dist/index.css'
import * as ElementPlusIconsVue from '@element-plus/icons-vue'
const app =createApp(App)
// element icon 注册
for (const [key, component] of Object.entries(ElementPlusIconsVue)) {
    app.component(key, component)
  }
app.use(store).use(router).use(ElementPlus).mount('#app')

```

#   store/index.js

```
import { createStore } from 'vuex'
import uInfo from './state/userinfo.state.js'
export default createStore({
  // 数据比较多,分模块
  modules: {
    uInfo
  }
})

```



#   store/state/userinfo.js

```
//登陆 
export default{
//保存登陆后的密码 账号数据
    state:{
        userInfo:(localStorage.getItem("loginData")&&JSON.parse(localStorage.getItem("loginData")))||{}
    },
    mutations:{
        setUserInfo(state,uInfo){
            state.userInfo=uInfo
        }
    }
}
```

#  退出操作

```
 <el-button @click="loginOut">退出</el-button>
  
const loginOut=()=>{
            localStorage.removeItem("loginData")
            store.commit('setUserInfo', {});
            router.push({
                path:"/login"
            })

 }
```

#   Axios 封装  

## util/service.js

```
import axios from "axios"
import { ElLoading } from 'element-plus'
import { ElMessage } from 'element-plus'
import store from "../store/index.js"
// 使用create创建axios实例
let loadingObj = null
const Service = axios.create({
    timeout:8000,
    baseURL:"http://127.0.0.1:8888/api/private/v1/",
    headers:{
        "Content-type":"application/json;charset=utf-8",
        "Authorization":store.state.uInfo.userInfo.token
    }
})
// 请求拦截-增加loading,对请求做统一处理
Service.interceptors.request.use(config=>{
    loadingObj=ElLoading.service({
        lock: true,
        text: 'Loading',
        background: 'rgba(0, 0, 0, 0.7)',
    })
    return config
})
// 响应拦截-对返回值做统一处理
Service.interceptors.response.use(response=>{
    loadingObj.close()
    const data = response.data
    if(data.meta.status!=200 && data.meta.status!=201){
        ElMessage.error(data.meta.msg||"服务器出错")
        // 请求出错 
        return data
    }
    return data

},error=>{
    loadingObj.close()
    ElMessage({
        message:"服务器错误",
        type:"error",
        duration:2000
    })
})

// post请求
export const post=config=>{
    return Service({
        ...config,
        method:"post",
        data:config.data
    })
}
// get请求
export const get=config=>{
    return Service({
        ...config,
        method:"get",
        params:config.data
    })
}
// put请求
export const put=config=>{
    return Service({
        ...config,
        method:"put",
        data:config.data
    })
}// delete请求
export const del=config=>{
    return Service({
        ...config,
        method:"delete" 
    })
}
```

##   util/request.js

```
import {post,get,put,del} from "./service"

export const loginApi=data=>{ 
    return post({
        url:"/login",
        data
    })
}
// 获取用户列表
export const userListApi=data=>{ 
    return get({
        url:"/users",
        data
    })
} 

// 新增用户列表
export const userAddApi=data=>{ 
    return post({
        url:"/users",
        data
    })
} 
//  用户列表更改状态
export const userChangeStateApi=data=>{ 
    return put({
        url:`users/${data.id}/state/${data.mg_state}`,
        data
    })
} 
// 更改用户信息
export const userChangeInfoApi=data=>{ 
    return put({
        url:`users/${data.id}`,
        data
    })
} 
// 删除用户
export const userDeleteApi=data=>{ 
    return del({
        url:`users/${data.id}`
    })
} 
// 获取角色
export const getRolesApi=data=>{ 
    return get({
        url:`roles`,
        data
    })
} 
// 新建角色
export const addRolesApi=data=>{ 
    return post({
        url:`roles`,
        data
    })
} 
// 编辑角色
export const editRolesApi=data=>{ 
    return put({
        url:`roles/${data.id}`,
        data
    })
} 

export const rolesDeleteApi=data=>{ 
    return del({
        url:`roles/${data.id}`
    })
}

export const goodsListApi=data=>{ 
    return get({
        url:`goods`,
        data
    })
} 
```

在应用到的页面上直接采用此方法

```
  login.vue
  
  const handleLogin=()=>{
            // 请求后台接口
            // 默认用户：admin/123456
            loginApi(data.loginData).then(res=>{
                if(res.data){
                    store.commit('setUserInfo', res.data);
                    localStorage.setItem("loginData",JSON.stringify(res.data))
                    // 跳转/user
                    router.push({
                        path:"/"
                    })
                }
            })
        }
```





#    表单的正则表达式

```
<!-- 编辑弹窗 -->
        <el-dialog v-model="dialogFormEVisible" title="编辑用户">
           <el-form 
            ref="userForm"
            :model="formData2"
            :rules="rules2"
           > 
               <el-form-item label="邮箱" prop="email">
                   <el-input v-model="formData2.email" placeholder="请输入用户邮箱" />
               </el-form-item>
               <el-form-item label="手机号" prop="mobile">
                   <el-input v-model="formData2.mobile" placeholder="请输入用户手机号" />
               </el-form-item>
           </el-form>
           <template #footer>
               <div class="flex">
                   <el-button>取消</el-button>
                   <el-button type="primary" @click="submitForm(userForm)" >确定</el-button>
               </div>
           </template>
        </el-dialog>
```

```
import { toRefs,reactive,ref } from 'vue'
export default {
   setup() {
   formData2:{ 
                id:"",
                email:"",
                mobile:"",
            },
   }
}
```



```
rules:{
  username:[
            {required:true,message:"此项为必填",trigger:"blur"}
          ],
                
password:[
            {required:true,message:"此项为必填",trigger:"blur"}
          ],
email:[
            {required:false,
             pattern:/^[A-Za-z0-9\u4e00-\u9fa5]+@[a-zA-Z0-9_-]+(\.[a-zA-Z0-9_-]+)+$/,
             message:"请填写正确邮箱",trigger:"blur"}
       ], 
mobile:[
             {required:false,
              pattern:/^[1][3,4,5,6,7,8][0-9]{9}$/,
               message:"请填写正确手机号",trigger:"blur"}
       ]
}
```

#    获取用户列表

```
reques.js
// 获取用户列表
export const userListApi=data=>{ 
    return get({
        url:"/users",
        data
    })
} 

页面
  <!-- 表格 -->
  <el-table :data="userList" style="width: 100%">
                <el-table-column prop="username" label="姓名" width="180" />
                <el-table-column prop="mg_state" label="状态" > 
                    <template #default="scope">
                        <el-switch v-model="scope.row.mg_state" @change="switchChange(scope.row)" />
                    </template>
                </el-table-column>
                <el-table-column   label="操作" > 
                    <template #default="scope">
                        <el-button type="primary" @click="editRow(scope.row)">编辑</el-button>
                        <el-button type="danger" @click="deleteRow(scope.row)">删除</el-button>
                    </template>
                </el-table-column>
 </el-table>
            
userList:[],
const searchList=()=>{
            userListApi(data.searchParams).then(res=>{
                if(res.data){
                    // 
                    console.log("用户数据",res)
                    data.userList=res.data.users
                    data.total=res.data.total
                }
            })
 }
 
     
 // 方法初始化
  searchList()   
  return{
     ... toRefs(data),
     searchList,
```

#    搜索用户

```
request.js
// 获取用户列表
export const userListApi = data => {
  return get({
    url: '/users',
    data
  })
}

页面
<el-input v-model="searchParams.query" placeholder="搜索关键字" class="input-with-select">
        <template #append>
          <el-button @click="searchList"><el-icon><Search /></el-icon></el-button>
        </template>
</el-input>

 const searchList = () => {
      userListApi(data.searchParams).then(res => {
        if (res.data) {
          //
          console.log('用户数据', res)
          data.userList = res.data.users
          data.total = res.data.total
        }
      })
    }
```



#   添加用户

```
写借口的时候 先找request。j s--------get post
需要的页面上 import 引进对应的API from request
request.js
// 新增用户列表
export const userAddApi=data=>{ 
    return post({
        url:"/users",
        data
    })
} 
```

```
 // 新增提交
       const addUser=()=>{
            data.dialogFormVisible=true
        }
       
        const submitForm=(formEl)=>{
            // validate
            formEl.validate(res=>{
                if(!res){
                    return
                }
                // 表单通过请求接口
                userAddApi(data.formData).then(res=>{
                    if(res.data){ 
                        // 隐藏弹窗
                        data.dialogFormVisible=false
                        // 清空form
                        data.formData={
                            username:"",
                            password:"",
                            email:"",
                            mobile:"",
                        }
                        // 重新更新列表 
                        searchList()
                    }
                })
            })
        }
        
         // 方法初始化
        searchList()
        const userForm2=ref()
        return{
            ... toRefs(data),
            searchList,
            addUser,
            submitForm,
            submitEForm,
            userForm,
            userForm2,
          
```

#  用户状态修改

```
reque.js

//  用户列表更改状态
export const userChangeStateApi=data=>{ 
    return put({
        url:`users/${data.id}/state/${data.mg_state}`,
        data
    })
}

import {userChangeStateApi} from "@/util/request.js"
// 状态更改
        const switchChange=row=>{
            console.log("操作的那条数据",row)
            userChangeStateApi(row).then(res=>{
                if(res.data){ 
                    searchList()
                }
            })
        }
  //方法初始化
        return{
            ... toRefs(data),
            switchChange,
        }
```

#   编辑/删除页面

```
request.js

// 更改用户信息
export const userChangeInfoApi=data=>{ 
    return put({
        url:`users/${data.id}`,
        data
    })
} 
// 删除用户
export const userDeleteApi=data=>{ 
    return del({
        url:`users/${data.id}`
    })
} 

页面
<el-table-column   label="操作" > 
       <template #default="scope">
               <el-button type="primary" @click="editRow(scope.row)">编辑</el-button>
               <el-button type="danger" @click="deleteRow(scope.row)">删除</el-button>
        </template>
</el-table-column>
import {userListApi,userAddApi,userChangeStateApi,userChangeInfoApi,userDeleteApi} from "@/util/request.js"

 // 修改提交
    const submitEForm = formEl => {
      formEl.validate(res => {
        if (!res) {
          return
        }
        // 提交修改
        userChangeInfoApi(data.formData2).then(res => {
          if (res.data) {
            data.dialogFormEVisible = false
            searchList()
          }
        })
      })
    }
    
  // 数据编辑
        const editRow=row=>{
            console.log("编辑的那条数据",row)
            const {email,mobile,id}=row
            // 展示编辑表单
             data.dialogFormEVisible=true;
             data.formData2.email=email
             data.formData2.mobile =mobile
             data.formData2.id =id
        }
        // 删除数据
        const deleteRow=row=>{
            console.log("删除的那条数据",row)
            userDeleteApi(row).then(res=>{
                searchList()
            }) 
        }
```

#  分页

##    vue3

```
 <!-- 分页 vue3-->
    <el-pagination
                v-model:currentPage="searchParams.pagenum"
                v-model:page-size="searchParams.pagesize"
                :page-sizes="[2,5,10,20]"
                :small="small"  
                layout="total, sizes, prev, pager, next, jumper"
                :total="total"
                @size-change="searchList"
                @current-change="searchList"
     />
     
         searchParams:{
                query:"",
                pagesize:5,
                pagenum:1
            },
    total:0,
    
    const searchList=()=>{
            userListApi(data.searchParams).then(res=>{
                if(res.data){
                    // 
                    console.log("用户数据",res)
                    data.userList=res.data.users
                    data.total=res.data.total
                }
            })
        
        
```

## vue2

```
 <el-pagination 
      @size-change="handleSizeChange" 
      @current-change="handleCurrentChange" 
      :current-page="queryInfo.pagenum" 
      :page-sizes="[1, 2, 5, 10]" 
      :page-size="queryInfo.pagesize" 
      layout="total, sizes, prev, pager, next, jumper" 
      :total="total">
</el-pagination>

  // 获取用户列表的参数对象
      queryInfo: {
        query: '',
        // 当前的页数
        pagenum: 1,
        // 当前每页显示多少条数据
        pagesize: 2
      },
      total: 0,

// 监听 pagesize 改变的事件
    handleSizeChange(newSize) {
      // console.log(newSize)
      this.queryInfo.pagesize = newSize
      this.getUserList()
    },
    // 监听 页码值 改变的事件
    handleCurrentChange(newPage) {
      console.log(newPage)
      this.queryInfo.pagenum = newPage
      this.getUserList()
    },
```

#   商品状态

##   vue3

```
表格
 <el-table :data="goodsList" style="width: 100%">
       <el-table-column prop="goods_state" label="商品状态" > 
                    <template #default="scope"> 
                        <p>{{switchState(scope.row.goods_state)}}</p>
                    </template>
       </el-table-column>            
</el-table>

 const switchState=state=>{
            switch (state) {
                case 0:
                    return "未通过"
                    break; 
                case 1:
                    return "审核中"
                    
                    break; 
                case 2:
                    return "已审核"
                    
                    break; 
            }
  }
  
  // 方法初始化
searchList() 
  return{
     switchState
        }
```

##   vue2

```
<el-table-column label="商品状态" prop="goods_state" width="80px">
    <template v-slot="scope">
            <el-tag v-if="scope.row.goods_state === '0'">通过</el-tag>
            <el-tag type="success" v-else-if="scope.row.goods_state === '1'"
              >审核中</el-tag
            >
            <el-tag type="success" v-else>已审核</el-tag>
     </template>
</el-table-column>
```



![截屏2023-02-16 14.59.59](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-02-16%2014.59.59.png)





#   22222222222222222222222222222

#      1. Vuex的基本使用

1. 安装vuex依赖包
   npm install vuex --save

2. 导入vuex包 在main.js 使用

   ```
   import Vue from "vue";
   import App from './App.vue'
   import store from './store'
   
   Vue.config.productionTip = false
   Vue.phototype.$store=store
   new Vue({
       store,
       render: h => h(App)
   }).$mount('#app')
   
   ```

3. 创建store对象 store.js 

   ```
   import Vue from 'vue'
   import Vuex, {mapGetters, mapMutations, mapState} from 'vuex'
   
   Vue.use(Vuex) //vuex的插件机制
   
   const store = new Vuex.Store({
       // state中存放的就是全局共享的数据
       state: {count: 0}
   })
   ```

   

4. 将store对象挂载到vue实例中

   ~~~vue
   new Vue({
       el: '#app',
       render: h => h(app),
       router,
       // 将创建的共享数据对象，挂载到Vue实例中
       // 所有的组件，就可以直接从store中获取全局的数据了
       store
   })
   ~~~

   

   #     2.Vuex的核心概念

   Vuex中的主要核心概念如下：

- State

- Mutation

- Action

- Getter

  ##  2.1 State

  在Vuex中，State提供唯一的公共数据源，所有共享的数据都要统一放到Store的State中进行存储，这里的Store相当于一个用于存储数据的公共容器。

  ```
  const store = new Vue.Store({
      state: {
          count: 0
      }
       ...
   })
   
   export default new Vuex.Store({
      state: {
          count: 0
      }
   })
  ```

  **1.组件访问State中数据的第一种方式**

```
this.$store.state.全局数据名称
```

去过是在html元素组件之间调用，则可以省略this，即：

```
<h3>当前最新的count值：{{$store.state.count}}</h3>
```

​       **2.组件访问State中数据的第二种方式**

通过mapState辅助函数方式，实现组件访问State中数据的第二种方式

```
 // 1. 从vuex中按需导入mapState函数
import { mapState } from 'vuex'
```

通过刚才导入的mapState函数，将当前组件需要的全局数据，映射为当前的computed计算属性：

```
 //将全局数据映射为当前组件的计算属性
computed: {
    // ...表示展开映射，意思就是将全局属性映射为当前组件的计算属性
    ...mapState(['count'])
}
```

直接在调用获取组件属性

```
<span>{{count}}</span>
```

## 2.2 Mutation

> Vuex中的Mutation是用于变更Store中的数据。

在Vuex中，只能通过mutation变更Store数据，不可以直接操作Store中的数据。虽然通过mutation的方式来操作数据，虽然繁琐了一点，但是却可以集中监控所有数据的变化。

例如需要让全局数据自增加1，则可以通过如下的方式在Mutation中定义

```
const store = new Vuex.Store({
    state: {
        count: 0
    },
    mutations: {
        add(state) {
            //变更状态
            state.count++;
        }
    }
})
```

定义完mutation之后，下面就来介绍下Vuex的触发方式

 **触发mutation方式一**

> 通过$store.commit()函数来触发mutation。

```
methods: {
    handle1 () {
        // 触发mutations的第一种方式
        this.$store.commit('add')
    }
}

//接着就可以通过@click方法来调用handle1，从而来触发mutation函数。
//另外，可以在触发mutation函数时，传入参数

const store = new Vuex.Store({
    state: {
        count: 0
    },
    mutations: {
        add(state) {
            //变更状态
            state.count++;
        },
        addN(state, n) {
            state.count += n;
        }
    }
})
//然后定义handler2
methods: {
    handler2: {
        this.$store.commit('addN', 5);
    }
}
```

**触发mutation方式二**

通过导入mapMutations辅助函数来触发mutations。

```
// 1. 从vuex中按需导入mapMutations函数
import { mapMutations } from 'vuex'

...

// 2. 将制定的mutations函数映射为当前组件的methods函数
methods: {
    // 将add和addN方法映射为methods中的函数，拱当前组件使用。
    ...mapMutations({'add', 'addN'}),
    handleAdd() {
        this.add();
    },
    handleAddN(n) {
        this.addN(n);
    }
    // 或者直接在标签元素中直接@click=add(n)
}
```

**对于mutations来说，只能够实现同步操作，不可以执行异步操作的。**

## 2.3 Action

从vuex官网中可以了解到，Action类似于mutation，不同之处在于：

> Action 提交的是 mutation，而不是直接变更状态。
> Action 可以包含任意异步操作。
> 可以得出一个结论就是，如果通过异步操作变更数据，必须通过Action，而不能使用Mutation，但是在Action中还是要通过触发Mutation的方式间接变更数据。

```vue
    //定义Actions
const store = new Vuex.Store({
    state: {
        count: 0
    },
    mutations: {
        add(state) {
            //变更状态
            state.count++;
        },
        addN(state, n) {
            state.count += n;
        }
    },
    actions: {
        // 通过context去调用mutation
        addAsync(context) {
            setTimeout(() => {
             // 在action中，不能直接更改 state中的数据
             // 必须通过 context.commit() 触发某个mutation才行
              context.commit('add')
            }, 1000)
        },
        // 调用Actions是也可以传入参数
        addNAsync(context, n) {
            setTimeout(() => {
                context.commit('addN', n);
            }, 1000);
        }
    }
})
```

> 需要再次强调的是，只有通过mutation中定义的函数，才有权利去修改state中的数据，因此actions最终还是要调用mutation。

**触发Actions的第一种方式**

```
methods: {
    handleAddAsync() {
        this.$store.dispatch('addAsync');
    },
    handleAddNAsync() {
        this.$store.dispatch('addNAsync', n);
    }
}
```

**触发Actions的第二种方式**

可以通过mapActions辅助函数的方式来触发Actions。

```
// 1. 从vuex中按需导入mapActions函数
import { mapActions } from 'vuex'

...

// 2. 将指定的actions函数，映射为当前组件的methos函数
methods: {
    ...mapActions(['addAsync', 'addNAsync'),
    handleAddAsync() {
        this.addAsync();
    },
    handleAddNAsync(n) {
        this.addNAsync(n);
    }
}
```

## 2.4 Getter

在Vuex官网中，用到了派生这一词来介绍Getter，在这里可以理解为就是用于对Store中的数据进行加工处理，形成新的数据，类似Vue的计算属性。Getter的数据是基于Store中的数据的，所以当Store中数据发生变化时，Getter中的数据也会随之变化。

```
定义Getter

例如state中存有todos计划项，其对象有一个done状态表示完成与否。

const store = new Vuex.Store({
  state: {
    todos: [
      { id: 1, text: '...', done: true },
      { id: 2, text: '...', done: false }
    ]
  },
  
  加减法里的getters
  getters: {
        showNum(state){
            return '当前最新的数据量是 【'+state.count+'】'
        }
    },
    
    
  getters: {
    // 这里通过getters定义的doneTodos方法来过滤已完成的todo项
    doneTodos: state => {
      return state.todos.filter(todo => todo.done);
    },
    // 这里还可以通过传入getters对象来获取其他方法
    doneTodosCount: (state, getters) => {
        return getters.doneTools.length;
    },
    // 传入参数
    getTodoById: (state) => (id) => {
        return state.todos.find(todo => todo.id == id);
    }
  }
})
```

**触发Getter定义函数的第一种方法**

```
this.$store.getters.doneTodos // -> [{id: 1, text: '...', done: true}]
this.$store.getters.doneTodosCount // -> 1
```

**触发Getter定义函数的第二种方法**

通过mapGetters来触发Getter中定义的函数

```
// 1. 导入mapGetters辅助函数
import { mapGetters } from 'vuex'

...

// 2. 将制定的Getters函数映射为当前组件的函数
computed: {
    ...mapGetters(['doneTodos', 'doneTodosCount']),
    handleDoneTodos() {
        this.doneTodos();
    }
}


 computed:{
     ...mapGetters(['showNum'])
 }
```

## 2.5 Module

当Store中存放了非常多非常大的共享数据对象时，应用会变的非常的复杂，Store对象也会非常臃肿，所以Vuex提供了一个Module模块来分隔Store。通过对Vuex中的Store分隔，分隔成一个一个的Module模块，每个Module模块都拥有自己的state、mutation、actions和getters。

```
const moduleA = {
  state: () => ({ ... }),
  mutations: { ... },
  actions: { ... },
  getters: { ... }
}

const moduleB = {
  state: () => ({ ... }),
  mutations: { ... },
  actions: { ... }
}

const store = new Vuex.Store({
  modules: {
    a: moduleA,
    b: moduleB
  }
})

store.state.a // -> moduleA 的状态
store.state.b // -> moduleB 的状态
```

对于模块中的mutations和getters，传入的第一个参数规定为state，而actions则依旧是context参数。如下：

```
const moduleA = {
  state: {
     count: 0
  },
  mutations: {
    increment (state) {
      // 这里的 `state` 对象是模块的局部状态
      state.count++
    }
  },

  getters: {
    doubleCount (state) {
      return state.count * 2
    }
  },
  actions: {
  	// context对象其实包含了 state、commit、rootState。
  	incrementIfOddRootsum (context) {
		if ((context.state.count + context.rootState.count) % 2 === 1) {
        // 调用mutations
        commit('increment')
      }
  	}
  }
}
```

在module中通过mapState、mapGetters、mapActions和mapMutations等辅助函数来绑定要触发的函数

**第一种方式**

```
methods: {
	...mapActions([
		'some/nested/module/foo',
		'some/nested/module/bar'
	])
}
```

在vuex中，可以为导入的state、getters、actions以及mutations命名别名，，这样可以方便调用

```
methods: {
	...mapActions([
		'foo': 'some/nested/module/foo',
		'bar': 'some/nested/module/bar'
	])
}
```

**第二种方式**
对于这种情况，你可以将模块的空间名称字符串作为第一个参数传递给上述函数，这样所有绑定都会自动将该模块作为上下文。于是上面的例子可以简化为：

```
methods: {
  ...mapActions('some/nested/module', [
    'foo', // -> this.foo()
    'bar' // -> this.bar()
  ])
}
```

**第三种方式**
可以通过使用 createNamespacedHelpers 创建基于某个命名空间辅助函数。它返回一个对象，对象里有新的绑定在给定命名空间值上的组件绑定辅助函数：

```
import { createNamespacedHelpers } from 'vuex'

const { mapState, mapActions } = createNamespacedHelpers('some/nested/module')

export default {
  methods: {
    // 在 `some/nested/module` 中查找
    ...mapActions([
      'foo',
      'bar'
    ])
  }
}
```

# 封装vuex在项目中的使用（公司）

```
gettings.js
接下来定义状态state各个字段的获取方法。
export default {
    opened: (state) => state.app.slider.opened,
    token: (state) => state.app.token,
    uname: (state) => state.app.uname,
    menuList: (state) => state.app.menuList,
    permissionList: (state) => state.app.permissionList,
};


import {
    TOGGLE_SLIDER,
    SET_TOKEN,
    SET_UNAME,
    SET_MENU_LIST,
    SET_PERMISSION_LIST,
    SET_ACTIVE,
    SET_MENU,
    SET_TASK_ID,
    SET_FORMDATA,
    SET_FILE
} from "./type.js";
export default {
    namespaced: true,
    state: {
        slider: {
            opened:JSON.parse(sessionStorage.getItem("opened")),
        },
        token: sessionStorage.getItem("token") || "",
        menuList: null,
        permissionList: [],
        uname: sessionStorage.getItem("uname") || "",
        componentsActive: 'serviceMain',
        userId: sessionStorage.getItem("userId") || "",
        sideMenuList: [
            {
                name: "服务内容",
                img: "",
                route: "serviceMain",
                router: 'service-subscriptions'
            },
            {
                name: "任务创建",
                img: "",
                route: "taskMain",
                router: 'service-subscriptions'
            }
        ],
        taskId: sessionStorage.getItem("taskId") || "",
        fileListObj: {},
        firstFormData: {
            name: "",
            description: "",
            hasInsar: false,
            hasAi: false,
        },
        secondFormData: {
            taskId: "",
            satelliteName: "",
            monitorStartTime: "",
            monitorEndTime: "",
            demResolution: "",
            hasAnomalyRegion: false,
            hasDeformationRate: false,
            hasAccumulatedDeformation: false,
            hasDiagram: false,
        },
        thirdFormData: {
            taskId: "",
            hasTargetGeohazard: false,
            hasTargetHazardBody: false,
            cognitionModel: 0,
            satelliteName: "",
            preStartTime: "",
            preEndTime: "",
            postStartTime: "",
            postEndTime: "",
            cloudCover: 0,
        },
        finalFormData: {
            taskId: "",
            name: "",
            department: "",
            phone: "",
            email: "",
        },
        dataDetail: null,
        tableName: null
    },
    
    定义一些修改state的操作方法。
    mutations: {
        [TOGGLE_SLIDER](state) {
            state.slider.opened = !state.slider.opened;
            sessionStorage.setItem(
                "opened",
                JSON.stringify(state.slider.opened)
            );
        },
        [SET_TOKEN](state, token) {
            state.token = token;
            sessionStorage.setItem("token", state.token);
        },
        [SET_UNAME](state, uname) {
            state.uname = uname;
            sessionStorage.setItem("uname", state.uname);
        },
        [SET_MENU_LIST](state, menuList) {
            state.menuList = menuList;
        },
        [SET_PERMISSION_LIST](state, permissionList) {
            state.permissionList = permissionList;
        },
        [SET_ACTIVE](state, val) {
            state.componentsActive = val;
        },
        [SET_MENU](state, val) {
            state.sideMenuList = val;
        },
        [SET_FILE](state, val) {
            state.fileListObj = val;
        },
        [SET_TASK_ID](state, val) {
            state.taskId = val;
            sessionStorage.setItem(
                "taskId",
                JSON.stringify(val)
            );
        },
        setUserId(state, val) {
            state.userId = val;
            sessionStorage.setItem(
                "userId",
                JSON.stringify(val)
            );
        },
        setDataDetail(state, val) {
            state.dataDetail = val
        },
        setTableName(state, val) {
            state.tableName = val
        },
        [SET_FORMDATA](state, val) {
            if (val.index == 0) {
                state.firstFormData = val.data;
            } else if (val.index == 1) {
                state.secondFormData = val.data;
            } else if (val.index == 2) {
                state.thirdFormData = val.data;
            } else if (val.index == 3) {
                state.finalFormData = val.data;
            }
        },
    },
正常情况下，我们一个操作，可能会同时修改多个state中的属性，那么就意味着一个操作执行多个mutation中的方法。所以定义一个action将多个方法封装成一个函数。
    actions: {
  
        [TOGGLE_SLIDER]({ commit }) {
            commit(TOGGLE_SLIDER);
        },
        [SET_TOKEN]({ commit }, token) {
            commit(SET_TOKEN, token);
        },
        [SET_UNAME]({ commit }, uname) {
            commit(SET_UNAME, uname);
        },
        [SET_MENU_LIST]({ commit }, menuList) {
            commit(SET_MENU_LIST, menuList);
        },
        [SET_ACTIVE]({ commit }, val) {
            commit(SET_ACTIVE, val);
        },
        [SET_MENU]({ commit }, val) {
            commit(SET_MENU, val);
        },
        [SET_TASK_ID]({ commit }, val) {
            commit(SET_TASK_ID, val);
        },
        [SET_FORMDATA]({ commit }, val) {
            commit(SET_FORMDATA, val);
        },
        [SET_FILE]({ commit }, val) {
            commit(SET_FILE, val);
        },
        setUserId({ commit }, val) {
            commit('setUserId', val);
        },
        setDataDetail({ commit }, val) {
            commit('setDataDetail', val);
        },
        setTableName({ commit }, val) {
            commit('setTableName', val);
        },
        [SET_PERMISSION_LIST]({ commit }, menuList) {
            let allMenus = XE.filterTree(menuList, (item) => item.type == 1);
            let permissionList = [];
            allMenus.forEach((item) => {
                if (item.children && item.children.length > 0) {
                    item.children.forEach((menu) => {
                        permissionList.push(
                            `${item.url}/${item.id}/${menu.menu}`
                        );
                    });
                }
            });
            commit(SET_PERMISSION_LIST, permissionList);
        },
    },
};

```

#   项目中的实例（百度）

在组合API中使用vuex，就需要在setup钩子函数中进行手动调用。

模版中

```
<template>
  <div class="player">
    <div
      class="normal-player"
      v-show="fullScreen"
    >
      <!--  使用v-if避免currentSong没有值的时候被渲染 -->
      <!-- 使用template避免产生多余的dom层 -->
      <template v-if="currentSong">
        <div class="background">
          <img :src="currentSong.pic">
        </div>
        <div class="top">
          <div
            class="back"
            @click="goBack"
          >
            <i class="icon-back"></i>
          </div>
          <h1 class="title">{{currentSong.name}}</h1>
        </div>
      </template>
    </div>
    <audio
      ref="audioRef"
    ></audio>
  </div>
</template>
```

JS

```
// vuex提供useStore专门从vuex中拿数据的方法
import { useStore } from 'vuex'
// 如果需要在组合api中使用计算监听 那么就要单独引入
import { computed, watch, ref } from 'vue'

export default {
  // 对于复杂的组件 将其中的各个逻辑进行拆分成不同文件
  setup() {
    // 获取的时候要先定义一个ref对象
    const audioRef = ref(null)

    // 这个store可以理解为createStore中返回的实例，其中含有state、getters等属性
    const store = useStore()
    // setup中的响应式需要自己去处理，所以要使用computed（）这个API
    // 让state.fullScreen变成一个响应式的
    // 记得必须要返回转化的计算属性
    const fullScreen = computed(() => store.state.fullScreen)
    const currentSong = computed(() => store.getters.currentSong)

    // 监听currentSong的属性变化，如果变化了就重新给audio赋值
    watch(currentSong, (newSong) => {
      if (!newSong.id || !newSong.url) {
        return
      }
      // 通过audioRef.value获取到audio的DOM元素
      const audioEl = audioRef.value
      audioEl.src = newSong.url
      audioEl.play()
    })

    // 通过store.commit方法，提交一个修改操作
    function goBack() {
      store.commit('setFullScreen', false)
    }
    
    // 只有返回出去 才能被模板获取到
    return {
      audioRef,
      fullScreen,
      currentSong,
      // 返回方法，模板中可以使用goback()
      goBack
    }
  }
}
```

1. 获取vuex中的实例

```
// vuex提供useStore专门从vuex中拿数据的方法
import { useStore } from 'vuex'

setup(){
  // 这个store可以理解为createStore中返回的实例，其中含有state、getters等属性
  const store = useStore()
}
```

2. 获取vuex中的state和getters

```
// setup中的响应式需要自己去处理，所以要使用computed（）这个API
// 让state.fullScreen变成一个响应式的
// 记得必须要返回转化的计算属性
import { computed } from 'vue'
// 直接返回 state中字段的属性
const fullScreen = computed(() => store.state.fullScreen)
// 执行vuex中的getters方法
const currentSong = computed(() => store.getters.currentSong)

// 只有返回出去 才能被模板获取到
return {
   fullScreen,
   currentSong
}
```

3. 执行mutations

```
setup() {
    // 通过store.commit方法，提交一个修改操作
    function goBack() {
      store.commit('setFullScreen', false)
    }
    // 只有返回出去 才能被模板获取到
    return {
      // 返回方法，模板中可以使用goback()
      goBack
    }
}

通过store.commit执行mutations中定义的方法，并对其传参。
```

4. 使用watch监听并获取元素DOM

```
import { watch, ref } from 'vue'

setup() {
    // 获取的时候要先定义一个ref对象
    // 注意 也要在模板元素上加 <audio ref="audioRef">
    const audioRef = ref(null)
    // 监听currentSong的值变化，如果变化了就重新给audio元素赋值
    watch(currentSong, (newSong) => {
      if (!newSong.id || !newSong.url) {
        return
      }
      // 通过audioRef.value获取到audio的DOM元素 固定套路
      const audioEl = audioRef.value
      audioEl.src = newSong.url
      audioEl.play()
    })
}
```

5. 在setup中获取计算属性的值

```
 <i :class="playIcon"></i>
 
 import { computed } from 'vue'
 import { useStore } from 'vuex'

 setup() {
    const store = useStore()
    // 从vuex中取出state.playing字段
    const playing = computed(() => store.state.playing)
    // 因为playing是一个计算属性，所以在js中要通过playing.value获取它的值
    const playIcon = computed(() => {
      return playing.value ? 'icon-pause' : 'icon-play'
    })
    
    return {
        playIcon
    }
 }

这里有个疑问：为什么需要用playing.value进行判断呢？之前判断player是否显示的fullscreen都是直接用的。

答：因为 playing 是一个计算属性，在 JS 中需要通过 .value 获取它的值。
```

6. 在setup中使用actions

```
从不同文件角度进行分析：

// 在player.vue
<i @click="changeMode"></i>

import useMode from './use-mode'
setup() {
    const { changeMode } = useMode()
    return {
        // 将方法返回给模板
        changeMode
    }
}
```

```
// 在use-mode.js文件
import { useStore } from 'vuex'
import { computed } from 'vue'

export default function useMode() {
  const store = useStore()
  const playMode = computed(() => store.state.playMode)

  function changeMode () {
    // 这样取值结果值就在0,1,2之间
    // 在js中获取计算属性的值要使用.value
    const mode = (playMode.value + 1) % 3
    // 执行一个actions-changeMode，传递参数mode
    store.dispatch('changeMode', mode)
  }

  // 注意 这里返回的必须是一个对象！这样接收的时候使用解构赋值接收
  return {
    changeMode
  }
}
```

这里执行vuex中的actions中封装的方法，要使用：

```
const store = useStore()
store.dispatch('actions方法名', 参数);
```

actions中封装的changeMoe方法(actions就是封装了多个Mutations修改方法的函数)：

```
// getters也可以被解构 commit是可以提交mutation的方法, state是定义的数据字段状态
export function changeMode({ commit, state, getters }, mode) {
  // 先从getters中拿到当前正在播放歌曲（对象）的Id
  const currentId = getters.currentSong.id
  
  // 设置提交Mutation，通过mutation方法修改state中的属性
  commit('setPlaylist', state.sequenceList)

  // 在修改后的playlist中找到这个ID对应的这首歌，找到它的索引之后再提交commit
  const index = state.playlist.findIndex((song) => {
    return song.id === currentId
  })

  // 修改当前正在播放的歌曲的索引
  commit('setCurrentIndex', index)
  // 修改播放模式
  commit('setPlayMode', mode)
}
```



# 总结

> Vuex主要用于管理Vue组件中共享的数据。
> Vuex中有state、mutation、action、getter等核心概念。
> 获取state可以通过this.$store.state.xx或者是通过定义mapState来获取。
> 修改state中的变量需要通过mutation函数实现，而mutation的触发由两种方式，一种是通过this.$store.commit()函数，另外一种就是通过mapMutations来实现。
> mutation只能用于修改数据，而Actions可以实现异步操作。
> 通过Actions的异步操作+mutation的修改数据，可以实现异步修改数据。调用Actions有两种方式，第一种是通过this.$store.dispatch来调用，另外一种方式是通过mapActions来调用。
> Getters函数用于对Store中数据进行加工，不会修改原本Store中的数据；Getters中的数据会受Store中数据进行影响。

#    createstore

```
import { createStore } from 'vuex'

const store = createStore({ ...options })
```

```
import { createStore } from "vuex";
import getters from "./getters";
export default createStore({
    getters,
    modules,
});
```

#   useStore

```
useStore<S = any>(injectKey?: InjectionKey<Store<S>> | string): Store<S>;
```

在 `setup` 钩子函数中调用该方法可以获取注入的 store。当使用组合式 API 时，可以通过调用该方法检索 store。

```
import { useStore } from 'vuex'

export default {
  setup () {
    const store = useStore()
  }
}
```

首先，使用 Vue 的 `InjectionKey` 接口声明一个 injection key。

```
// store.ts
import { InjectionKey } from 'vue'
import { createStore, Store } from 'vuex'

export interface State {
  count: number
}

export const key: InjectionKey<Store<State>> = Symbol()

export const store = createStore<State>({
  state: {
    count: 0
  }
})
```

然后，将定义好的 key 作为第二个参数传递给 `app.use` 方法。

```
// main.ts
import { createApp } from 'vue'
import { store, key } from './store'

const app = createApp({ ... })

app.use(store, key)

app.mount('#app')
```

最后，将 key 传递给 `useStore` 方法以获取指定类型的 store 实例。

```
// 在 vue 组件内
import { useStore } from 'vuex'
import { key } from './store'

export default {
  setup () {
    const store = useStore(key)

    store.state.count // 类型为 number
  }
}
```

#   vue-provide

##   提供

用`provide`和解决道具钻孔问题`inject`。父组件可以充当其所有后代的**依赖提供者。**后代树中的任何组件，无论它有多深，都可以**注入**其父链中组件提供的依赖项。

![截屏2023-02-16 17.02.35](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-02-16%2017.02.35.png)

要向组件的后代提供数据，请使用以下[`provide()`](https://vuejs.org/api/composition-api-dependency-injection.html#provide)函数：

```
<script setup>
import { provide } from 'vue'

provide(/* key */ 'message', /* value */ 'hello!')
</script>
```

如果不使用`<script setup>`，请确保`provide()`在内部同步调用`setup()`：

```
import { provide } from 'vue'

export default {
  setup() {
    provide(/* key */ 'message', /* value */ 'hello!')
  }
}
```

该`provide()`函数接受两个参数。第一个参数称为**注入密钥**，可以是字符串或`Symbol`. 后代组件使用注入键来查找要注入的所需值。单个组件可以`provide()`使用不同的注入键多次调用以提供不同的值。



第二个参数是提供的值。该值可以是任何类型，包括反应状态，例如 refs：

```
import { ref, provide } from 'vue'

const count = ref(0)
provide('key', count)

```

##  应用级提供

除了在组件中提供数据，我们还可以在应用层提供：

```
import { createApp } from 'vue'

const app = createApp({})

app.provide(/* key */ 'message', /* value */ 'hello!')
```

##  注入

要注入祖先组件提供的数据，请使用以下[`inject()`](https://vuejs.org/api/composition-api-dependency-injection.html#inject)函数：

```
<script setup>
import { inject } from 'vue'

const message = inject('message')
</script>
```

如果不使用`<script setup>`，`inject()`则只能在内部同步调用`setup()`：

```
import { inject } from 'vue'

export default {
  setup() {
    const message = inject('message')
    return { message }
  }
}
```

###    注入默认值

默认情况下，inject假定注入的密钥在父链中的某处提供。在未提供密钥的情况下，将出现运行时警告。

如果我们想让注入的属性与可选提供者一起工作，我们需要声明一个默认值，类似于 props：

```
// `value` will be "default value"
// if no data matching "message" was provided
const value = inject('message', 'default value')
```

在某些情况下，可能需要通过调用函数或实例化新类来创建默认值。为了避免在不使用可选值的情况下进行不必要的计算或副作用，我们可以使用工厂函数来创建默认值：

```
const value = inject('key', () => new ExpensiveClass())
```

##  使用反应性

当使用反应式提供/注入值时，**建议尽可能将任何突变保留在\*提供者\***内部的反应状态。这确保了所提供的状态及其可能的变化位于同一个组件中，使将来更容易维护。

有时我们可能需要更新来自注入器组件的数据。在这种情况下，我们建议提供一个负责改变状态的函数：

```
<!-- inside provider component -->
<script setup>
import { provide, ref } from 'vue'

const location = ref('North Pole')

function updateLocation() {
  location.value = 'South Pole'
}

provide('location', {
  location,
  updateLocation
})
</script>
```

```
<!-- in injector component -->
<script setup>
import { inject } from 'vue'

const { location, updateLocation } = inject('location')
</script>

<template>
  <button @click="updateLocation">{{ location }}</button>
</template>
```

[`readonly()`](https://vuejs.org/api/reactivity-core.html#readonly)最后，如果你想确保传递的数据`provide`不会被注入器组件改变，你可以将提供的值包裹起来。

```
<script setup>
import { ref, provide, readonly } from 'vue'

const count = ref(0)
provide('read-only-count', readonly(count))
</script>
```



#    ES6 Map Set

##    Set

Set是ES6中新增的数据结构，它类似于数组，但是Set数据中的元素都是唯一的，没有重复值的;
Set构造函数参数：初始化参数的时候，参数必须是实现iterator接口的数据类型，否则会抛出异常；![截屏2023-03-03 14.34.14](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-03-03%2014.34.14.png)

```
const set = new Set([1,2,3]);
const set1 = new Set('1233');
const set2 = new Set(1);
//VM387:1 Uncaught TypeError: number 1 is not iterable (cannot read property Symbol(Symbol.iterator))
    at new Set (<anonymous>)
    at <anonymous>:1:12
```

```
// 注意：方法中的参数是元素的值，不是元素的索引
 const s = new Set();
 s.add(1).add(2).add(3); // 向 set 结构中添加值，可以链式操作
 s.delete(2)             // 删除 set 结构中的2值   
 s.has(1)                // 表示 set 结构中是否有1这个值 
 s.clear()               // 清除 set 结构中的所有值
 s.size()               // 统计 Set 中的元素个数

// 将set转化为数组
const arr = Array.from(s)

// 遍历set
let set=new Set(['red','blue','green']);
// 遍历方法1，不常用
for(let key of set.keys()){
	console.log(key);//red,blue,green
}
// 遍历方法2，不常用
for(let value of set.values()){
	console.log(value);//red,blue,green
}
// 遍历方法3，常用
s.forEach(value => console.log(value)) //red,blue,green
```

属性和方法

1. Set.prototype.add()方法

Set.prototype.add(value);
参数1 value：需要添加到set元素中的值，不能够添加重复值；
返回值：返回实例化对象Set本身；

```
var s1 = new Set([1, 2, 3]);
var s2 = s1.add(4);
console.log(s1); // Set {1, 2, 3, 4}
console.log(s1 === s2); // true
```

2. Set.prototype.has()方法

Set.prototype.has(value)；
参数1 value：必填项，测试该值是否存在Set对象中；
返回值：布尔值，false表示不存在，true表示存在；

```
var s1 = new Set([1, 2, 3, 4]);
s1.has(4); // true
```

3. Set.prototype.size

size属性将返回Set对象的元素个数；

```
// add方法可以链式调用
var mySet = new Set();
mySet.add(1).add(2).add(3);
mySet.size; // 3
```

4. Set.prototype.delete()方法

Set.prototype.delete(value)；
参数1 value：需要删除的元素；
返回值：成功删除返回true，否则返回false；

5. Set.prototype.clear()方法

clear()方法用来清空一个Set对象中的所有元素；

6. Set遍历的方法

Set.prototype.keys()方法，Set.prototype.values()方法，Set.prototype.entires()方法

```
var s1 = new Set([1, 2, 3]);
var iterator = s1.keys();
var iterator = s1.values();
var iterator = s1.entries();
console.log(iterator.next());
```

![截屏2023-03-03 13.31.29](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-03-03%2013.31.29.png)

keys和values返回的结果相同，Set中的key等于value，这也是新增时add只传一个参数的原因

应用场景

1. 数组去重

```
var arr = [1, 2, 3, undefined,undefined,null,null, NaN, 1, 2, 3, NaN],
    set = new Set(arr);
console.log([...set]); 
```

```
// 借助Array.from() 或 ...（扩展运算符）
let arrs = [1,1,3,3,4,5,6];
let s = new Set(arrs); 
// 方法1：利用 ...  
let arr1 = [...s];
// 方法二：利用 Array.from()
let arr2 =  Array.from(s)

console.log(arr1);// 1,3,4,5,6
console.log(arr2);// 1,3,4,5,6
```

![截屏2023-03-03 13.34.53](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-03-03%2013.34.53-20230303133502592.png)

2. 数组去重后的实现映射数组

set实例本身没有map，filter等数组属性

```
let set = new Set([1,2,3,4,5,6,7]);
let set2 = new Set([...set].map(value => value * 2));

let set = new Set([1,2,3]);
let set1 = new Set(Array.from(set, vlaue=>value * 2));
```

![截屏2023-03-03 13.44.54](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-03-03%2013.44.54.png)

3. 数组去重后，过滤返回新的数组

```
let set = new Set([1,2,3,4,5,6,7,1,2,3]);
let set2 = new Set([...set].filter(x => (x%2) == 0));
```

![截屏2023-03-03 13.50.30](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-03-03%2013.50.30.png)

4. 循环递归调用

```
const s1 = new Set([1])
s1.forEach(item => {s1.delete(1);s1.add(1);console.log('end')})
//会一直循环调用forEach 里面的代码 不断打印end
```

5. 数组的交集、并集和差集

```
let arr1 = [1,2,3];
let arr2 = [4,3,2];
let a=new Set(arr1);
let b=new Set(arr2);
// 并集
let union=new Set([...a, ...b]);
console.log(union);// 1,2,3,4
// 交集(借助数组的filter方法)
let intersect=new Set([...a].filter(x=>b.has(x)));
console.log(intersect);// 2,3
// 差集(借助数组的filter方法)
let difference=new Set([...a].filter(x=>!b.has(x)));
console.log(difference);//1
```



##  map

传统的对象属性键名为字符串，并能够真真正正的实现属性键 — 属性值的对应；ES6Map数据结构实现的出现，实现对象键名与键值一 一对应的关系；

![截屏2023-03-03 14.36.54](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-03-03%2014.36.54.png)

```
// map的基本操作
const map=new Map();
map.set(1,'a').set(2,'b').set(3,'c'); // 链式新增/修改值，前面是键 后面是值
map.get(1); // a 获取键对应的值 value
map.has(2); // true 判断某个key是否存在
map.delete(3); // true  删除某个key
map.clear(); // 清除map所有成员
map.size(); // 获取map中所有key的个数

// map的遍历
map.set(1,'a').set(2,'b').set(3,'c');
// 遍历全部的键
for(let key of map.keys()){
	console.log(key);//1,2,3
}
// 遍历全部的值
for(let values of map.values()){
	console.log(values);//a,b,c
}
// 遍历全部的键和值
for(let [key,value] of map.entries()){
	console.log(key,value);//1=>a,2=>b,3=>c
}
// 遍历全部的键和值
map.forEach(function(value,key){  // 注意这里的forEach是value在前，key在后
	console.log(key,value);
})
```

1. 基本用法

Map构造函数参数：必须已经部署iterator接口的数据结构；
此时构造函数参数中的每一个参数必须拥有双元的数组结构；

两种声明方式

- ```
  let map = new Map([['name', 'zhansan'], ['sex', 'male']]);
  ```

- ```
  let items = [['name', 'zhansan'], ['sex', 'male']],
  map = new Map();
  items.forEach(function([key, value]){
    map.set(key, value);
  });
  ```

2. Map遍历的方法

```
const map = new Map([['name','zhangsan'],['sex','male'],['age',20]]);
console.log(map.keys());
console.log(map.values());
console.log(map.entries());
```

![截屏2023-03-03 14.12.53](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-03-03%2014.12.53.png)

3. Map.prototype.set()

set()方法为Map对象添加或者更新一个指定键（key）和值（value）的新键值对；

```
var myMap = new Map();
// 添加元素
myMap.set("bar", "foo");
myMap.set(1, "foobar");
console.log(myMap);
// 更新元素
myMap.set("bar", 'goo');
console.log(myMap);
```

![截屏2023-03-03 14.15.14](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-03-03%2014.15.14.png)

Map.set()设置属性时，属性名相同时，后面覆盖前面的键值；

Map键名覆盖的问题： 本质上与全等的运算方式类型，只是对待NaN问题上不同

```
const map = new Map();
map.set(-0, 123);
console.log(map.get(+0)); // 123

map.set(true,1);
map.set('true',2);
console.log(map.get(true)); // 1

map.set(NaN,123);
map.set(NaN,456);
console.log(map.get(NaN)); // 456
```

4. Map.prototype.get()方法

get()方法返回某一个Map对象中的一个指定元素；
如果找不到相关的键名，则返回undefined；
注意不同的引用值数据类型作为键名，获取的数据不同；

```
// 引用地址不同的情况;
const map = new Map();
map.set([5], 555);
map.get([5]); // undefined

map.set({}, 555);
console.log(map.get({})); // undefined


// 引用地址相同的情况
var obj = {id:1};
const map = new Map();
map.set(obj, 'foo');
console.log(map.get(obj)); // 'foo'

```

应用场景

- map转化为数组

```
const map=new Map([
	[1,'one'],
	[2,'two'],
	[3,'three']
]);
// 以数组的形式 输出所有key
console.log([...map.keys()]);   // [1,2,3]
// 以数组的形式 输出所有values
console.log([...map.values()]); // one,two,three
// 以二维数组的形式  输出所有键值对
console.log([...map]);			// [1,one],[2,two],[3,three]
// 以二维数组的形式  输出所有键值对
console.log([...map.entries()]);// [1,one],[2,two],[3,three]
```

- Map 转化为对象

```
// 声明map对象
const map=new Map().set('yes',true).set('no',false);
// 处理方法
function strMapObj(strMap){
    // 创建一个新对象
	let obj=Object.create(null);
    // 遍历循环strMap对象
	for(let [key,value] of strMap){
		obj[key]=value;
	}
    // 返回生成的对象
	return obj;
}
console.log(strMapObj(map));//{yes:true,no:false}
```

- 对象转化为map

```
// 声明map对象
const map=new Map().set('yes',true).set('no',false);
// 处理方法
function objToMap(obj){
	let map=new Map();
    // Object.keys() 返回
	for(let key of Object.keys(obj)){
		map.set(key,obj[key]);
	}
	return map;
}
console.log(strMapObj(map)); // yes=>true,no=>false
```



##  总结

和Set 对比
Map.prototype上的clear()、has()、size、delete()方法与Set.prototype上相同；唯一不同的是，Set是不存在键名的，键值与键名相同，所以没有get和set的方法，只有add方法；而Map具有键名和键值，所以对应set和get方法；

