# zuka
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
手機版左側導覽 無限階層.
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
