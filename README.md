
<div align="center">
    <img src="https://cdn.learnku.com/uploads/images/202009/27/38389/WFQxJ7qZ1k.png!large" height="80"> 
</div>
<br>
<p align="center"><code>Dcat Admin</code> is based on <a href="https://www.laravel-admin.org/" target="_blank">laravel-admin</a> Second development from the backend system builder, with very little code to quickly build a fully functional backend system of high value. Built with a wealth of common backend components, out of the box, allowing developers to say goodbye to redundant HTML code, very friendly to back-end developers.</p>

<p align="center">
<a href="https://learnku.com/docs/dcat-admin/1.x">learnku文档</a> |
<a href="http://www.dcatadmin.com/">Homepage</a> |
<a href="http://103.39.211.179:8080/admin">Demo (Live)</a> |
<a href="https://github.com/jqhph/dcat-admin-demo">Demo source code</a> |
<a href="https://gitee.com/jqhph/dcat-admin-demo">Demo source code (Gitee)</a> |
<a href="#extensions">Extensions</a>
</p>

<p align="center">
    <a href="https://github.com/jqhph/dcat-admin/blob/master/LICENSE"><a href="https://opencollective.com/dcat-admin" alt="Financial Contributors on Open Collective"><img src="https://opencollective.com/dcat-admin/all/badge.svg?label=financial+contributors" /></a> <img src="https://img.shields.io/badge/license-MIT-7389D8.svg?style=flat" ></a>
    <a href="https://travis-ci.org/jqhph/dcat-admin">
        <img src="https://travis-ci.org/jqhph/dcat-admin.svg?branch=master" alt="Build Status">
    </a>
    <a href="https://styleci.io/repos/182349597">
        <img src="https://github.styleci.io/repos/182349597/shield" alt="StyleCI">
    </a>
    <a href="https://packagist.org/packages/dcat/laravel-admin" ><img src="https://poser.pugx.org/dcat/laravel-admin/v/stable" /></a> 
    <a href="https://packagist.org/packages/dcat/laravel-admin"><img src="https://img.shields.io/packagist/dt/dcat/laravel-admin.svg?color=" /></a> 
    <a><img src="https://img.shields.io/badge/php-7.1+-59a9f8.svg?style=flat" /></a> 
    <a><img src="https://img.shields.io/badge/laravel-5.5+-59a9f8.svg?style=flat" ></a>
</p>

## 截图

