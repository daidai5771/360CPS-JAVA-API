360CPS API(JAVA) cps360.demo.CPS360PluginDemo使用说明
==============

步骤1
-------------
将360CPS接口文件夹中的src下所有源文件加载到工程中

步骤2
-------------
修改cps360.demo.CPS360JDBCDemo 中数据库连接字符串

// 驱动程序名
protected String driver = "com.mysql.jdbc.Driver";   
// URL指向要访问的数据库名    
protected String url = "jdbc:mysql://127.0.0.1:3306/db_test";

// MySQL配置时的用户名

protected String username = "test";

// MySQL配置时的密码          

protected String password = "test";


步骤3
-------------
创建订单数据存储表
`
  create table test_order(
		order_id varchar(64) not null default '' comment '订单id' ,
		qid varchar(32) not null default '' comment '用户id' ,
		qihoo_id varchar(32) not null default '' comment '业务线' ,
		ext varchar(64) not null default '' comment '扩展字段' ,
		order_url varchar(1024) not null default '' comment '商品url' ,
		create_time datetime not null comment '第一次创建时间',
		order_time datetime not null comment '下单时间',
		order_updtime datetime not null comment '更新时间',
		order_price decimal(20,2) default 0 comment '订单价格',
		server_price decimal(20,2) default 0 comment '服务费用',
		discount  decimal(20,2) default 0 comment '优惠',
		status  tinyint default 1 comment '状态',
		products text not null default '' comment '产品信息' ,
		delivery text not null default '' comment '邮递信息' ,
		primary key(order_id)
	 ) ENGINE=MyISAM DEFAULT CHARSET=utf8;
 `
创建用户数据存储表
`
	create table test_user(
	 	id int not null AUTO_INCREMENT ,
		username varchar(64) not null ,
		realname varchar(64) null default '',
		email varchar(256) not null,
		password varchar(64) not null,
		sns varchar(128) null default '',
		primary key(id)
	  ) ENGINE=MyISAM DEFAULT CHARSET=utf8;
`
	  
步骤4
-------------
