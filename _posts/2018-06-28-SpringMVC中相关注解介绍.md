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

**@Entity**
@Entity注释指名这是一个实体Bean。

**@Table**
@Table注释指定了Entity所要映射带数据库表,如果缺省@Table注释，系统默认采用类名作为映射表的表名。实体Bean的每个实例代表数据表中的一行数据，行中的一列对应实例中的一个属性。

**@Column**
@Column注释定义了将成员属性映射到关系表中的哪一列和该列的结构信息，属性如下：

1）name：映射的列名。如：映射tbl_user表的name列，可以在name属性的上面或getName方法上面加入；

2）unique：是否唯一；

3）nullable：是否允许为空；

4）length：对于字符型列，length属性指定列的最大字符长度；

5）insertable：是否允许插入；

6）updatetable：是否允许更新；

7）columnDefinition：定义建表时创建此列的DDL；

8）secondaryTable：从表名。如果此列不建在主表上（默认是主表），该属性定义该列所在从表的名字。

**@Id**
@Id注释指定表的主键

**@GeneratedValue**
@GeneratedValue注释定义了标识字段生成方式。

**@Temporal**
@Temporal注释用来指定java.util.Date或java.util.Calender属性与数据库类型date、time或timestamp中的那一种类型进行映射。
@Temporal(value=TemporalType.TIME)

**@Transient**
如果不想让一些成员属性映射成数据库字段，可以使用@Transient注释进行标注。

**@OneToOne**
一对一关系，需要在关系维护端的@OneToOne注释中定义mappedBy属性。在关系被维护端建立外键列指向关系维护的主键列。
@OneToOne注释指明User与Card为一对一关系，@OneToOne注释有5个属性：targetEntity、cascade、fetch、optional和mappedBy。

1）targetEntity：Class类型的属性

2）mappedBy：String类型的属性。定义类之间的双向关联。如果类之间是单向关系，不需要提供定义，如果类和类之间形成双向关系。就需要使用这个属性进行定义，否则可能引起数据一致性的问题。

3）cascade：CascadeType类型。该属性定义类和类之间的级联关系。定义级联关系将被容器视为当前类对象及其关联类对象采取相同的操作，而且这种关系是递归的。cascade的值只能从CascadeType.PERSIST(级联新建)、CascadeType.REMOVE(级联删除)、CascadeType.REFRESH(级联刷新)、Cascade.MERGE(级联更新)中选择一个或多个。还有一个选择是使用CascadeType.ALL，表示选择全部四项。

4）fetch：FetchType类型的属性。可选择项包括：FetchType.EAGER和FetchType.LAZY。前者表示关系类在主体类加载的时候同时加载，后者表示关系类在被访问时才加载。默认值是FetchType.LAZY。

5）optional：表示被维护对象是否需要存在。如果为真，说明card属性可以null，也就是允许没有身份证，未成年人就是没有身份证。

@OneToOne注释指明Card与User为一对一关系，Card是关系被维护端，optional=false设置user属性值不能为空，也就是身份证必须有对应的主人。@JoinColumn(name=”user_id” referencedColumnName=”id” unique=”true”)指明tbl_card表的user_id列作为外键与tbl_user表的person_id列进行关联，unique=true指明user_id列的值不可重复。

**@OneToMany**
**@ManyToOne**
**@ManyToMany**
an*
*
