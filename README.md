# WindowsJavaMock
To accelerate the development of mobile team
<p>
	<span style="font-size:18px;"><br />
	</span>
</p>
<p>
</p>
<p>
	<span style="font-size:18px;"><span style="color:rgb(51, 51, 51);"><span style="white-space:pre">	</span>&nbsp;</span><span style="color:rgb(51, 51, 51);">本文来自</span><a target="_blank" href="http://blog.csdn.net/liuxian13183/"><span style="color:rgb(202, 0, 0);">http://blog.csdn.net/liuxian13183/</span></a><span style="color:rgb(51, 51, 51);">&nbsp;</span>，引用必须注明出处！</span>
</p>
<p>
	<span style="font-size:18px;"><br />
	</span>
</p>
<p>
	<span style="font-size:18px;">公司进行技术部拆分，以项目制作为新的开发模式，前端+移动端+后端，于是加速Api开发变得很有必要，准备使用</span>
</p>
<p>
	<span style="font-size:18px;">mock加速进程，使各端可以并行开发。</span>
</p>
<p>
	<span style="font-size:18px;"><br />
	</span>
</p>
<p>
	<span style="font-size:18px;">Mock介绍：<a target="_blank" href="http://wiremock.org/">http://wiremock.org/</a></span>
</p>
<p>
	<br />
	
</p>
<p>
	<span style="font-size:18px;">第一步配置Java环境&nbsp; 地址：<a target="_blank" href="http://blog.csdn.net/reboot123/article/details/6631229">http://blog.csdn.net/reboot123/article/details/6631229</a></span>
</p>
<p>
	<br />
	
</p>
<p>
	<span style="font-size:18px;">第二步：下载standalone.jar 地址：<a target="_blank" href="https://github.com/tomakehurst/wiremock">https://github.com/tomakehurst/wiremock</a></span>
</p>
<p>
	<br />
	
</p>
<p>
	<span style="font-size:18px;">第三步：写Bat工具（py等其他亦可），本文使用1.46版本，9991为端口号</span>
</p>
<p>
	<span style="font-size:18px;"><br />
	</span>
</p>
<p>
	<span style="font-size:18px;">@echo on</span>
</p>
<p>
	<span style="font-size:18px;">java -jarwiremock-1.46-standalone.jar --port 9991</span>
</p>
<p>
	<span style="font-size:18px;">@echo off</span>
</p>
<p>
	<span style="font-size:18px;">运行生成mappings和__files文件夹，mappings目录下写映射文件first-mapping.json</span>
</p>
<p>
	<span style="font-size:18px;">{</span>
</p>
<p>
	<span style="font-size:18px;">&nbsp;&nbsp;&nbsp; &quot;request&quot;: {</span>
</p>
<p>
	<span style="font-size:18px;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &quot;method&quot;: &quot;GET&quot;,</span>
</p>
<p>
	<span style="font-size:18px;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &quot;url&quot;: &quot;/api/login&quot;</span>
</p>
<p>
	<span style="font-size:18px;">&nbsp;&nbsp;&nbsp; },</span>
</p>
<p>
	<span style="font-size:18px;">&nbsp;&nbsp;&nbsp; &quot;response&quot;: {</span>
</p>
<p>
	<span style="font-size:18px;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &quot;status&quot;: 200,</span>
</p>
<p>
	<span style="font-size:18px;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &quot;bodyFileName&quot;:&quot;login.json&quot;,</span>
</p>
<p>
	<span style="font-size:18px;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &quot;headers&quot;: {</span>
</p>
<p>
	<span style="font-size:18px;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &quot;Content-Type&quot;:&quot;application/json&quot;,</span>
</p>
<p>
	<span style="font-size:18px;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &quot;Cache-Control&quot;:&quot;max-age=86400&quot;</span>
</p>
<p>
	<span style="font-size:18px;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; }</span>
</p>
<p>
	<span style="font-size:18px;">&nbsp;&nbsp;&nbsp; }</span>
</p>
<p>
	<span style="font-size:18px;">}</span>
</p>
<p>
	<span style="font-size:18px;">_files目录下写请求结果login.json</span>
</p>
<p>
	<span style="font-size:18px;">{</span>
</p>
<p>
	<span style="font-size:18px;">&nbsp;&nbsp;&nbsp; &quot;working&quot;: &quot;YES&quot;</span>
</p>
<p>
	<span style="font-size:18px;">}</span>
</p>
<p>
	<span style="font-size:18px;"><br />
	</span>
</p>
<p>
	<span style="font-size:18px;">第四步浏览器访问：<a target="_blank" href="http://localhost:9991/api/login">http://localhost:9991/api/login</a>获得请求结果</span>
</p>
<p>
	<span style="font-size:18px;"><br />
	</span>
</p>
<p>
	<span style="font-size:18px;">资源：<a target="_blank" href="http://download.csdn.net/detail/liuxian13183/9652816">下载</a></span>
</p>
<br />
