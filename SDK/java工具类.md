# java工具类

## 功能发布记录

| 版本 | 拟制/修改日期 | 拟制/修改人 | 修改记录 | 批准人 |
| ---- | ------------- | ----------- | -------- | ------ |
| 1.0  | 2022/11/10    | 杜金跃      | 初版     |        |
|      |               |             |          |        |

## 重要通知

无

## 组件描述

为了支持项目组的快速开发需求,java工具类组件封装了开源的工具,提供一系列工具使项目组加速开发

## 快速入门

工具类是面向开发者使用SDK集成的技术组件。要求开发者在项目中引入该组件所生成的jar包。

### 功能清单

#### 布隆过滤器封装

布隆过滤器可以用于检索一个元素是否在一个集合中。 它的优点是空间效率和查询时间都比一般的算法要好的多，缺点是有一定的误识别率和删除困难

使用方式:

```java
public class BloomFilterFactoryTest {
    @Test
    public void createBoomFilter() {
        BloomFilter boomFilter = BloomFilterFactory.createBoomFilter(5);
        boomFilter.add("1");
        boomFilter.add("2");
        boomFilter.add("3");
        boomFilter.add("4");
        boomFilter.add("5");
        boomFilter.add("6");
        boolean a = boomFilter.contains("1");
        boolean b = boomFilter.contains("8");
        Assert.assertTrue(a);
        Assert.assertFalse(b);

        BloomFilter boomFilter1 = BloomFilterFactory.createBoomFilter(1, 2, 3);
        boomFilter1.add("1");
        boomFilter1.add("2");
        boomFilter1.add("3");
        boomFilter1.add("4");
        boomFilter1.add("5");
        boomFilter1.add("6");
        boolean c = boomFilter.contains("1");
        boolean d = boomFilter.contains("8");
        Assert.assertTrue(c);
        Assert.assertFalse(d);
    }
}
```

#### http客户端封装

使用示例：

```java
public class HttpUtilsTest {
    @Test
    public void httpGet() {
        String bodyString = HttpUtil.get("https://www.baidu.com");
        Assert.assertNotNull(bodyString);

        String bodyString2 = HttpUtil.get("https://www.baidu.com", CharsetUtil.CHARSET_UTF_8);
        Assert.assertNotNull(bodyString2);

        HashMap<String, Object> paramMap = new HashMap<>();
        paramMap.put("city", "北京");
        String bodyString3 = HttpUtil.get("https://www.baidu.com", paramMap);
        Assert.assertNotNull(bodyString3);
    }

    @Test
    public void httpPost() {
        HashMap<String, Object> paramMap = new HashMap<>();
        paramMap.put("city", "北京");
        String bodyString = HttpUtil.post("https://www.baidu.com", paramMap);
        Assert.assertNotNull(bodyString);
    }

    @Test
    public void httpUpload() {
        HashMap<String, Object> paramMap = new HashMap<>();
        //文件上传只需将参数中的键指定（默认file），值设为文件对象即可，对于使用者来说，文件上传与普通表单提交并无区别
        //paramMap.put("file", FileUtil.file("D:\\face.jpg"));
        String result = HttpUtil.post("https://www.baidu.com", paramMap);
        Assert.assertNotNull(result);
    }

    @Test
    public void httpDownload() {
        String fileUrl = "https://mirrors.sohu.com/nginx/nginx-1.9.5.zip";

        //将文件下载后保存在E盘，返回结果为下载文件大小
        long size = HttpUtil.downloadFile(fileUrl, FileUtil.file("e:/"));
        Assert.assertTrue(size > 0);
    }

    @Test
    public void httpDownload2() {
        String fileUrl = "https://mirrors.sohu.com/nginx/nginx-1.9.5.zip";

        long size = HttpUtil.downloadFile(fileUrl, FileUtil.file("e:/"), new StreamProgress() {

            @Override
            public void start() {
                Console.log("开始下载。。。。");
            }

            @Override
            public void progress(long total, long progressSize) {
                Console.log("total {} 已下载：{}", total, FileUtil.readableFileSize(progressSize));
            }

            @Override
            public void finish() {
                Console.log("下载完成！");
            }
        });
        Assert.assertTrue(size > 0);
    }
}
```

#### shell脚本执行封装

Shell脚本执行工具类提供了java进程调用shell脚本的封装,还封装了在jvm关闭时提供的hook

使用示例:

