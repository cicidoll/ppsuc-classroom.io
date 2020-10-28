公安大学团河校区空闲教室查询课表
===
<h3>更新日志：</h3><br>
<h4>2020/10/28</h4><br>
1、重写Python爬虫：（1）优化铸剑楼、中楼、西配教室查询机制。（2）支持一键运行脚本，自动查询多栋教学楼。（3）支持查询结果文件化，以classRoomData.json输出至根目录。<br>
------------------------------<br>
<h3>更新日志：</h3><br>
<h4>2020/10/22</h4><br>
1、教室列表剔除育警中楼四楼会议室（403、404、405、406）。<br>
2、主要样式css文件更改为less文件。<br>
3、添加小功能：可根据当前周几，默认跳转到相应日期的课表查询。<br>
4、项目采用webpack打包，打包规则见webpack.config.js<br>
5、添加.gitignore文件，省略node_modules文件夹<br>
6、版本更新至1.7<br>
------------------------------<br>
<h3>更新日志：</h3><br>
<h4>2020/10/19</h4><br>
1、更新数据。<br>
2、版本更新至1.6<br>
------------------------------<br>
<h3>更新日志：</h3><br>
<h4>2020/09/18</h4><br>
1、优化css背景图片，由本地资源改为网络资源，降低服务器流量压力。<br>
2、优化冗余css样式，更新页脚信息。<br>
3、为content-div添加Vue动画。<br>
4、版本更新至1.5<br>
------------------------------<br>
<h3>更新日志：</h3><br>
<h4>2020/09/16</h4><br>
1、优化了css文件，剔除冗余样式。<br>
2、优化了教室选择按钮逻辑，简化代码。<br>
------------------------------<br>
<h3>更新日志：</h3><br>
<h4>2020/09/14</h4><br>
1、添加了对中楼和西配楼的数据支持。<br>
------------------------------<br>
<h3>更新日志：</h3><br>
<h4>2020/09/10</h4><br>
1、添加了显示 上午空闲教室 和 下午空闲教室 的功能。<br>
------------------------------<br>
<h2>一、Python爬虫</h2><br>
通过Python抓取课表上无课的教室，以数组的方式存取下来。<br>
am12=[0 ,0 ,'101',0 ,0 ,'103' ,0 ,'103' ,0 ,0]#以五个元素为周一到周五，0为占位符，表示该教室有课。<br>
am12的命名，是指向上午第1、2节。<br>
以am12数组为例，说明周三的上午1、2节，101教室空闲；周一的上午1、2节，103教室空闲；周三上午1、2、节，103教室空闲。<br>

<h2>二、vue框架</h2><br>
<h3>1、逻辑简述</h3><br>
主要是利用了vue的组件注册。<br>
共注册两个全局组件（tab组件和pane组件），其中pane组件嵌套在tab组件当中；一个局部组件（content-div），负责显示数据。<br>
数据由vue主实例进行维护，并通过调用主实例的方法computedRes()将数据传递到content-div组件中。<br>
组件与组件之间的内容分发利用了slot。<br>