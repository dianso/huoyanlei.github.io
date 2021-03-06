### 210109 更新日志
- 新增：特殊整理时，尝试保护无结尾标点的歌词类多段文本，避免合并成一行
- 新增：全局检查小于 3 个标点符号单独一行的情况
- 新增：全局检查新增错误标点相连的检查
- 优化：结尾统一处理数字与字母的修正，加快运行速度
- 优化：章节标题转换处理、过滤处理
- 优化：大纲视图转换处理
- 优化：英文格式整理，处理拉丁字母、单个字母、段落最前的字母和特定姓名的大小写
- 优化：更多的 HTML 字符实体转换
- 优化：标题中大写转小写，过滤不符合章节规范的段落
- 优化：倒计时样式语句，后面跟省略号的，不处理逗号	`100，99，98……`
- 优化：抛弃日期间隔符半角处理，合并至时间处理
- 优化：工具栏图标更新
- 优化：增强整理代码
- 优化：分段排版代码
- 优化：全文检查时的逻辑判断，加快检查速度
- 优化：高级提取星号时，修改为提取一段文字方便对比
- 优化：Enter 事件自动刷新大纲的代码
- 修正：Tab 事件快捷输入的错误
- 修正：插入标头和统计字数统计空白字符时的错误
- 修正：标题小标号识别的错误

### 201121 更新日志
- 更新：OpenCC 词库更新为11月版本
- 修正：异体字表删除以下单字（错误的和人名中仍然经常使用的），另将有异议的放到最后，可自行酌情删除：
	- 徬	仿
	- 晳	晰
	- 捱	挨
	- 喆	哲
	- 堃	坤
	- 覜	眺
- 修正：简繁自定义修正“⼳幺麽么”、“沉沈”、“著着”、“猛勐”
- 新增：特殊整理，去除章节标题结尾的句号

### 201102 更新日志
- 新增：编辑区换行时，若上下五行检测为章节标题时，将自动刷新大纲视图	`超过限定行数不刷新`
- 优化：繁转简时，简单修正 `沉 -> 沈` 的错误转换
- 优化：比分类识别小数，`4：3。5：1。5 -> 4:3.5:1.5`
- 修正：分隔符居中时全角空格转半角的错误
- 优化：拼音转换更新为多音字，可识别 20858 个常用字	`不推荐大文件时运行`
- 优化：拼音转换删除省市部分
- 优化：拼音转换方式 逐字拼音分组模式 -> 逐字转拼音+逐字首字母	`首字母错误率较高`
	- 例：西藏 -> xi藏 西cang 西zang
	- 例：西藏 -> x藏 西c 西z

### 201018 更新日志
- 优化：大纲视图识别顶级章节，用于处理不规则的章节分级
	- 例：第一季、第一集（rescueme《行湿走肉》）
- 优化：词典放置到内存中缓存，不再生成文件
- 优化：合并部分词典到屏蔽词组
- 优化：分段排版不再修正被分隔的单词，不再用空格补齐单双字节字数
- 更新：词典表分解为8个：
	- 屏蔽词组表 block			基本屏蔽词组表，自动转换拼音修正，最优先级运行
	- 拼音词组表 pinyin			拼音+汉字混杂的词组表
	- 拼音单字表 single			单拼字+缩拼词组表，错误率高
	- 星号缺字表 missword			星号、缺字表，错误率较低，运行慢
	- 词组勘误表 correct			常见中文字词勘误表
	- 错词修正表 phrase			常见错误字/词组修正表
	- 地名修正表 place			省市地名修正表，转拼音修正+混淆修正
	- 地名缩拼表 place.acronym	省市地名缩拼表，错误率高
- 调整：词组类修正为：
	- 31.★修正 → 拼音缺字			处理屏蔽词拼音+省市地名拼音修正，拼音词组修正，单字拼音词组组合修正，缺字、星号词组，单拼修正，错词修正
	- 32.★修正 → 词组勘误			处理词组勘误、错词修正
	- 33.★修正 → 词组混淆			处理屏蔽词混淆
	- 34.★修正 → 省市地名			处理省市地名拼音修正、混淆修正
	- 35.★修正 → 量词小写			处理量词小写修正
- 新增：“自动排版”目录，三个自动排版宏，可以自动化处理整理、排版等流程：
	- 01.自动排版 → 整理·纠错.mac		适合处理无排版文章，整理、转简体后显示纠错		`快捷键：F1`
	- 02.自动排版 → 阅读·大纲.mac		对应 01，阅读排版后显示大纲						`无快捷键`
	- 03.自动排版 → 分段·大纲.mac		适合整理好的文章，分段排版后添加标头				`快捷键：Alt+F2`
	- 04.自动排版 → 反向·纠错.mac		03 的反向整理过程								`快捷键：Alt+F1`
- 主程序更新为 EverEdit 4.3.1.4480
- 用户设置加入 WordFix 字段，用于修正约定英语错误
- 增加“单双引号互换”，可实现单双引号一次性转换
- 新增快捷转换功能，编辑区可利用 `Tab` 键快速转换常用格式（详细说明请看下方列表）
