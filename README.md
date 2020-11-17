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
在html 中引入 jquery <很重要>

<script src="/assets/js/jquery-3.2.1.min.js"></script>
 
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

商品詳情      -  1   +     修改版

```
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
-  1  +  中 js 
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

footer 新增手機版下拉選單

```
<footer class="footer footer-1 bg-color" style="border-top-style:solid ; border-color:#ccc;">
            <div class="footer-top pt--30 pt-md--60 d-none d-lg-block">
                <div class="container-fluid">
                    <div class="row footer-row">
                        <div class="footer-column footer-column  mb-md--30 ">                          
                            <div class="footer-widget text-center text-sm-left">
                            </div>                         
                        </div>
                        <div class="footer-column footer-column-2  mb-md--25 ">
                            <div class="footer-widget text-center text-sm-left ">
                                <h3 class="widget-title mb--25 mt--15 mb-xs--20 font_white">會員中心</h3>
                                <ul class="widget-menu ">
                                    <li><a class="font_white" href="download_center.html" target="_blank">會員條款</a></li>
                                    <li><a class="font_white" href="download_center.html" target="_blank">下載專區</a></li>
                                </ul>
                            </div>
                        </div>
                        <div class="footer-column footer-column-3 mb-md--25 ">
                            <div class="footer-widget text-center text-sm-left ">
                                <h3 class="widget-title mt--15 mb--25 font_white">購物說明</h3>
                                <ul class="widget-menu">
                                    <li><a class="font_white" href="shopping_guide.html" target="_blank">配送方式</a></li>
                                    <li><a class="font_white" href="shopping_guide.html" target="_blank">付款方式</a></li>
                                    <li><a class="font_white" href="shopping_guide.html" target="_blank">換貨服務</a></li>
                                </ul>
                            </div>
                        </div>
                        <div class="footer-column footer-column-4 mb-md--30 ">
                            <div class="footer-widget text-center text-sm-left">
                                <h3 class="widget-title mt--15 mb--25 font_white">服務時間</h3>
                                <ul class="widget-menu">
                                    <li><span class="font_white">星期一至星期五</span></li>
                                    <li><span class="font_white">08:30 – 17:30</span></li>
                                </ul>
                            </div>
                        </div>
                        <div class="footer-column footer-column ">
                            <div class="footer-widget text-center text-sm-left ">
                                <div class="textwidget mb--10 mb-sm--20">
                                        <a href="index.html" class="footer-logo">
                                            <h3 >昕荋睿</h3>
                                        </a>
                                    </div>
                            <div class="widget_contact_info font_white">
                                <ul>
                                    <li><i class="fa fa-phone "></i><span class="font_white" > 04-25310101</span></li>
                                    <li><i class="fa fa-envelope"></i><a  class="font_white" href=" service@shinglow.com.tw"> service@shinglow.com.tw</a></li>
                                    <li><i class="fa fa-map-marker"></i><span class="font_white">台中市豐原區豐原大道一段647號3樓</span></li>
                                </ul>
                            </div>
                        </div>

                            <div class="footer-widget text-center text-sm-left" style="padding: 4% 0% 12% 0%;">                                
                                <!-- Social Icons Start Here -->
                                <ul class="social social-medium">
                                    <li class="social__item">
                                        <a href="" target="_blank" class="social__link">
                                            <i class="fa fa-twitter font_white"></i>
                                        </a>
                                    </li>
                                    <li class="social__item">
                                        <a href="" target="_blank" class="social__link">
                                            <i class="fa fa-google-plus font_white"></i>
                                        </a>
                                    </li>
                                    <li class="social__item">
                                        <a href="" target="_blank" class="social__link">
                                            <i class="fa fa-facebook font_white"></i>
                                        </a>
                                    </li>
                                    <li class="social__item">
                                        <a href="" target="_blank" class="social__link">
                                            <i class="fa fa-youtube font_white"></i>
                                        </a>
                                    </li>
                                    <li class="social__item">
                                        <a href="header-inner"  target="_blank" class="social__link">
                                            <i class="fa fa-instagram font_white"></i>
                                        </a>
                                    </li>
                                </ul>
                                <!-- Social Icons End Here -->
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="mobile-menu-wrapper">
                <div class="row mb--40 mb-md--20 mb-sm--10">
                    <div class="col-lg-12">
                        <!-- Widget Start Here -->
                        <div class="text-center text-sm-center">
                            <div class="textwidget mt--30 mb--30">
                                <a href="im" class="footer-logo">
                                    <img src="assets/img/logo/logo_2.png"   alt="Logo"  style="width:177px; height: 70px;"/>
                                </a>
                            </div>
                        </div>
                        <!-- Widget End Here -->
                    </div>
                    <div class="col-lg-12">
                        <div class="accordion__single">
                            <div class="accordion__header" id="headingOne">
                                <h4 class="accordion__link" data-target="#accordionOne">
                                    <b>會員中心</b>
                                </h4>
                            </div>
                            <div id="accordionOne" class="accordion__body hide-in-default">
                                <div class="accordion__text">
                                    <a href="">會員條款</a>
                                </div>
                                <div class="accordion__text">
                                    <a href="">下載專區</a>
                                </div>
                            </div>
                        </div>
                        <div class="accordion__single">
                            <div class="accordion__header" id="headingTwo">
                                <h4 class="accordion__link" data-target="#accordionTwo">
                                    <b>購物說明</b>
                                </h4>
                            </div>
                            <div id="accordionTwo" class="accordion__body hide-in-default">
                                <div class="accordion__text">
                                    <a href="">配送方式</a>
                                </div>
                                <div class="accordion__text">
                                    <a href="">付款方式</a>
                                </div>
                                <div class="accordion__text">
                                    <a href="">換貨服務</a>
                                </div>
                            </div>
                        </div>
                        <div class="accordion__single">
                            <div class="accordion__header" id="headingThree">
                                <h4 class="accordion__link" data-target="#accordionThree">
                                    <b>服務時間</b>
                                </h4>
                            </div>
                            <div id="accordionThree" class="accordion__body hide-in-default">
                                <div class="accordion__text">
                                    <a href="">星期一至星期五</a>
                                </div>
                                <div class="accordion__text">
                                    <a href="">08:30 – 17:30</a>
                                </div>
                            </div>
                        </div>
                        <div class="accordion__single">
                            <div class="accordion__header" id="headingFive">
                                <h4 class="accordion__link" data-target="#accordionFive">
                                    <b>聯絡我們</b>
                                </h4>
                            </div>
                            <div id="accordionFive" class="accordion__body hide-in-default">
                                <div class="accordion__text">
                                    <a href="index.html">昕荋睿</a>
                                </div>
                                <div class="accordion__text">
                                    <i class="fa fa-phone"></i><span> &nbsp;04-25310101</span>
                                </div>
                                <div class="accordion__text">
                                    <i class="fa fa-envelope"></i><span> &nbsp; service@shinglow.com.tw</span>
                                </div>
                                <div class="accordion__text">
                                    <i class="fa fa-building"></i><span> &nbsp;台中市豐原區豐原大道一段647號3樓</span>
                                </div>
                           </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="footer-bottom pt--25 pt-sm--35 pb--25 pb-xs--45" style="background-color:#397BAE;">
                <div class="container">
                    <div class="row">
                        <div class="col-12 text-center">
                            <p class="copyright-text " style="color: #fff;">&copy; 2020 昕荋睿 </p>
                        </div>
                    </div>
                </div>
            </div>
        </footer>