```java
class RunTest implements Runnable {
    @Override
    public void run() {
        System.out.println("jvm is closing down");
    }
}

public class ShellExecUtilTest {
    @Test
    public void execTest() {
        String ipconfig = ShellExecUtil.exec("ipconfig");
        Assert.assertNotNull(ipconfig);
    }

    @Test
    public void hookTest() {
        ShellExecUtil.addJvmShutdownHook(new RunTest());
        System.out.println("go go go");
        Assert.assertTrue(true);
    }
}
```

#### DFA算法封装

提供字符串查找和敏感词替换功能

使用示例:

```java
public class DFAUtilTest {

    /**
     * 可以做大段文字中的词汇匹配
     */
    @Test
    public void wordTreeTest() {
        List<String> words = new ArrayList<>();
        words.add("aa");
        words.add("bb");
        words.add("cc");

        String demo = "你是aa，bb，cc";

        WordTree wordTree = DFAUtil.createWordTree(words);
        List<String> result = wordTree.matchAll(demo);
        Assert.assertEquals("[aa, bb, cc]", result.toString());

        // match 方法 匹配到第一个会终止匹配
        String match = wordTree.match(demo);
        Assert.assertEquals("aa", match);
    }

    /**
     * 敏感词 替换
     */
    @Test
    public void sensitiveTest() {
        List<String> words = new ArrayList<>();
        words.add("aa");
        words.add("bb");
        words.add("cc");

        String demo = "你个aa,bb,cc";

        SensitiveUtil.init(words);
        String result = SensitiveUtil.sensitiveFilter(demo);
        Assert.assertEquals("你个**,*,啥**玩意", result);

        String result2 = SensitiveUtil.sensitiveFilter(demo, true, null);
        Assert.assertEquals("你个**,*,啥**玩意", result2);
    }

    @Test
    public void sensitiveTest2() {
        List<String> words = new ArrayList<>();
        words.add("aa");
        words.add("bb");
        words.add("cc");
        DFAUtil.initKeyWords(words);

        String result = DFAUtil.sensitiveReplace("你个aa,bb,cc");
        Assert.assertEquals("你个**,*,啥**玩意", result);
    }

    @Test
    public void zodiacTest() {
        String zodiac = DateUtils.zodiac(19999);
        System.out.println(zodiac);
        Assert.assertNotNull(zodiac);
    }
}
```

#### 日期工具

提供日期格式化和日期计算功能

使用示例：

```java
public class DateUtilsTest {

    @Test
    public void currentDateTest() {
        String dateStr = DateUtils.currentDateStr();
        System.out.println(dateStr);
        Assert.assertNotNull(dateStr);
    }

    @Test
    public void smartParseTest() {
        Date date = DateUtils.smartParse("2022-08-02");
        System.out.println(date.toString());
        Date date2 = DateUtils.smartParse("2022-08-02 22:22:10");
        System.out.println(date2.toString());

        //yyyy年MM月dd日 HH时mm分ss秒
        Date date3 = DateUtils.smartParse("2022年8月2日 22时22分10秒");
        System.out.println(date3.toString());
        Assert.assertTrue(true);
    }

    @Test
    public void parseTest() {
        Date date = DateUtils.parse("2022年8月2日 22时22分10秒", "yyyy年MM月dd日 HH时mm分ss秒");
        System.out.println(date.toString());
        Assert.assertTrue(true);
    }

    @Test
    public void formatDateTest() {
        String date = DateUtils.formatDate(new Date(), "yyyy年MM月dd日 HH时mm分ss秒");
        System.out.println(date);
        Assert.assertTrue(true);
    }

    @Test
    public void offsetTest() {
        Date newDate = DateUtils.offset(new Date(), Calendar.MONTH, -3);
        System.out.println(newDate.toString());
        Assert.assertTrue(true);
    }

    @Test
    public void timeDifferenceTest() {
        Date newDate = DateUtils.offset(new Date(), Calendar.MONTH, -3);
        long diff = DateUtils.timeDifference(new Date(), newDate, ChronoUnit.DAYS);
        System.out.println(diff);
        Assert.assertTrue(true);
    }
}
```

#### 文件工具类

提供文件读写和文件操作功能

使用示例：

