---
layout:     post
title:      SpringMVC中相关注解介绍
subtitle:   SpringMVC中相关注解介绍
date:       2018-06-26
author:     Pancratius
header-img: img/home-bg-art.jpg
catalog: true
tags:
    - cocoapods
    - 更新
---

**@RequestMapping**
@RequestMapping是一个用来处理请求地址映射的注解，可用于类或方法上。用于类上，表示类中的所有响应请求的方法都是以该地址作为父路径。

**@GetMapping**
@GetMapping是一个组合注解，是@RequestMapping(method = RequestMethod.GET)的缩写。该注解将HTTP Get 映射到 特定的处理方法上。

**@PreAuthorize/@PostAuthorize**
@PreAuthorize/@PostAuthorize 注解更适合方法级的安全,也支持Spring 表达式语言，提供了基于表达式的访问控制。

**@Controller**
@Controller 用来响应页面，@Controller必须配合模版来使用。

**@RestController**
@RestController是@ResponseBody和@Controller的组合注解。