```

功能鍵  三 從左到右淡出(css)

```
<style>        
   .side-navigation-wrapper {
       right: unset;
       left: 0 !important;
       -webkit-transform: translateX(-350px);
       -moz-transform: translateX(-350px);
       -ms-transform: translateX(-350px);
       -o-transform: translateX(-350px);
        transform: translateX(-350px);
      }
 </style>
```

修改網頁icom 抓不到的解決方法
```
1.找到 assets/plugins.css 修改路徑

 @font-face {
    font-family: dl-icon;
    src: url(/assets3/fonts/dl-icon.eot?v=1.1.);
    src: url(/assets3/fonts/dl-icon??v=1.1.#iefix) format("embedded-opentype"), url(/assets3/fonts/dl-icon.woff?v=1.1.) format("woff"), url(/assets3/fonts/dl-icon.ttf?v=1.1.) format("truetype"), url(/assets3/fonts/dl-icon.svg?v=1.1) format("svg");
    font-weight: 400;
    font-style: normal
}

2.重新 vagrant reload 即可
```
```
修改商品詳情圖片播放與點擊後的效果

<div class="col-12 pl--0">
     <style>
     .swiper-button {
      z-index: 19;
      top: 50%;
      font-size: 20px;
      line-height: 50px;
      color: #040404;
      background: #fff;
      opacity: 1;
      cursor: pointer;
      margin: 0px;
      transition: all .2s;
      padding: 12px 3px;
      width: auto;
      transform: translate(0, -50%);
      }

      .swiper-button:hover {
            background: #fff;
        }

        .scrollbars::-webkit-scrollbar-track {
            -webkit-box-shadow: inset 0 0 6px rgba(199, 199, 199, 0.3);
            border-radius: 15px;
            background-color: rgba(199, 199, 199, 0.3);
        }

          .scrollbars::-webkit-scrollbar {
              height: 10px;
              background-color: rgba(199, 199, 199, 0.3);
          }

          .scrollbars::-webkit-scrollbar-thumb {
              border-radius: 15px;
              -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, .3);
              background-color: #000000;
          }

          .scrollbars {
              height: 100%;
              width: 100%;
              overflow-x: scroll;
          }

            .mask {
                opacity: 0.3;
            }

      </style>
         <div class="product-image">
             <div class="product-gallery">
                 <div id="details" class="carousel slide carousel-fade"
                     style="padding-left: 1px !important;padding-right: 0px !important;"
                     data-ride="carousel" data-interval="false">
                     <div class="carousel-inner">
                         <div class="carousel-item ca active" id='b1'>
                                 <img src="/assets3/img/list/list01.jpg"
                                     class="d-block w-100 " alt="">
                         </div>
                         <div class="carousel-item ca" id='b2'>
                             <img src="/assets3/img/list/list02.jpg" class="d-block w-100 "
                                 alt="">
                         </div>
                         <div class="carousel-item ca" id='b3'>
                             <img src="/assets3/img/list/list03.jpg" class="d-block w-100 "
                                 alt="">
                         </div>
                     </div>
                     <a class="carousel-control-prev" href="#details" role="button"
                         data-slide="prev">
                         <div class="swiper-button" onclick="mask_ch()"><i
                                 class="fa fa-chevron-left"></i></div>
                     </a>
                     <a class="carousel-control-next" href="#details" role="button"
                         data-slide="next">
                         <div class="swiper-button" onclick="mask_ch()"><i
                                 class="fa fa-chevron-right"></i></div>
                     </a>
                 </div>
             </div>

             <div class="product-gallery__nav-image">
                 <div class="scrollbars" style="overflow-x: auto;overflow-y: hidden;">
                     <table>
                         <tr>
                             <td>
                                 <div style="width: 100px;height: 100px;margin: 10px 0px;"
                                     class="">
                                     <a onclick="carousel_ch(this.id)" id='a_b1'
                                         class="mask">
                                         <img width="100%" src="/assets3/img/list/list01.jpg"
                                             alt="Products"
                                             data-large="/assets3/img/list/list01.jpg"
                                             title="Фото">
                                     </a>
                                 </div>
                             </td>
                             <td>
                                 <div style="width: 100px;height: 100px;">
                                     <a onclick="carousel_ch(this.id)" id='a_b2'
                                         class="mask">
                                         <img width="100%" src="/assets3/img/list/list02.jpg"
                                             alt="Products">
                                     </a>
                                 </div>
                             </td>
                             <td>
                                 <div style="width: 100px;height: 100px;">
                                     <a onclick="carousel_ch(this.id)" id='a_b3'
                                         class="mask">
                                         <img width="100%" src="/assets3/img/list/list03.jpg"
                                             alt="Products">
                                     </a>
                                 </div>
                             </td>
                         </tr>
                     </table>
                 </div>
             </div>
         </div>
      </div>
      例如澄霖的商品詳情
      帶入下列jquery,在網頁上加上ID，css
<script>
    let b = $("div .carousel-item.ca")
    for (let i = 0; i < b.length; i++) {
        $('#a_' + b[i].id).attr('mask')
        console.log(b[i].className)
        if (b[i].className == 'carousel-item ca active') {

            $('#a_' + b[i].id).removeClass('mask')
        }
    }

    function mask_ch() {
        let dt = setInterval(function () {
            for (let i = 0; i < b.length; i++) {
                $('#a_' + b[i].id).addClass('mask')
                if (b[i].className == 'carousel-item ca active') {
                    $('#a_' + b[i].id).removeClass('mask');
                    clearInterval(dt);
                }
            }
        }, 100);
    }

    function carousel_ch(id) {

        let a = $('#' + id.split('_')[1])
        console.log(a[0].className)
        if (a.className != 'carousel-item ca active') {
            let b = $("div .carousel-item.ca")
            for (let i = 0; i < b.length; i++) {
                b[i].className = 'carousel-item ca';
                $('#a_' + b[i].id).addClass('mask')
            }
            // console.log($('#' + id.split('_')[1]))
            $('#' + id.split('_')[1])[0].className = 'carousel-item ca active';
            $('#a_' + id.split('_')[1]).removeClass('mask');
        }
    }
</script>
```
