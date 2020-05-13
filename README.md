# zuka

Header(頭) 的修改位置

```
1.assets
2.js
3.main.js
4.$headerTotalHeaight = $headerPosition + $mainHeaderHeight
5.搜索下一個修改JS
```	
商品詳情修改

```
button 下一個（在<div class="product-gallery__nav-image">下新增）

<div class="row hidden-xs-down" style="text-align: center; ">
      <div class="col pb--20" style="font-size: 24px;">
           <button onclick="product_detail_next()" class="action-btn-2 ">
	      <i class="fa fa-angle-up fa-lg"></i>
           </button>
       </div>
</div>

button 上一個

<div class="row hidden-xs-down" style="text-align: center">
     <div class="col " style="font-size: 24px;">
          <button onclick="product_detail_prev()" class="action-btn-2 ">
	      <i class="fa fa-angle-down fa-lg"></i>
	  </button>
     </div>
</div>

img 變小利用 pr--85 pl--85 加在img的class中

<div class="product-gallery__large-image mb-md--30">
     <div class="product-gallery__wrapper">
          <div class="zuka-element-carousel main-slider image-popup"
                    data-slick-options='{
                    "slidesToShow": 1,
                    "slidesToScroll": 1,
                    "infinite": true,
                    "arrows": false, 
                    "asNavFor": ".nav-slider"
                    }'>
                <figure class="product-gallery__image zoom pr--85 pl--85">
                     <img src="assets/img/products/prod-14-1.jpg" alt="Product">
                </figure>
                <figure class="product-gallery__image zoom pr--85 pl--85">
                    <img src="assets/img/products/prod-13-1.jpg" alt="Product">
                </figure>
                <figure class="product-gallery__image zoom pr--85 pl--85">
                    <img src="assets/img/products/prod-13-2.jpg" alt="Product">
                </figure>
                <figure class="product-gallery__image zoom pr--85 pl--85">
                    <img src="assets/img/products/prod-12-1.jpg" alt="Product">
                </figure>
         </div>
         <div class="product-gallery__actions pr--85" style="bottom: 0px !important;">
              <button class="action-btn-2 btn-zoom-popup">
                    <i class="dl-icon-zoom-in"></i>
              </button>
         </div>
    </div>
</div>
   
   新增css

<style>
        @media (min-width:921px) {
            .hidden-xs-up {
                display: none !important;
            }

            .cellphone.slick-btn.slick-prev.slick-arrow {
                display: none !important;
            }

            .cellphone.slick-btn.slick-next.slick-arrow {
                display: none !important;
            }
        }

        @media (max-width: 920px) {
            .hidden-xs-down {
                display: none !important;
            }
        }
    </style>

新增js

<script>
        function product_detail_prev() {
            $(".cellphone.slick-btn.slick-prev").click();
        }

        function product_detail_next() {
            $(".cellphone.slick-btn.slick-next").click();
        }
 </script>
```
購物車修改（原本在main.js 中的Product Quantity註解）

```
<td class="product-quantity">
    <div class="quantity">
    	<input type="number" class="quantity-input"  name="amount" id="product_id" value="1" min="1">
        <div class="dec qtybutton change">-</div>
        <div class="inc qtybutton change">+</div>
    </div>
</td>
<script>
        $(".change").on("click", function () {                                                                         
            var $button = $(this);
            var oldValue = $button.parent().find("input").val();
            if ($button.hasClass("inc")) {
                var newVal = parseFloat(oldValue) + 1;
            } else {
                if (oldValue > 1) {
                    var newVal = parseFloat(oldValue) - 1;
                } else {
                    newVal = 1;
                }
            }
            $('#product_id').val(newVal);
        });	
    </script>
```
手機版左側導覽 無限階層

```
<ul class="sub-menu">
	<li class="menu-item-has-children">
	    <a href="#"> <span class="mm-text">第一層</span></a>
		<ul class="sub-menu">
		   <li class="menu-item-has-children">
			<a href="shop-fullwidth.html"><span class="mm-text">第二層</span></a>
		          <ul class="sub-menu">
			      <li class="menu-item-has-children">
				<a href="shop-fullwidth.html"><span class="mm-text">第三層</span></a>
			      </li>
			  </ul>
		   </li>
	       </ul>
	</li>
</ul>
```

電腦網頁左側導覽 無限階層

