# Basic flexbox grid in SCSS from [this source](https://product.voxmedia.com/2017/5/22/15655480/building-the-vox-media-video-microsite)

* [alternative simple grid](https://github.com/zachacole/Simple-Grid/blob/master/simple-grid.css)

```
$m: 700px;

@mixin flexbox() {
  display: -webkit-box;
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
  -webkit-flex-wrap: wrap;
  -ms-flex-wrap: wrap;
  flex-wrap: wrap;
}

@mixin layout-justify {
  $justify: start, end, center, between, around;
  @each $value in $justify {
    .layout-justify-#{$value} {
      -webkit-justify-content: #{$value};
      -ms-justify-content: #{$value};
      justify-content: #{$value};
    }
  }
}

@mixin flex-basis {
  $widths: 25, 30, 50, auto;
  @each $width in $widths {
    @if $width == auto {
      .layout-width-auto {
        -webkit-flex-basis: $width;
        -ms-flex-basis: $width;
        flex-basis: $width;
      }
    } @else {
      .layout-width-#{$width} {
        -webkit-flex-basis: percentage($width/100);
        -ms-flex-basis: percentage($width/100);
        flex-basis: percentage($width/100);
      }
    }
  }
}

@supports(display: flex){
  @media screen and (min-width: $m) {
    .layout-container {
      @include flexbox();
    }
  }
  @include layout-justify();
  @include flex-basis();
}
```