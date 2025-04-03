---
media: https://www.bilibili.com/video/BV1Hx4y147gW
---

- ![《ROS 2机器人开发从入门到实践》 2.4 多功能包的最佳实践WorkSpace - 01:08|50](《ROS%202机器人开发从入门到实践》%202.4%20多功能包的最佳实践WorkSpacePT1M8.286S.webp) [01:08](https://www.bilibili.com/video/BV1Hx4y147gW?t=68.285514#t=01:08.29) 工作空间的概念


- ![《ROS 2机器人开发从入门到实践》 2.4 多功能包的最佳实践WorkSpace - 01:22|50](《ROS%202机器人开发从入门到实践》%202.4%20多功能包的最佳实践WorkSpacePT1M22.625S.webp) [01:22](https://www.bilibili.com/video/BV1Hx4y147gW?t=82.625139#t=01:22.63) 创建工作空间
- -p表示创建双重文件夹


- ![《ROS 2机器人开发从入门到实践》 2.4 多功能包的最佳实践WorkSpace - 02:22|50](《ROS%202机器人开发从入门到实践》%202.4%20多功能包的最佳实践WorkSpacePT2M22.857S.webp) [02:22](https://www.bilibili.com/video/BV1Hx4y147gW?t=142.85719#t=02:22.86) 选择构建单独功能包

- ![《ROS 2机器人开发从入门到实践》 2.4 多功能包的最佳实践WorkSpace - 03:00|50](《ROS%202机器人开发从入门到实践》%202.4%20多功能包的最佳实践WorkSpacePT3M0.74S.webp) [03:00](https://www.bilibili.com/video/BV1Hx4y147gW?t=180.739731#t=03:00.74) 功能包的依赖情况
- 声明依赖就可以先构建需要的功能包再构建另一个功能包


- ![《ROS 2机器人开发从入门到实践》 2.4 多功能包的最佳实践WorkSpace - 05:19|50](《ROS%202机器人开发从入门到实践》%202.4%20多功能包的最佳实践WorkSpacePT5M19.238S.webp) [05:19](https://www.bilibili.com/video/BV1Hx4y147gW?t=319.237518#t=05:19.24) 
- python不用编译所以快一些

- ![《ROS 2机器人开发从入门到实践》 2.4 多功能包的最佳实践WorkSpace - 05:48|50](《ROS%202机器人开发从入门到实践》%202.4%20多功能包的最佳实践WorkSpacePT5M48.572S.webp) [05:48](https://www.bilibili.com/video/BV1Hx4y147gW?t=348.571974#t=05:48.57) 只构建单独功能包
- --packages-select

colcon build 再当前文件夹生成build/ log/ install/
colcon build 会自动扫描当前文件夹下的子文件包


- ![《ROS 2机器人开发从入门到实践》 2.4 多功能包的最佳实践WorkSpace - 08:15|50](《ROS%202机器人开发从入门到实践》%202.4%20多功能包的最佳实践WorkSpacePT8M15.848S.webp) [08:15](https://www.bilibili.com/video/BV1Hx4y147gW?t=495.848454#t=08:15.85) 构建依赖关系
- 再功能包的package.xml写个depend先加载的功能包
