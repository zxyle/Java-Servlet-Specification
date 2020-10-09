# Web Applications

## 10.1 Web Applications Within Web Servers

## 10.2 Relationship to ServletContext

## 10.3 Elements of a Web Application

## 10.4 Deployment Hierarchies

## 10.5 Directory Structure

## 10.6 Web Application Archive File

## 10.7 Web Application Deployment Descriptor

## 10.8 Replacing a Web Application

## 10.9 错误处理

### 10.9.1 请求属性

Web应用程序必须能够发生指定错误时，使用该应用程序中的其他资源来提供错误响应的内容主体。 这些资源的规范在部署描述符中完成。

如果错误处理程序的位置是servlet或JSP页面：

- 容器创建的原始未包装的请求和响应对象将传递到servlet或JSP页面。
- 设置请求路径和属性，就好像执行了对错误资源的`RequestDispatcher.forward`一样。

必须设置表10-1中的请求属性。

| **Request Attributes**             | **Type**            |
| ---------------------------------- | ------------------- |
| javax.servlet.error.status_code    | java.lang.Integer   |
| javax.servlet.error.exception_type | java.lang.Class     |
| javax.servlet.error.message        | java.lang.String    |
| javax.servlet.error.exception      | java.lang.Throwable |
| javax.servlet.error.request_uri    | java.lang.String    |
| javax.servlet.error.servlet_name   | java.lang.String    |

这些属性允许Servlet根据状态码，异常类型，错误消息，传播的异常对象以及发生错误的Servlet处理的请求的URI生成专门的内容（由getRequestURI调用确定），以及发生错误的Servlet的逻辑名称。

在本规范的2.3版本的属性列表中引入了异常对象后，异常类型和错误消息属性就变得多余了。 保留它们是为了与早期版本的API向后兼容。

### 10.9.2 错误页面

为了允许开发人员自定义servlet生成错误时返回到Web客户端的内容的外观，部署描述符定义了错误页面描述的列表。 该语法允许当servlet或过滤器在响应中针对特定状态代码调用sendError时，或者如果servlet生成传播到容器的异常或错误时，容器将返回资源配置。

如果在响应上调用sendError方法，则容器将查询使用状态码语法的Web应用程序的错误页面声明列表，并尝试进行匹配。 如果存在匹配项，则容器将返回该资源，如位置条目所示。

Servlet或过滤器在处理请求期间可能会引发以下异常：

- 运行时异常或错误
- ServletExceptions或其子类
- IOExceptions或其子类

Web应用程序可能已使用exception-type元素声明了错误页面。 在这种情况下，容器通过将抛出的异常与使用exception-type元素的错误页面定义列表进行比较来匹配异常类型。 匹配导致容器返回位置条目中指示的资源。 类层次结构中最接近的匹配获胜。

如果没有使用类层次结构匹配项包含包含异常类型的错误页面声明，并且抛出的异常是ServletException或其子类，则容器将提取包装的异常，如ServletException.getRootCause方法所定义。 对错误页面声明进行第二遍处理，再次尝试与错误页面声明进行匹配，但改用包装的异常。

在部署描述符中使用exception-type元素的错误页面声明必须是唯一的，直到该exception-type的类名为止。 同样，使用状态码元素的错误页面声明在部署描述符中必须唯一，直到状态码为止。

如果部署描述符中的错误页面元素不包含异常类型或错误代码元素，则错误页面为默认错误页面。

当使用RequestDispatcher或filter.doFilter方法调用时发生错误时，描述的错误页面机制不会干预。 这样，使用RequestDispatcher的筛选器或Servlet就有机会处理所生成的错误。

如果Servlet产生了如上所述的错误页面机制无法处理的错误，则容器必须确保发送状态为500的响应。

默认的servlet和容器将使用sendError方法发送4xx和5xx状态响应，以便可以调用错误机制。 默认的servlet和容器将对2xx和3xx响应使用setStatus方法，并且不会调用错误页面机制。

如果应用程序按照第2-10页的第2.3.3.3节“异步处理”中所述使用异步操作，则应用程序有责任处理应用程序创建的线程中的所有错误。 容器可以处理通过AsyncContext.start发出的线程中的错误。 有关处理在AsyncContext.dispatch期间发生的错误的信息，请参见第2-17页，第2节“容器必须按以下方式捕获和处理在执行分配方法期间可能发生的任何错误或异常：”

### 10.9.3 错误过滤器

错误页面机制对容器创建的原始未包装/未过滤的请求和响应对象进行操作。 第6.2.5节“过滤器和RequestDispatcher”中描述的机制可用于指定在生成错误响应之前应用的过滤器。

## 10.10 Welcome Files

## 10.11 Web Application Environment

## 10.12 Web Application Deployment

## 10.13 Inclusion of a web.xml Deployment Descriptor