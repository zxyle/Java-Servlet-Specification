# 前言

本文档是Java™Servlet规范4.0版。 本文描述了Java Servlet API的标准。

## 其他来源

该规范旨在对Java Servlet进行完整而清晰的解释，但是如果仍有疑问，可以参考以下资源：

- 已提供参考实现（RI），该参考实现为此规范提供了行为基准。 在规范中保留对特定功能的实现进行解释的地方，实现者可以将参考实现用作如何实现规范意图的模型。
- 提供了兼容性测试套件（CTS），用于评估实现是否满足Java Servlet API标准的兼容性要求。 测试结果对于解决有关实施是否标准的问题具有规范价值。
- 如果需要进一步澄清，则应咨询Java Community Process下的Java Servlet API工作组，它是此类问题的最终仲裁者。

欢迎发表评论和反馈，并将其用于改进将来的版本。

## 谁应该阅读本规范

本规范的目标读者包括以下几类：

- 想要提供符合此标准的servlet引擎的Web服务器和应用程序服务器供应商。
- 想要支持符合此规范的Web应用程序的创作工具开发人员
- 有经验的servlet作者，他们想了解servlet技术的基本机制。

我们强调，此规范不是servlet开发人员的用户指南，也不能照此使用。

## API参考

可在http://docs.oracle.com/javaee/在线获得定义Java Servlet API的类，接口和方法签名的完整规范及其随附的Javadoc™文档。

## 其他Java平台规范

本规范通篇引用以下Java API规范：

- Java平台企业版（" Java EE" ），版本8
- Java Server Pages™（"JSP™" ），版本2.3
- Java命名和目录接口™（" J.N.D.I" ）
- Java EE平台的上下文和依赖项注入
- 托管bean规范

这些规范可以在Java平台企业版网站上找到：http://docs.oracle.com/javaee/。

## 其他重要参考

以下Internet规范提供了与Java Servlet API和标准Servlet引擎的开发和实现有关的信息：

- RFC 1630 Uniform Resource Identifiers (URI) Preface vii 
- RFC 1738 Uniform Resource Locators (URL) 
- RFC 3986 Uniform Resource Identifiers (URI): Generic Syntax 
- RFC 1945 Hypertext Transfer Protocol (HTTP/1.0) 
- RFC 2045 MIME Part One: Format of Internet Message Bodies 
- RFC 2046 MIME Part Two: Media Types 
- RFC 2047 MIME Part Three: Message Header Extensions for non-ASCII text 
- RFC 2048 MIME Part Four: Registration Procedures 
- RFC 2049 MIME Part Five: Conformance Criteria and Examples 
- RFC 6265 HTTP State Management Mechanism 
- RFC 7258 Pervasive Monitoring Is an Attack 
- RFC 7540 Hypertext Transfer Protocol Version 2 (HTTP/2) 
- RFC 7541 HPACK: Header Compression for HTTP/2 (HPACK) 
- RFC 7230 Hypertext Transfer Protocol (HTTP/1.1): Message Syntax and Routing 
- RFC 7231 Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content 
- RFC 7232 Hypertext Transfer Protocol (HTTP/1.1): Conditional Requests 
- RFC 7233 Hypertext Transfer Protocol (HTTP/1.1): Range Requests 
- RFC 7234 Hypertext Transfer Protocol (HTTP/1.1): Caching 
- RFC 7235 Hypertext Transfer Protocol (HTTP/1.1): Authentication 
- RFC 7301 Transport Layer Security (TLS) Application-Layer Protocol Negotiation Extension (ALPN)
- RFC 7168 The Hyper Text Coffee Pot Control Protocol for Tea Ef (HTCPCP-TEA)1 
- RFC 6585 Additional HTTP Status Codes 
- RFC 2617 HTTP Authentication: Basic and Digest Authentication 
- RFC 3986 Uniform Resource Identifier (URI): Generic Syntax 
- RFC 2119 Key words for use in RFCs to Indicate Requirement Levels

这些RFC的在线版本位于http://www.ietf.org/rfc/

万维网联盟（http://www.w3.org/）是影响该规范及其实现的HTTP相关信息的权威来源。

可扩展标记语言（XML）用于本规范第13章中描述的部署描述符规范。

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in RFC2119.

## 提供反馈

我们欢迎任何有关此规范的反馈。 请通过电子邮件将您的评论发送到servlet-spec@javaee.groups.io。

请注意，由于我们收到的反馈量很大，因此通常不会收到工程师的答复。 但是，每个注释都由规范团队阅读，评估和存档。

## 专家组成员

- Euigeun Chung (TmaxSoft, Inc) 
- Greg Wilkins (Webtide LLC) 
- Justin Lee (MongoDB, Inc) 
- Mark Thomas 
- Martin Mulholland (IBM) 
- Minehiko IIDA (Fujitsu Limited) 
- Neil Griffin (Liferay Inc) 
- Stuart Douglas (RedHat) 
- Wenbo Zhu (Google Inc.)

## 致谢

Oracle的Bill Shannon为该规范提供了宝贵的技术投入。 Oracle的Ron Monzillo帮助推动了有关安全方面的一些建议和技术讨论。 从2.5版开始，Rajiv Mordani一直领导该规范，并为该规范的成功做出了巨大贡献。 多年来，Arjan Tijms为Java EE JCP专家组做出了很大贡献，尤其是对Security和JSF的贡献。 Arjan建议了Servlet 4.0中Mapping Discovery API的初始设计。