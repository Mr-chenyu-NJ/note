## 代码里出现的类加载器一般在做什么

**1. 突破双亲委派，实现 SPI 机制（最典型场景）**

在 Spring 或 JDBC 中，框架的核心接口（比如 `DataSource`、`Driver`）是由上层的**启动类加载器（Bootstrap ClassLoader）**加载的。但是，具体的实现类（比如 MySQL 驱动、HikariCP 连接池）是放在项目的 `lib` 目录下，由**应用类加载器（AppClassLoader）**加载的。

根据双亲委派机制，父加载器是无法直接看到子加载器加载的类的。为了解决这个问题，Java 引入了**线程上下文类加载器（Thread Context ClassLoader）**。

```java
// 1. 这是 JDK 核心类 DriverManager 的初始化逻辑（由 Bootstrap ClassLoader 加载）
public class DriverManager {
    static {
        // 关键动作：获取当前线程的上下文类加载器（默认就是 AppClassLoader）
        ClassLoader cl = Thread.currentThread().getContextClassLoader();
        
        // 2. 使用 ServiceLoader 加载驱动，并显式传入 AppClassLoader
        ServiceLoader<Driver> loadedDrivers = ServiceLoader.load(Driver.class, cl);
        
        // 3. 遍历加载到的驱动并注册
        for (Driver driver : loadedDrivers) {
            registerDriver(driver);
        }
    }
}
```



**2. 保证类的唯一性与正确性（类隔离）**



**3. 动态加载与热部署**



**4. 加载非 .class 资源文件**



> **一句话总结**：
> 框架获取类加载器，本质上是为了**在复杂的类加载层级中，精准地找到并加载目标类或资源**，同时利用类加载器的隔离特性，保证系统的安全与稳定。