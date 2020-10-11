# 应用程序生命周期事件

## 11.1 介绍

应用程序事件功能使Web应用程序开发人员可以更好地控制`ServletContext`和`HttpSession`和`ServletRequest`的生命周期，实现更好的代码分解，并提高管理Web应用程序使用的资源的效率。

## 11.2 事件监听器

应用程序事件监听器是实现一个或多个servlet事件侦听器接口的类。 在部署Web应用程序时，将实例化它们并将其注册在Web容器中。 它们由WAR中的开发人员提供。

Servlet事件侦听器支持`ServletContext`，`HttpSession`和`ServletRequest`对象中状态更改的事件通知。 ``ServletContext`侦听器用于管理应用程序在JVM级别上持有的资源或状态。 `HttpSession`用于管理与同一客户端或用户向Web应用程序发出的一系列请求相关的状态或资源。 `ServletRequest`侦听器用于管理Servlet请求生命周期中的状态。 异步侦听器用于管理异步事件，例如超时和异步处理完成。

可能有多个侦听器类在侦听每种事件类型，并且开发人员可以指定容器为每种事件类型调用侦听器bean的顺序。

### 11.2.1 事件类型和侦听器接口

### 11.2.2 侦听器使用示例

## 11.3 Listener Class Configuration

### 11.3.1  Provision of Listener Classes

### 11.3.2 Deployment Declarations

### 11.3.3 Listener Registration

### 11.3.4 Notifications At Shutdown

## 11.4 Deployment Descriptor Example

## 11.5 Listener Instances and Threading

## 11.6 Listener Exceptions

## 11.7 Distributed Containers

## 11.8 Session Events

