## JavaScript编码规范 V170525

1. 常量及全局变量采用全部大写的形式.

* 变量的命名使用骆驼命名法，例如：``strParsor. maxLength``

* 类的命名使用骆驼命名法,其中首字母大写.``AccountInfo, EventHandler``

* 方法的命令必须为动词或者是动词短语：``obj.getSomeValue()``

* 私有类的成员变量命名前面加下划线``（_）``。例如：

  ```
  var MyClass = function(){
    var _buffer;
    this.doSomething = function(){
    };
  }
  this._somePrivateVariable = statement;
  ```

* 前缀为 "is" 的变量应该为布尔值，同理 "has";

* 术语 "initialize" 或者 "init" 作为变量名应为初始化方法;

* 迭代临时变量建议使用 "i", "j", "k" （依次类推）等名称;

* 异常处理类建议在变量名称后加上 "Exception" 或者 "Error";

## 缩进 V170525

1. 采用 TAB 键缩进, 统一为4个字符,

  ```
  function demo(param){
      var a1 = 1
      …
  }
  此规则亦适用于函数的参数：
  var o = someObject.get(
      Expression1,
      Expression2,
      Expression3
  );
  ```

* 变量必须在声明初始化以后才能使用，即便是 NULL 类型;

* 变量名请勿使用系统保留关键字;

* 变量应该尽量保持最小的生存周期,及时销毁防止内存泄露;

* 浮点变量必须指明小数点后一位（即使是 0）;

* 浮点变量必须指明实部，即使为零（使用 0. 开头）。

### 代码块 V170525
1. 普通代码段：
  ```
  while (!isDone){
  	doSomething();
  	isDone = moreToDo();
  }

  // IF 语句：
  if (someCondition){
  	statements;
  } else if (someOtherCondition){
  	statements;
  } else {
  	statements;
  }

  //FOR 语句：
  for (initialization; condition; update){
  	statements;
  }

  //WHILE 语句：
  while (!isDone) {
  	doSomething();
  	isDone = moreToDo();
  }

  //DO ... WHILE 语句：
  do {
  	statements;
  } while (condition);

  //SWITCH 语句：
  switch (condition) {
  	case ABC:
  		statements; break;
  	default:
  		statements; break;
  }

  // TRY ... CATCH 语句 ：
  try {
  	statements;
  } catch(e) {
  	statements;
  } finally {
  	statements;
  }
  ```

* 单行的 IF，WHILE 或者 FOR 语句需加入括号 ：

  ```
  if (condition){ statement; }
  while (condition){ statement; }
  for (intialization; condition; update){ statement;}
  ```

* 单行的 IF – ELSE 允许不加括号:

  ```
  if(condition)
  	Statement;
  else
  	Statement;
  ```

* 操作符使用空格隔开（包括三元操作符）,如:
  ```
  var x = a – b;
  var y = result == true ? 1 : 0;]
  ```

* 逗号（,)与for循环中的封号(;)后添加空格。例如:

  ```
  var test = Array(), test2;
  for(i = 0; i < 100; i++){
      Statements;
  }
  ```

* 冒号(:)后添加空格

* 逻辑块之间以空行隔开

### 注释 V170525

1. 保持良好的注释习惯。

* 类/函数/方法前需添加注释,并注明参数类型,返回值类型。例如,

  ```
  /**
   * 金额大小写转换函数
   * @param Int {number} 数字金额
   * @param Num {number} 数字
   * @return String 大写金额
   */
  ```
