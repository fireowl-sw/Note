---
media: https://www.bilibili.com/video/BV191p2eMErj/
---

![《ROS 2机器人开发从入门到实践》2.5.1ROS2基础之编程:面向对象编程C++示例 - 01:20](《ROS%202机器人开发从入门到实践》2.5.1ROS2基础之编程_面向对象编程C++示例PT1M20.467S.webp) [01:20](https://www.bilibili.com/video/BV191p2eMErj/?t=80.466512#t=01:20.47) 创建node文件继承rcl的node

![《ROS 2机器人开发从入门到实践》2.5.1ROS2基础之编程:面向对象编程C++示例 - 02:06](《ROS%202机器人开发从入门到实践》2.5.1ROS2基础之编程_面向对象编程C++示例PT2M6.573S.webp) [02:06](https://www.bilibili.com/video/BV191p2eMErj/?t=126.572779#t=02:06.57) 导库

![《ROS 2机器人开发从入门到实践》2.5.1ROS2基础之编程:面向对象编程C++示例 - 02:58](《ROS%202机器人开发从入门到实践》2.5.1ROS2基础之编程_面向对象编程C++示例PT2M58.642S.webp) [02:58](https://www.bilibili.com/video/BV191p2eMErj/?t=178.642061#t=02:58.64) 定义类

![《ROS 2机器人开发从入门到实践》2.5.1ROS2基础之编程:面向对象编程C++示例 - 03:48](《ROS%202机器人开发从入门到实践》2.5.1ROS2基础之编程_面向对象编程C++示例PT3M48.959S.webp) [03:48](https://www.bilibili.com/video/BV191p2eMErj/?t=228.958733#t=03:48.96) 添加属性
加入下划线表示私有

![《ROS 2机器人开发从入门到实践》2.5.1ROS2基础之编程:面向对象编程C++示例 - 04:43](《ROS%202机器人开发从入门到实践》2.5.1ROS2基础之编程_面向对象编程C++示例PT4M43.395S.webp) [04:43](https://www.bilibili.com/video/BV191p2eMErj/?t=283.395092#t=04:43.40) 调用父类的构造函数
调用父类的init方法
传静态引用变量

![《ROS 2机器人开发从入门到实践》2.5.1ROS2基础之编程:面向对象编程C++示例 - 07:53](《ROS%202机器人开发从入门到实践》2.5.1ROS2基础之编程_面向对象编程C++示例PT7M53.871S.webp) [07:53](https://www.bilibili.com/video/BV191p2eMErj/?t=473.87103#t=07:53.87) 属性赋值
this->name_ = name;
this->age_ = age;

![《ROS 2机器人开发从入门到实践》2.5.1ROS2基础之编程:面向对象编程C++示例 - 08:40](《ROS%202机器人开发从入门到实践》2.5.1ROS2基础之编程_面向对象编程C++示例PT8M40.482S.webp) [08:40](https://www.bilibili.com/video/BV191p2eMErj/?t=520.481903#t=08:40.48) eat方法
![《ROS 2机器人开发从入门到实践》2.5.1ROS2基础之编程:面向对象编程C++示例 - 10:15](《ROS%202机器人开发从入门到实践》2.5.1ROS2基础之编程_面向对象编程C++示例PT10M15.11S.webp) [10:15](https://www.bilibili.com/video/BV191p2eMErj/?t=615.109649#t=10:15.11) const的作用是防止改变&引用的外部变量的值

![《ROS 2机器人开发从入门到实践》2.5.1ROS2基础之编程:面向对象编程C++示例 - 10:42](《ROS%202机器人开发从入门到实践》2.5.1ROS2基础之编程_面向对象编程C++示例PT10M42.268S.webp) [10:42](https://www.bilibili.com/video/BV191p2eMErj/?t=642.267984#t=10:42.27) 打印日志
RCLCPP_INFO(this->get_logger(), "打印内容我是%s, %d岁 爱吃%s", this->name_.c_str(), this->age_, food_name.c_str());

![《ROS 2机器人开发从入门到实践》2.5.1ROS2基础之编程:面向对象编程C++示例 - 13:55](《ROS%202机器人开发从入门到实践》2.5.1ROS2基础之编程_面向对象编程C++示例PT13M55.278S.webp) [13:55](https://www.bilibili.com/video/BV191p2eMErj/?t=835.27815#t=13:55.28)使用类
make_shared创建指针和new类似

![《ROS 2机器人开发从入门到实践》2.5.1ROS2基础之编程:面向对象编程C++示例 - 16:31](《ROS%202机器人开发从入门到实践》2.5.1ROS2基础之编程_面向对象编程C++示例PT16M31.428S.webp) [16:31](https://www.bilibili.com/video/BV191p2eMErj/?t=991.427505#t=16:31.43) 编译
cmake list要添加节点
colcon build