```java
public class FileUtilsTest {
    /**
     * 文件创建
     */
    @Test
    public void touch() {
        File touch = FileUtil.touch("E://test.txt");
        boolean exists = touch.exists();
        Assert.assertTrue(exists);
    }

    /**
     * 文件删除
     */
    @Test
    public void del() {
        boolean del = FileUtil.del("E://test.txt");
        Assert.assertTrue(del);
    }

    /**
     * 文件移动
     */
    @Test
    public void move() {
        File source = new File("E://test.txt");
        File target = new File("D://test.txt");
        FileUtil.move(source, target, true);
        Assert.assertTrue(true);
    }

    /**
     * 文件写入 和 读取
     */
    @Test
    public void write() {
        List<String> list = new ArrayList<>();
        list.add("test");
        list.add("test2");
        File file = FileUtil.writeLines(list, "E://test.txt", StandardCharsets.UTF_8, true);
        List<String> lines = FileUtil.readLines(file, StandardCharsets.UTF_8);
        System.out.println(lines.toString());
        Assert.assertTrue(true);
    }

    /**
     * junit 中 启动线程会被强制终止, 代码仅供参考
     */
    @Test
    public void createFileWatchTest() {
        File file = FileUtil.file("E://test.txt");
        //这里只监听文件或目录的修改事件
        WatchMonitor watchMonitor = WatchMonitor.create(file, WatchMonitor.ENTRY_MODIFY);
        watchMonitor.setWatcher(new Watcher() {
            @Override
            public void onCreate(WatchEvent<?> event, Path currentPath) {
                Object obj = event.context();
                System.out.println("创建：" + currentPath + obj + DateUtil.now());
            }

            @Override
            public void onModify(WatchEvent<?> event, Path currentPath) {
                Object obj = event.context();
                System.out.println("修改:" + currentPath + obj + DateUtil.now());
            }

            @Override
            public void onDelete(WatchEvent<?> event, Path currentPath) {
                Object obj = event.context();
                System.out.println("删除:" + currentPath + obj + DateUtil.now());
            }

            @Override
            public void onOverflow(WatchEvent<?> event, Path currentPath) {
                Object obj = event.context();
                System.out.println("Overflow：" + currentPath + obj + DateUtil.now());
            }
        });

        //设置监听目录的最大深入，目录层级大于制定层级的变更将不被监听，默认只监听当前层级目录
        watchMonitor.setMaxDepth(3);
        //启动监听
        watchMonitor.start();

        Assert.assertTrue(true);
    }
}
```

#### 图片工具

提供图片的缩放,剪切,转换类型,彩色变黑白,图片添加文字水印或图片水印,图片的旋转,图片压缩.

使用示例:

```java
public class ImageUtilsTest {

    @Test
    public void scaleTest() {
        ImageUtils.scale("E://1.jpg", "E://2.jpg", 0.5f);
        Assert.assertTrue(true);
    }

    @Test
    public void cutTest() {
        ImageUtils.cut("E://1.jpg", "E://3.jpg", new Rectangle(100, 100, 100, 100));
        Assert.assertTrue(true);

    }

    @Test
    public void convertTest() {
        ImageUtils.convert("E://1.jpg", "E://4.png");
        Assert.assertTrue(true);
    }

    @Test
    public void grayImageTest() {
        ImageUtils.grayImage("E://1.jpg", "E://5.png");
        Assert.assertTrue(true);
    }

    @Test
    public void addTextTest() {
        ImageUtils.addText("E://1.jpg", "E://6.jpg", "哈哈哈哈", Color.BLUE, new Font("黑体", Font.BOLD, 100), 0, 0, 0.5f);
        Assert.assertTrue(true);
    }

    @Test
    public void addWatermarkTest() {
        ImageUtils.addWatermark("E://1.jpg", "E://7.jpg", "E://biaoqing.jpg", 0, 0, 0.5f);
        Assert.assertTrue(true);
    }

    @Test
    public void rotateTest() {
        try {
            ImageUtils.rotate("E://biaoqing.jpg", "E://8.jpg", 90);
        } catch (IOException e) {
            e.printStackTrace();
        }
        Assert.assertTrue(true);
    }

    @Test
    public void compress() {
        ImageUtils.compress("E://1.jpg", "E://9.jpg", 0.5d);
        Assert.assertTrue(true);
    }
}
```

## 操作指南

无

## 典型实践

无

## API参考

无

## SDK

```
<dependency>
    <groupId>com.chinatower</groupId>
    <artifactId>chinatower_common_utils</artifactId>
    <version>1.0</version>
</dependency>
```

## 网络要求

无

## 常见问题

无

## 样例文件

无