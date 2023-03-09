### go简单入门

##### 环境变量

- GOPATH：当前用户的HOME目录下的名为go文件夹对应的目录路径。
- GOPATH文件夹中的pkg子文件夹用来缓存被本地项目所依赖的Go模块（一个Go模块为若干Go库包	的集合）的版本。
- GOBIN：指定go install子命令产生的Go应用程序二进制可执行文件应该存储在何处。 它的默认值为GOPATH文件夹中的bin子目录所对应的目录路径。 

##### 运行go程序

- go run子命令并不推荐在正式的大项目中使用。go run子命令只是一种方便的方式来运行简单的Go程序。 对于正式的项目，最好使用go build或者go install子命令构建可执行程序文件来运行Go程序。
- 支持Go模块特性的Go项目的根目录下需要一个go.mod文件。此文件可以使用go mod init子命令来生成。
- 名称以_和.开头的源代码文件将被Go官方工具链工具忽略掉。

##### go子命令

* go vet子命令可以用来检查可能的代码逻辑错误（即警告）。
* go fmt子命令来用同一种代码风格格式化Go代码
* 
  go test子命令来运行单元和基准测试用例。

* 用go doc子命令来（在终端中）查看Go代码库包的文档
* go mod init example.com/myproject命令可以用来在当前目录中生成一个go.mod文件。 当前目录将被视为一个名为example.com/myproject的模块（即当前项目）的根目录。 此go.mod文件将被用来记录当前项目需要的依赖模块和版本信息。 我们可以手动编辑或者使用go子命令来修改此文件。
* go mod tidy命令用来通过扫描当前项目中的所有代码来添加未被记录的依赖至go.mod文件或从go.mod文件中删除不再被使用的依赖。go get命令用拉添加、升级、降级或者删除单个依赖。此命令不如go modtidy命令常用。

##### 简单go实例

* 注释
  * 单行注释 ：//
  * 块级注释：/*  */
* 代码断行：{}左大括号{不能被放到下一行，否则编译不通过

##### 关键字和标识符

关键字

```text
 break default func interface select
 case defer go map struct
 chan else goto package switch
 const fallthrough if range type
 continue for import return var
```

- const、func、import、package、type和var用来声明各种代码元素。
- chan、interface、map和struct用做 一些组合类型的字面表示中。
- break、case、continue、default、 else、fallthrough、for、goto、if、range、 return、select和switch用在流程控制语句中。
- defer和go也可以看作是流程控制关键字， 但它们有一些特殊的作用。

标识符

- 一个标识符是一个以Unicode字母或者_开头并且完全由Unicode字母和Unicode数字组成的单词。

- 标识符_是一个特殊字符，它叫做空标识符。

- 由大写Unicode字母开头的标识符称为导出标识符。 这里导出可以被理解为公开（public）。 其它（即非Unicode大写字母开头的）标识符称为非导出标识符。 非导出可以被理解为私有。

  ​

##### 基本类型和它们字面量表示


类型（type）可以被看作是值（value）的模板，值可以被看作是类型的实例

基本内置类型

- 一种内置布尔类型：bool。
- 十一种内置整数类型：int8、uint8、int16、uint16、int32、uint32、int64、uint64、int、uint和uintptr。
- 两种内置浮点数类型：float32和float64。
- 两种内置复数类型：complex64和complex128。
- 一种内置字符串类型：string。


内置类型也称为预声明类型。

除了bool和string类型，其它的15种内置基本类型都称为数值类型（整型、浮点数型和复数型）。

Go中有两种内置类型别名（type alias）：

- byte是uint8的内置别名。 我们可以将byte和uint8看作是同一个类型。
- rune是int32的内置别名。 我们可以将rune和int32看作是同一个类型。