![](https://cdn.learnku.com/uploads/images/202008/23/38389/Oam6CYOobf.jpeg!large)
![](https://cdn.learnku.com/uploads/images/202007/24/38389/35KJXfVXib.png!large)
![](https://cdn.learnku.com/uploads/images/202008/23/38389/Lu7LZDSX0M.jpg!large)
![](https://cdn.learnku.com/uploads/images/202004/24/38389/GBkt9jYnW0.png!large)
![](https://cdn.learnku.com/uploads/images/202008/08/38389/lGYIdhifb5.jpg!large)


## Features

- [x] Simple, elegant, flexible and extensible APIs
- [x] User management
- [x] RBAC rights management, support for unlimited rights nodes
- [x] Menu management
- [x] using pjax to build refresh-free pages, support for ** load on demand ** static resources, can be infinitely expandable components without affecting overall performance
- [x] Loosely coupled page building and data manipulation design with easy switching of data sources
- [x] Custom pages
- [x] Customize theme coloring
- [x] Multi-themes switching function, built-in multiple theme colors
- [x] Easily build standalone pages without a menu bar (e.g. for building pop-up selectors, etc.)
- [x] Plug-in functionality
- [x] Visual code generator to generate add/drop pages from data tables with one click
- [x] Data table builder with a wealth of common table features (e.g. combobox headers, data export, search, quick creation, batch operations, etc.)
- [x] Tree table feature builder with pagination and click-to-load support
- [x] Data form builder with rich built-in form types and support for asynchronous form submission
- [x] Step-by-step form builder
- [x] Pop-up form builder
- [x] Data detail page builder
- [x] Infinite hierarchical tree page builder with drag-and-drop support for data hierarchy, sorting, etc.
- [x] Rich set of frequently used page components (e.g. charts, statistics cards, drop-down menus, tab cards, hint tools, etc.) built in
- [x] `Section` function (similar to `Filter` of `Wordpress` and `section` tab of `blade` template).
- [x] Asynchronous file upload form, support block multi-threaded uploading
- [x] Multi-application
- [ ] Plug-in market, you can install, update and uninstall plug-ins with a single click of the mouse on the administration page.


## Requirements
 - PHP >= 7.1.0
 - Laravel 5.5.0 ~ 8.*
 - Fileinfo PHP Extension

## Installation

> If `composer` downloads too slowly or fails to install, run the command `composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/`

First, you need to install `laravel`. If you already have it installed, you can skip this step.
```bash
composer create-project --prefer-dist laravel/laravel ProjectName 7.*
# or
composer create-project --prefer-dist laravel/laravel ProjectName
```

After installing `laravel`, you will need to modify the `.env` file to set the database connection to the correct settings:

```dotenv
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=dcat-admin
DB_USERNAME=root
DB_PASSWORD=
```

Installation `dcat-admin`


```
cd {ProjectName}

composer require dcat/laravel-admin
```

Then run the following command to publish the resource:

```
php artisan admin:publish
```

The command will generate the configuration file `config/admin.php`, in which you can modify the installation address, database connection, and table name. It is recommended that all the default configuration is not modified.

Then run the following command to complete the installation:

```
php artisan admin:install
```

After the above steps are completed, you can configure the webserver, ** Note that you need to point the document root to the `public` directory**! If you are using `nginx`, you also need to add a pseudo-static configuration to the configuration.

```dotenv
location / {
	try_files $uri $uri/ /index.php?$query_string;
}
```

After starting the service, open `http://localhost/admin` in your browser and log in with the username `admin` and password `admin`.


<a name="extensions"></a>
## Extensions

| Extension                                       | Description                             | dcat-admin Version                           |
| ------------------------------------------------ | ---------------------------------------- |---------------------------------------- |
| [dcat-page](https://github.com/jqhph/dcat-page)    | 简洁的静态站点构建工具 | * |
| [ueditor](https://github.com/jqhph/dcat-admin-ueditor) | 百度在线编辑器     | * |
| [grid-sortable](https://github.com/jqhph/dcat-admin-grid-sortable) | 表格拖曳排序工具      | * |


## Thanks
`Dcat Admin` is based on the following components:

+ [Laravel](https://laravel.com/)
+ [Laravel Admin](https://www.laravel-admin.org/)
+ [AdminLTE3](https://github.com/ColorlibHQ/AdminLTE)
+ [bootstrap4](https://getbootstrap.com/)
+ [jQuery3](https://jquery.com/)
+ [Eonasdan Datetimepicker](https://github.com/Eonasdan/bootstrap-datetimepicker/)
+ [font-awesome](http://fontawesome.io)
+ [jquery-form](https://github.com/jquery-form/form)
+ [moment](http://momentjs.com/)
+ [webuploader](http://fex.baidu.com/webuploader/)
+ [jquery-pjax](https://github.com/defunkt/jquery-pjax)
+ [Nestable](http://dbushell.github.io/Nestable/)
+ [toastr](http://codeseven.github.io/toastr/)
+ [editor-md](https://github.com/pandao/editor.md)
+ [fontawesome-iconpicker](https://github.com/itsjavi/fontawesome-iconpicker)
+ [layer弹出层](http://layer.layui.com/)
+ [char.js](https://www.chartjs.org)
+ [nprogress](https://ricostacruz.com/nprogress/)
+ [bootstrap-validator](https://github.com/1000hz/bootstrap-validator)
+ [Google map](https://www.google.com/maps)
+ [Tencent map](http://lbs.qq.com/)

## Contributors

### Code Contributors

This project exists thanks to all the people who contribute. [[Contribute](CONTRIBUTING.md)].
<a href="https://github.com/jqhph/dcat-admin/graphs/contributors"><img src="https://opencollective.com/dcat-admin/contributors.svg?width=890&button=false" /></a>

### Financial Contributors

Become a financial contributor and help us sustain our community. [[Contribute](https://opencollective.com/dcat-admin/contribute)]

#### Individuals

<a href="https://opencollective.com/dcat-admin"><img src="https://opencollective.com/dcat-admin/individuals.svg?width=890"></a>

#### Organizations

Support this project with your organization. Your logo will show up here with a link to your website. [[Contribute](https://opencollective.com/dcat-admin/contribute)]

<a href="https://opencollective.com/dcat-admin/organization/0/website"><img src="https://opencollective.com/dcat-admin/organization/0/avatar.svg"></a>
<a href="https://opencollective.com/dcat-admin/organization/1/website"><img src="https://opencollective.com/dcat-admin/organization/1/avatar.svg"></a>
<a href="https://opencollective.com/dcat-admin/organization/2/website"><img src="https://opencollective.com/dcat-admin/organization/2/avatar.svg"></a>
<a href="https://opencollective.com/dcat-admin/organization/3/website"><img src="https://opencollective.com/dcat-admin/organization/3/avatar.svg"></a>
<a href="https://opencollective.com/dcat-admin/organization/4/website"><img src="https://opencollective.com/dcat-admin/organization/4/avatar.svg"></a>
<a href="https://opencollective.com/dcat-admin/organization/5/website"><img src="https://opencollective.com/dcat-admin/organization/5/avatar.svg"></a>
<a href="https://opencollective.com/dcat-admin/organization/6/website"><img src="https://opencollective.com/dcat-admin/organization/6/avatar.svg"></a>
<a href="https://opencollective.com/dcat-admin/organization/7/website"><img src="https://opencollective.com/dcat-admin/organization/7/avatar.svg"></a>
<a href="https://opencollective.com/dcat-admin/organization/8/website"><img src="https://opencollective.com/dcat-admin/organization/8/avatar.svg"></a>
<a href="https://opencollective.com/dcat-admin/organization/9/website"><img src="https://opencollective.com/dcat-admin/organization/9/avatar.svg"></a>

## License
------------
`dcat-admin` is licensed under [The MIT License (MIT)](LICENSE).
