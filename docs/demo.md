# 创建一个<a href="https://ziaochina.github.io/mk-demo/" target="_blank">mk-demo</a>这样的网站过程

## 1、安装mk-tools命令行工具

```
$ npm i -g mk-tools
```


## 2、创建空website

```
$ mk website myDemo
$ cd myDemo
```

## 3、clone应用

```
$ mk clone mk-app-root apps/
$ mk clone mk-app-login apps/
$ mk clone mk-app-portal apps/
$ mk clone mk-app-person-list apps/
$ mk clone mk-app-person-card apps/
```

## 4、修改website配置文件

```
//修改文件：myDemo/config.js
//也可以直接进apps目录根据自己需求修改app内容
...
	_options.apps && _options.apps.config({
		//'*': { webapi } //正式网站应该有一个完整webapi对象，提供所有web请求函数
		'mk-app-root': {
			defaultAppName: 'mk-app-login'
		},
		'mk-app-login': {
			goAfterLogin: {
				appName: 'mk-app-portal'
			}
		},
		'mk-app-portal': {
			menu: [{
				key: '1',
				name: 'about',
				appName: 'mk-app-portal-about',
				isDefault: true
			}, {
				key: '2',
				name: 'apps',
				isExpand: true,
				children: [{
					key: '201',
					name: '人员列表',
					appName: 'mk-app-person-list'
				}, {
					key: '202',
					name: '人员卡片',
					appName: 'mk-app-person-card'
				}]
			}]
		}
	})
...
```

## 5、编译
- 编译会生成index.js,mock.js,apps.less 文件
```
$ mk compile website
```

## 6、启动website

```
$ npm start
```