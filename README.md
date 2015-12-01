sass sprite 封装
----
瞎搞

## 使用
```scss
@charset "utf-8";
@import "compass";
@import "pc-sprite";

$icon-dir1: 'event/thanksgiving/en/icon';
$icon-dir2: 'event/thanksgiving/fr/icon';

%inline-block{
    @include inline-block;
}

%icon-sprite1{
    @extend %inline-block;
    @include _pc-sprite($icon-dir1);
}

%icon-sprite2{
    @extend %inline-block;
    @include _pc-sprite($icon-dir1);
}

// 导出目录下所有精灵图样式
//     写第2个参数为了避免冗余代码，可选
@include pc-sprite-all($icon-dir1 ,'%icon-sprite1');
@include pc-sprite-all($icon-dir2 ,'%icon-sprite2');

.one{
    // 输出单张
    @include pc-sprite($icon-dir1 ,'one');
    width: pc-sprite-width($icon-dir1 ,'one');
    height: pc-sprite-height($icon-dir1 ,'one');
}

/* 用例未经测试 */
```