```
<ul class="megamenu four-column"  style="padding: 30px 45px !important;min-width: 10px !important">
 	<li style="min-width: 135px !important">
        <ul>
            <li id="main_01">
                <a href="">
                    <span class="mm-text">
                        <h5><b>所有商品</b></h5>
                    </span>
                </a>
            </li>
            <li id="main_02">
                <a href="">
                    <span class="mm-text">
                        <h5><b>明星商品 </b></h5>
                    </span>
                </a>
            </li>
            <li id="main_03">
                <a href="">
                    <span class="mm-text">
                        <h5><b>一般商品 </b></h5>
                    </span>
                </a>
            </li>
            <li id="main_04">
                <a href="">
                    <span class="mm-text">
                        <h5><b>積分商品 </b></h5>
                    </span>
                </a>
            </li>
            <script>
                $("#main_01").hover(function () {
                    $("#main_child_01").css('display', 'block')
                }, function () {
                    $("#main_child_01").css('display', 'none')
                });
                $("#main_02").hover(function () {
                    $("#main_child_02").css('display', 'block')
                }, function () {
                    $("#main_child_02").css('display', 'none')
                });
                $("#main_03").hover(function () {
                    $("#main_child_03").css('display', 'block')
                }, function () {
                    $("#main_child_03").css('display', 'none')
                });
                $("#main_04").hover(function () {
                    $("#main_child_04").css('display', 'block')
                }, function () {
                    $("#main_child_04").css('display', 'none')
                });
            </script>
        </ul>
    </li>
    <li id="main_child_01" style="min-width: 290px !important;display: none;">
        <ul>
            <div class="row">
                <div class="col-xl-12">
                    <li>
                        <a href="">
                            <span class="mm-text">
                                <h5><b>中類別01</b></h5>
                            </span>
                        </a>
                    </li>
                    <div class="row">
                        <div class="col-xl-12" style="padding-right: 0px;">
                            <ul>
                                <li  style="float: left !important;padding-right:5px;">
                                    <a style="padding:0px;" href="">小類別02</a>
                                </li>
                                <li  style="float: left !important;padding-right:5px;">
                                        <a style="padding:0px;" href="">小類別03</a>
                                </li>
                                <li style="float: left !important;padding-right:5px;">
                                    <a style="padding:0px;" href="">小類別04</a>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </ul>
        <script>
            $("#main_child_01").hover(function () {
                $("#main_child_01").css('display', 'block')
            }, function () {
                $("#main_child_01").css('display', 'none')
            });
        </script>
    </li>
    <li id="main_child_02" style="min-width: 290px !important;display: none;">
        <ul>
            <div class="row">
                <div class="col-xl-12">
                    <li>
                        <a href="">
                            <span class="mm-text">
                                <h5><b>中類別02</b></h5>
                            </span>
                        </a>
                    </li>
                    <div class="row">
                        <div class="col-xl-12" style="padding-right: 0px;">
                            <ul>
                                <li
                                    style="float: left !important;padding-right:5px;">
                                    <a style="padding:0px;" href="">
                                        小類別03
                                    </a>
                                </li>
                                <li
                                    style="float: left !important;padding-right:5px;">
                                    <a style="padding:0px;" href="">
                                        小類別04
                                    </a>
                                </li><li
                                style="float: left !important;padding-right:5px;">
                                <a style="padding:0px;" href="">
                                    小類別05
                                </a>
                            </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </ul>
        <script>
            $("#main_child_01").hover(function () {
                $("#main_child_01").css('display', 'block')
            }, function () {
                $("#main_child_01").css('display', 'none')
            });
        </script>
    </li>
    <li id="main_child_03"  style="min-width: 290px !important;display: none;">
        <ul>
            <div class="row">
                <div class="col-xl-12">
                    <li>
                        <a href="">
                            <span class="mm-text">
                                <h5><b>中類別03</b></h5>
                            </span>
                        </a>
                    </li>
                    <div class="row">
                        <div class="col-xl-12" style="padding-right: 0px;">
                            <ul>
                                <li
                                    style="float: left !important;padding-right:5px;">
                                    <a style="padding:0px;" href="">
                                        小類別04
                                    </a>
                                </li>
                                <li
                                    style="float: left !important;padding-right:5px;">
                                    <a style="padding:0px;" href="">
                                        小類別05
                                    </a>
                                </li>
                                <li
                                    style="float: left !important;padding-right:5px;">
                                    <a style="padding:0px;" href="">
                                        小類別06
                                    </a>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </ul>
        <script>
            $("#main_child_03").hover(function () {
                $("#main_child_03").css('display', 'block')
            }, function () {
                $("#main_child_03").css('display', 'none')
            });
        </script>
    </li>
    <li id="main_child_04"  style="min-width: 290px !important;display: none;">
        <ul>
            <div class="row">
                <div class="col-xl-12">
                    <li>
                        <a href="">
                            <span class="mm-text">
                                <h5><b>中類別04</b></h5>
                            </span>
                        </a>
                    </li>
                    <div class="row">
                        <div class="col-xl-12" style="padding-right: 0px;">
                            <ul>
                                <li
                                    style="float: left !important;padding-right:5px;">
                                    <a style="padding:0px;" href="">
                                        小類別05
                                    </a>
                                </li>
                                <li
                                    style="float: left !important;padding-right:5px;">
                                    <a style="padding:0px;" href="">
                                        小類別05
                                    </a>
                                </li>
                                <li
                                    style="float: left !important;padding-right:5px;">
                                    <a style="padding:0px;" href="">
                                        小類別06
                                    </a>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </ul>
        <script>
            $("#main_child_04").hover(function () {
                $("#main_child_04").css('display', 'block')
            }, function () {
                $("#main_child_04").css('display', 'none')
            });
        </script>
    </li>
    <!-- 圖片 -->
    <li class="banner-holder" style="padding-left: 20px;">
        <div class="megamenu-banner">
            <div class="megamenu-banner-image"
                style="background: url(assets/img/banner/about_1.jpg)no-repeat scroll center/cover;">
            </div>
            <div class="megamenu-banner-info">
                <span>Autumn Winter 2019</span>
                <h3>new <strong>arrival</strong></h3>
            </div>
        </div>
    </li>                                               
 </ul>
```
```
商品詳情   - 1  +   修改版

<div class="col-md-6 product-main-details mt--55 mt-sm--25 ">
                                    <div class="product-summary">
                                        <div class="clearfix"></div>
                                        <h3 class="product-title mb--20 mb-lg--20 mb-sm--10 pt--10 pr--10 pl--10s"
                                            style="font-weight: bold;">抗皺奇蹟活膚霜 50g</h3>
                                        <p class="mb--0" style="font-weight: bold;color: black;">容量：</p>    
                                        <p style="margin-bottom: 3rem !important;">料號：</p>
                                        <div class="product-price-wrapper float-left mb--30 mb-lg--20 mb-sm--10  ">
                                            <span class="product-price-new pr--20">
                                                <span class="money" style="font-weight: bold;">定價NT.2380</span>
                                            </span>
                                            <span class="product-price-new">
                                                <span class="money" style="font-weight: bold;">會員價NT.1980</span>
                                            </span>
                                        </div>
                                        <div class="clearfix"></div>
                                        <div class="selectPopupBox-wrapper popup-wrapper" style="width: 35rem;">
                                            <p>請選擇數量</p>
                                            <div class="row">
                                                <div class="col-lg-3 col-sm-6">
                                                </div>
                                                <div class="col-lg-6 col-sm-6 pl--25 pr--65" >
                                                    <div class="quantity" style="width: 100%;">
                                                        <input type="number" class="quantity-input"  name="amount" id="product_id" value="1" min="1">
                                                        <div class="dec qtybutton change" style="font-size: 30px;">
                                                            <i class="fa fa-minus-square"></i>
                                                        </div>
                                                        <div class="inc qtybutton change"  style="font-size: 30px;">
                                                            <i class="fa fa-plus-square"></i>
                                                        </div>
                                                    </div>
                                                </div>
                                                <div class="col-lg-3 col-sm-6"></div>
                                            </div>
                                            <div class="selectPopupBox-buttonbox button-full"
                                                style="padding: 3px !important;">
                                                <button type="button" class="btn  btn-style-1  add-to-cart pr--20 pl--20"
                                                    style="width:150px;height:40px; border-radius: 0.8rem;">加入購物車
                                                </button> &nbsp;
                                                <button type="button" class="btn  btn-style-1  add-to-cart"
                                                    style="width:150px;height:40px; border-radius: 0.8rem;">&nbsp; 立即結帳
                                                    &nbsp;&nbsp;
                                                </button>
                                            </div>
                                            <!-- <div class="col-lg-6 col-sm-6">
                                                    <button type="button"
                                                        class="btn btn-style-1 btn-semi-large btn-shape-round add-to-cart"
                                                        style="margin-bottom: 2rem;border-radius: 0.8rem;width: 100%;padding: 0px 55px;"
                                                        onclick="add('<?php echo $detail['data']['product_id'];?>','detail_qty_<?php echo $detail['data']['product_id'];?>','<?php echo $product_belong; ?>')">
                                                        加入購物車
                                                    </button>
                                                </div>
                                                <div class="col-lg-6 col-sm-6 pl--0">
                                                    <button type="button"
                                                        class="btn btn-style-1 btn-semi-large btn-shape-round add-to-cart"
                                                        style="margin-bottom: 2rem;border-radius: 0.8rem;width: 100%;padding: 0px 55px;"
                                                        onclick="add('<?php echo $detail['data']['product_id'];?>','detail_qty_<?php echo $detail['data']['product_id'];?>','<?php echo $product_belong; ?>')">
                                                        立即結帳
                                                    </button>
                                                </div> -->
                                            <!-- <div class="pb--10" >                                                
                                                <form class="form--action">
                                                    <div class="product-action d-flex align-items-center " >
                                                        <td class="product-quantity" >
                                                            <div class="quantity" >
                                                                <input type="number" class="quantity-input"  name="amount" id="product_id" value="1" min="1">
                                                                <div class="dec qtybutton change" >-</div>
                                                                <div class="inc qtybutton change" >+</div>
                                                            </div>
                                                        </td>                                                                                               
                                                    </div>      
                                                </form>
                                            </div> -->
                                            <!-- style="border-color:#CECECE;border-style:solid;" 購物車邊框 -->
                                            <!-- <div class="selectPopupBox-numberBox flexbox pb--10 product-action d-flex align-items-center quantity">                                                
                                                <i class=" dec qtybutton change"></i>
                                                <input type="number" class="selectPopupBox-amountBox amountBox text-smail" style="text-align: center;" value="1" max="15"
                                                     name="">
                                                <i class=" inc qtybutton change" style="padding-left: 80px !important;"></i>
                                            </div> -->

                                        </div>
                                        <div class="product-meta mt--35 mt-lg--25 mt-sm--15 pt-sm--1 pl--1 pr--20"
                                            style="width: 35rem;">
                                            <div class="accordion__single mb--30 mb-sm--20" style="border-bottom-width: 1px !important;
                                            border-bottom-style: solid !important">
                                                <div class="accordion__header" id="headingOne"
                                                    style="font-weight: bold;">
                                                    <h4 class="accordion__link" data-target="#accordionOne">
                                                        商品介紹
                                                    </h4>
                                                </div>
                                                <div id="accordionOne" class="accordion__body hide-in-default">
                                                    <div class="accordion__text">
                                                        結合日本柚子萃取精華<br>
                                                        天然植萃成分以及草本浮游精萃<br>
                                                        只要10分鐘<br>
                                                        就能讓肌膚宛如一夜好眠的膨潤、自然健康狀態。<br>
                                                        其療癒、舒緩的天然植萃香氛<br>
                                                        更能有助提升睡眠品質和放鬆身心靈的狀態！<br>
                                                        豐潤肌膚並保濕<br>
                                                    </div>
                                                </div>
                                            </div>
                                            <div class="accordion__single mb--30 mb-sm--20" style="border-bottom-width: 1px !important;
                                            border-bottom-style: solid !important">
                                                <div class="accordion__header" id="headingTwo">
                                                    <h4 class="accordion__link" data-target="#accordionTwo">
                                                        使用方法
                                                    </h4>
                                                </div>
                                                <div id="accordionTwo" class="accordion__body hide-in-default">
                                                    <div class="accordion__text">
                                                        結合日本柚子萃取精華<br>
                                                        天然植萃成分以及草本浮游精萃<br>
                                                        只要10分鐘<br>
                                                        就能讓肌膚宛如一夜好眠的膨潤、自然健康狀態。<br>
                                                        其療癒、舒緩的天然植萃香氛<br>
                                                        更能有助提升睡眠品質和放鬆身心靈的狀態！<br>
                                                        豐潤肌膚並保濕<br>
                                                    </div>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                </div>
```
