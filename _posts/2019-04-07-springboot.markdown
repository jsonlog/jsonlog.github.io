---
layout: post
title:  "Springboot"
# date:   2018-04-07
categories: jekyll snippets
---
# Gradle

```Gradle
buildscript {
    repositories {
        maven { url "http://repo.spring.io/snapshot" }
        maven { url "http://repo.spring.io/milestone" }
    }
 
    dependencies {
        classpath("org.springframework.boot:spring-boot-gradle-plugin:1.4.1.BUILD-SNAPSHOT")
    }
}
 
apply plugin: 'java'
apply plugin: 'spring-boot'
 
repositories {
    maven { url "http://repo.spring.io/snapshot" }
    maven { url "http://repo.spring.io/milestone" }
}
 
dependencies {
    compile("org.springframework.boot:spring-boot-starter-web")
    testCompile("org.springframework.boot:spring-boot-starter-test")
}
```
# Maven
```Maven
<！ - 从Spring Boot继承默认值 - > 
<parent> 
	<groupId> org.springframework.boot </ groupId> 
	<artifactId> spring-boot-starter-parent </ artifactId> 
	<version> 2.0.1.RELEASE < / version> 
</ parent>

<!-- 可以在自己的项目中通过覆盖属性来覆盖个别的依赖。例如，要升级到另一个Spring Data发行版，您需要将以下内容添加到您的pom.xml-->
<pre class="programlisting"><span class="hl-tag"><properties> </span>
    <span class="hl-tag"><spring-data- </span><span class="hl-tag">releasetrain.version></span> Fowler-SR2 <span class="hl-tag"></spring-data-releasetrain.version> 
</span><span class="hl-tag"></ properties></span></pre>
```


# 自定义SpringApplication
```Java
public static void main(String[] args) {
    SpringApplication app = new SpringApplication(MySpringConfiguration.class);
    app.setBannerMode(Banner.Mode.OFF);
    app.run(args);
}
//or
new SpringApplicationBuilder()
        .sources(Parent.class)
        .child(Application.class)
        .bannerMode(Banner.Mode.OFF)
        .run(args);
```

