
<div align="center">
    <img src="https://cdn.learnku.com/uploads/images/202009/27/38389/WFQxJ7qZ1k.png!large" height="80"> 
</div>
<br>

<p align="center">
    <a href="https://github.com/jqhph/dcat-admin/actions">
        <img src="https://github.com/jqhph/dcat-admin/workflows/Laravel%20Dusk/badge.svg" alt="Build Status">
    </a>
    <a href="https://styleci.io/repos/182349597">
        <img src="https://github.styleci.io/repos/182349597/shield" alt="StyleCI">
    </a>
    <a href="https://packagist.org/packages/dcat/laravel-admin" ><img src="https://poser.pugx.org/dcat/laravel-admin/v/stable" /></a> 
    <a href="https://packagist.org/packages/dcat/laravel-admin"><img src="https://img.shields.io/packagist/dt/dcat/laravel-admin.svg?color=" /></a> 
    <a><img src="https://img.shields.io/badge/php-7.1+-59a9f8.svg?style=flat" /></a> 
    <a><img src="https://img.shields.io/badge/laravel-5.5+-59a9f8.svg?style=flat" ></a>
</p>

<p align=""><code>Dcat Admin</code> is a backend system building tool based on <a href="https://www.laravel-admin.org/" target="_blank">laravel-admin</a>, which requires very little code to quickly build a fully functional and high value backend system. Built-in rich backend common components, easy to use out of the box, so that developers can say goodbye to tedious HTML code, very friendly to back-end developers.</p>


- [Official Website (Chinese)](http://www.dcatadmin.com)
- [Chinese Documentation](https://learnku.com/docs/dcat-admin)
- [English Documentation](http://www.dcatadmin.com/docs/en-2.x/quick-start.html)
- [Demo / 在线演示](http://103.39.211.179:8080/admin)
- [Demo source code](https://github.com/jqhph/dcat-admin-demo)
- [Demo Source Code (Code Cloud)](https://gitee.com/jqhph/dcat-admin-demo)
- [Extensions](#)


![](https://cdn.learnku.com/uploads/images/202101/28/38389/YLmL7PLqH7.png!large)


### Features

- [x] Simple, elegant, flexible and extensible API
- [x] User management
- [x] RBAC privilege management with infinite privilege node support
- [x] Menu management
- [x] Build refreshless pages with pjax, support **load-on-demand** static resources, infinitely extendable components without affecting overall performance
- [x] Loosely coupled page construction and data manipulation design, easy to switch data sources
- [x] Customized pages
- [x] Customizable theme color scheme
- [x] Multi-theme switching with multiple theme colors built-in
- [x] Easily build standalone pages without menu bar (e.g. for building popup selectors, etc.)
- [x] Plugin functionality
- [x] Visual code builder to generate add, delete, and check pages based on data tables with one click
- [x] Data table builder with built-in rich table common functions (such as combined table headers, data export, search, quick creation, batch operations, etc.)
- [x] Tree table function builder with support for paging and click-to-load
- [x] Data form builder with rich built-in form types and support for asynchronous form submission
- [x] Step-by-step form builder
- [x] Popup form builder
- [x] Data detail page builder
- [x] Infinite hierarchical tree page builder with drag-and-drop support for hierarchical, sorting and other data operations
- [x] Rich built-in common page components (such as charts, stats cards, drop-down menus, tab cards, hint tools, etc.)
- [x] `Section` function (similar to `Filter` of `Wordpress` and `section` tag of `blade` template)
- [x] Asynchronous file upload form, support for chunked multi-threaded uploads
- [x] Multi-application
- [ ] Plugin marketplace, you can install, update and uninstall plugins with just a click of the mouse on the admin page


### Environment
 - PHP >= 7.1.0
 - Laravel 5.5.0 ~ 9.*
 - Fileinfo PHP Extension

### Installation

> If `composer` download is too slow or installation fails during installation, please run the command `composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/` to replace the `composer` image with AliCloud image.

First you need to install `laravel` framework, you can skip this step if it is already installed. If you are using `laravel` for the first time, please make sure to read the documentation first [Installation `Laravel Documentation`].(https://laravel.com/docs/9.x/) ！
```bash
composer create-project --prefer-dist laravel/laravel ProjectName 9.*
# or
composer create-project --prefer-dist laravel/laravel ProjectName
```

After installing `laravel`, you need to modify the `.env` file to set the database connection settings correctly

```dotenv
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=dcat-admin
DB_USERNAME=root
DB_PASSWORD=
```

Installation`dcat-admin`


```
cd {ProjectName}

composer require dcat/laravel-admin
```

Then run the following command to publish the resource：

```
php artisan admin:publish
```

The command will generate a configuration file `config/admin.php`, in which you can modify the installation address, database connection, and table name, and it is recommended to use the default configuration without modification.

Then run the following command to complete the installation.

> Executing this command may result in the following error `Specified key was too long ... 767 bytes`, if this error occurs, please add the code \Schema::defaultStringLength(191);` to the \boot` method in the `app/Providers/AppServiceProvider.php` file, then delete all the data tables in the database, and then then delete all the data tables in the database and run the `php artisan admin:install` command again.

```
php artisan admin:install
```

After the above steps are completed you can configure the `web` service, **Note that you need to point the `web` directory to the `public` directory**! If you are using `nginx`, you also need to add pseudo-static configuration to the configuration

```dotenv
location / {
	try_files $uri $uri/ /index.php?$query_string;
}
```

After starting the service, open `http://localhost/admin` in your browser and log in with the username `admin` and password `admin`.


<a name="extensions"></a>
### Extensions

| Extension                                        | Description                              | dcat-admin Versions                             |
| ------------------------------------------------ | ---------------------------------------- |---------------------------------------- |
| [mosiboom/dcat-iframe-tab](https://github.com/mosiboom/dcat-iframe-tab)    | IFRAME TAB标签切换 | 2.x |
| [super-eggs/dcat-distpicker](https://github.com/super-eggs/dcat-distpicker)    | 省市区联动 | 2.x |
| [ueditor](https://github.com/jqhph/dcat-admin-ueditor) | Baidu Online Editor     | 1.x |
| [grid-sortable](https://github.com/jqhph/dcat-admin-grid-sortable) | Table Drag & Drop Sorting      | 1.x |


### Acknowledgements
`Dcat Admin` Based on the following components:

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

### Contributors

#### Code Contributors

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

### License
------------
`dcat-admin` is licensed under [The MIT License (MIT)](LICENSE).
