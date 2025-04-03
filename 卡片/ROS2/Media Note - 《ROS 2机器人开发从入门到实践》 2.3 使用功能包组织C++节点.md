---
media: https://www.bilibili.com/video/BV1Pb42177BJ
---
DECK: C++::2.3 使用功能包组织C++节点
#### 怎么用功能包？
创建ros2 pkg create demo_cpp_pkg --build-type ament_cmake --license Apache-2.0
- ros2 pkg create 功能包名字 构建类型 证书类型
->CMackLists.txt配置
->->find_package(rclcpp REQUIRED)
->->add_executable(可执行文件名 src/*.cpp)
->->ament_target_dependencies(项目名 rclcpp)
->-> install(TARGETS 可执行文件名 DESTINATION lib/${项目名})
->项目名和可执行文件名没有冲突
->colcon build(在功能包文件夹同级)
->source install/setup.bash添加功能包输出的环境变量
->ros2 run 功能包名 可执行文件名(验证结果)
<!--ID: 1743148144733-->




- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 00:21|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT21.704S.webp) [00:21](https://www.bilibili.com/video/BV1Pb42177BJ?t=21.70367#t=21.70) 创建功能包
- ros2 pkg create demo_cpp_pkg --build-type ament_cmake --license Apache-2.0

- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 00:53|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT53.673S.webp) [00:53](https://www.bilibili.com/video/BV1Pb42177BJ?t=53.673138#t=53.67) 注册节点

- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 01:20|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT1M20.925S.webp) [01:20](https://www.bilibili.com/video/BV1Pb42177BJ?t=80.92461#t=01:20.92) 依赖声明

- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 01:38|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT1M38.313S.webp) [01:38](https://www.bilibili.com/video/BV1Pb42177BJ?t=98.313214#t=01:38.31) 运行

- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 01:54|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT1M54.053S.webp) [01:54](https://www.bilibili.com/video/BV1Pb42177BJ?t=114.052958#t=01:54.05) 实操



- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 02:46|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT2M46.985S.webp) [02:46](https://www.bilibili.com/video/BV1Pb42177BJ?t=166.984703#t=02:46.98) 
- ros2 pkg create demo_cpp_pkg --build-type ament_cmake --license Apache-2.0
- ros2 pkg create 功能包名字 构建类型 证书类型


- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 03:28|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT3M28.108S.webp) [03:28](https://www.bilibili.com/video/BV1Pb42177BJ?t=208.108223#t=03:28.11) 功能包里面有CMakeLists的原因


- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 03:51|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT3M51.681S.webp) [03:51](https://www.bilibili.com/video/BV1Pb42177BJ?t=231.681254#t=03:51.68) 编写功能包代码


- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 04:38|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT4M38.741S.webp) [04:38](https://www.bilibili.com/video/BV1Pb42177BJ?t=278.741393#t=04:38.74) 配置功能包

- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 07:17|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT7M17.66S.webp) [07:17](https://www.bilibili.com/video/BV1Pb42177BJ?t=437.660202#t=07:17.66) 代替查找rclcpp的头文件的命令
- find_package(ament_cmake REQUIRED)
- ament_target_dependencies(项目名 rclcpp)

- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 10:31|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT10M31.117S.webp) [10:31](https://www.bilibili.com/video/BV1Pb42177BJ?t=631.117302#t=10:31.12) find rclcpp的时候就find了ament_cmake所以可以直接找rclcpp。但是有点ament命令可能不执行

- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 12:04|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT12M4.483S.webp) [12:04](https://www.bilibili.com/video/BV1Pb42177BJ?t=724.482708#t=12:04.48) 构建功能包！！！colcon build
- 在同能包同级目录
- 需要已经生成可执行文件

- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 13:03|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT13M3.781S.webp) [13:03](https://www.bilibili.com/video/BV1Pb42177BJ?t=783.780638#t=13:03.78) ldd命令
- 查看项目链接哪些库

- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 13:57|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT13M57.284S.webp) [13:57](https://www.bilibili.com/video/BV1Pb42177BJ?t=837.283743#t=13:57.28) 运行功能包



- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 14:34|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT14M34.416S.webp) [14:34](https://www.bilibili.com/video/BV1Pb42177BJ?t=874.416436#t=14:34.42) 修改环境变量
- source install/setup.bash

- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 15:33|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT15M33.792S.webp) [15:33](https://www.bilibili.com/video/BV1Pb42177BJ?t=933.792442#t=15:33.79) 找不到目录错误

- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 16:51|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT16M51.512S.webp) [16:51](https://www.bilibili.com/video/BV1Pb42177BJ?t=1011.511815#t=16:51.51) 手动添加目录才可以

- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 20:02|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT20M2.838S.webp) [20:02](https://www.bilibili.com/video/BV1Pb42177BJ?t=1202.838072#t=20:02.84) 依赖声明

- ![《ROS 2机器人开发从入门到实践》 2.3 使用功能包组织C++节点 - 20:50|50](《ROS%202机器人开发从入门到实践》%202.3%20使用功能包组织C++节点PT20M50.651S.webp) [20:50](https://www.bilibili.com/video/BV1Pb42177BJ?t=1250.650568#t=20:50.65) 功能包结构分析