## 项目简介
 基于spring  springmvc  springsecurity restful构建本项目。
 * spring 提供框架管理功能。
 * springmvc 通过restful风格，提供服务。
 * 通过注解实现方法级别的安全控制。

主要注解：
* @PreAuthorize
* @PostAuthorize
* @Security

核心代码如下所示；
``` bash
public interface UserService {

	List<User> findAllUsers();

	@PostAuthorize ("returnObject.type == authentication.name")
	User findById(int id);

	@PreAuthorize("hasRole('ADMIN')")
	void updateUser(User user);
	
	@PreAuthorize("hasRole('ADMIN') AND hasRole('DBA')")
	void deleteUser(int id);
}
```
本项目没有xml配置文件，全部以注解的方式，进行配置注入。

#### 项目参考：[www.websystique.com](http://www.websystique.com)
#### 个人blog: [wiki.niejinkun.com](http://wiki.niejinkun.com)
