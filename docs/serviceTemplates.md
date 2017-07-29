# service模板项目（待续）

## 1、mk-service-auth <a href="https://github.com/ziaochina/mk-service-auth" target="_blank">[代码]</a>

- 提供token的创建与验证
- 注册为mk-server的拦截器
- 扩展上下文中的setToken方法和token对象

## 2、mk-service-db <a href="https://github.com/ziaochina/mk-service-db" target="_blank">[代码]</a>

- 基于sequelize实现数据库的访问
- 注册为mk-server的拦截器
- 实现自动化事务包装，通过api.getDB()返回数据库访问对象
