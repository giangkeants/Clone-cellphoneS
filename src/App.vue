<template>
  <div id="app">
    <!-- Navbar -->
    <nav class="navbar navbar-inverse">
      <div class="container-fluid nav1">
        <div class="navbar-header logo1">
          <a href="#"><img class="logo" src="/dist/image/as.png" alt=""></a>
        </div>
        <ul class="nav navbar-nav navbarmenu">
          <li style="margin-top:10px;"><a href="#"><i class="fas fa-bars"></i> Danh mục</a></li>
          <li><a href="#"><i class="fas fa-map-marker-alt"></i> Xem giá tại<br> Miền Nam</a></li>
        </ul>

        <form class="navbar-form navbar-left formSearch" action="/action_page.php">
          <div class="">
            <input
              type="text"
              class="form-control formedit"
              placeholder="Bạn cần tìm gì?"
              name="search"
            />
            <div class=" btnsearch">
              <button  type="submit">
               <i class="fas fa-search"></i>
              </button>
            </div>
          </div>
        </form>

        <ul class="nav navbar-nav navbarmenu">
          <li><a href="#"><i class="fas fa-phone-alt"></i> Gọi mua hàng <br> <strong>1800.2097</strong></a></li>
          <li><a href="#"><i class="fas fa-map-marker-alt"></i> Cửa hàng <br> gần bạn</a></li>
          <li><a href="#"><i class="fas fa-truck"></i>Tra cứu <br> đơn hàng</a></li>
          <li style="margin-top:10px;"><a href="#"><i class="fas fa-shopping-bag"></i> Giỏ hàng</a></li>
          <li><a href="#"><i class="fas fa-user-circle"></i><br> Smember</a></li>
        </ul>
      </div>
    </nav>
   
      <div class="container">
        <div class="slider">
            <div class ="menu">
              <ul>
                <li><i class="fas fa-mobile-alt"></i><strong> Điện thoại</strong><i class="right"></i></li>
                <li><i class="fas fa-laptop"></i><strong> Laptop</strong><i class="right"></i></li>
                <li><i class="fas fa-tablet"></i><strong> Máy tính bảng</strong><i class="right"></i></li>
                <li><i class="fas fa-headphones-alt"></i><strong> Âm thanh</strong><i class="right"></i></li>
                <li><i class="fas fa-stopwatch"></i><strong> Đồng hồ </strong><i class="right"></i></li>
                <li><i class="fas fa-home"></i><strong> Nhà thông minh</strong><i class="right"></i></li>
                <li><i class="fas fa-plug"></i><strong> Phụ kiện</strong><i class="right"></i></li>
                <li><i class="fas fa-desktop"></i><strong> PC - Màn hình</strong><i class="right"></i></li>
                <li><i class="fas fa-tv"></i><strong> Tivi</strong><i class="right"></i></li>
                <li><i class="fas fa-sync"></i><strong> Thu cũ</strong><i class="right"></i></li>
                <li><i class="fas fa-mobile-alt"></i><strong> Hàng cũ</strong><i class="right"></i></li>
                <li><i class="fas fa-bullhorn"></i><strong> Khuyến mãi</strong><i class="right"></i></li>
              </ul>
            </div>
            <div class="middle">
                <div id="show">
                  <img src="/dist/image/content1.png" name="slide" width="300px" height="150px">
                  <button class="btn" v-on:click="show1()" id="pre">-</button>
                  <button class="btn" v-on:click="show2()" id="next">+</button>
                </div>
                <div id ="menu-horizontal">
                    <ul>
                      <li>MỪNG KHAI TRƯƠNG<br> Giảm sốc đến 65%</li>
                      <li>GALAXY S22 ULTRA<br> Ưu đãi hấp dẫn</li>
                      <li>NOKIA C21<br>Màn khủng pin trâu</li>
                      <li>XIAOMI REDMIBOOK 15<br>Giá rẻ vô đối</li>
                      <li>MSI MODERN 14<br> Mỏng nhẹ - thời thượng</li>
                    </ul>
                </div>
            </div>
            <div class="slide-right">
              <img src="/dist/image/content2.png" alt="">
              <img src="/dist/image/content3.png" alt="">
              <img src="/dist/image/content4.png" alt="">
            </div>
           
        </div>
    </div>


  </div>
</template>

<script >
  window.onload = function () {
      var transferImage = new Vue({
          el: '#show',
          data: {
              images: ['/dist/image/content1.png','/dist/image/content5.png',
              '/dist/image/content6.png','/dist/image/content7.png','/dist/image/content8.png'],
              i: 0
          },
          methods: {
              show1() {
                  if(this.i >= 1)
                  {
                    this.i--;
                  }else{
                    this.i = this.images.length-1;
                  }
                  document.slide.src = this.images[i];
              },
              show2() {
                  this.i++;
                  if(this.i === images.length)
                  {
                    this.i = 0;
                  }
                  document.slide.src = this.images[i];

              }
          }
      });
  }
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
/* navbar */
.nav1{
  background-color: rgb(224,5,43);
  padding-left: 150px;
  padding-right:25px;
}
.nav1 a{
 color: #fff!important;
 padding: 10px 18px 10px 18px;
}
.logo1 .logo{
  margin-left:20px;
  margin-top: 10px;
}
.logo{
  height: 50px;
  width: 200px;
}
.navbarmenu li{
  border: 1px transparent solid;
  border-radius: 10px;
}
.navbarmenu li:hover{
  background:rgba(183, 183, 183, 0.4);
}
.input-group .formedit{
  border: #fff solid 1px;
}
.formSearch{
  position: relative;
  padding-top: 10px;
}
.formSearch input{
  padding-left: 25px;
  
  border-radius: 10px;
  width: 500px;
}

.btnsearch button{
  position: absolute;
  top: 40%;
  left: 8%;
  color: #4f5b66;
  background: transparent;
  border: none;
} 
/* /navbar */

.container {
    width: 80%;
    height: 80vh;
    overflow: hidden;
    margin: 0 auto;
    position: relative;
}

.container .slider {
    display: flex;
}

.container img {
    width: 100%;
    height: 100%;
}

#pre {
    position: absolute;
    top: 50%;
    left: 0;
    transform: translateY(-50%);
}

#next {
    position: absolute;
    top: 50%;
    right: 0;
    transform: translateY(-50%);
}

.btn {
    width: 40px;
    height: 40px;
    color: #fff;
    background: #2c3e50;
    font-size: 18px;
    border: none;
    position: absolute;
}
/* menu */
.slider{
  position: relative;
  display: block;
}
.menu ul{
    display: block;
    background:#fff;
    border-radius: 10px ;
    list-style:none;
    margin-right: 10px;
    box-shadow: rgb(177, 177, 177) 2px 2px 2px 2px;
    text-align: left;
}
.menu ul li{
  position: relative;
  text-decoration: none;
  font-size:15px;
  line-height: 33px;
  padding-left: 3px;
  width: 200px;
  cursor: pointer;
}
.menu ul li:hover{
  background: rgb(224, 224, 224);
   border-radius: 10px ;

}
.menu ul li .right{
  position: absolute;
  border: solid #2c3e50;
  border-width: 0 2px 2px 0;
  display: inline-block;
  padding: 3px;
  transform: rotate(-45deg);
  right: 3%;
  top:30%;
}
#show img{
    /* box-shadow: rgb(177, 177, 177) 2px 2px; */
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
    height:41vh;
    width:max-content;
}

/* menu horizontal */
.middle{
  position: relative;
}
#menu-horizontal{
  position: absolute;
  list-style:none;
  box-shadow: rgb(177, 177, 177) 2px 2px;
  border-bottom-left-radius: 10px;
  border-bottom-right-radius: 10px;
}
#menu-horizontal ul{
    width: 94vh;
}
#menu-horizontal ul li{
  width: fit-content;
  display:inline-flex;
  cursor: pointer;
  font-size: 12px;
  padding-top: 17.5px;
  padding-bottom: 10px;
}
.slide-right{
  position: relative;
  width: fit-content;
  border: 1px #000;
}
.slide-right img{
  position: relative;
  display: block;
  height: 16.2vh;
  width: 35vh;
  border-radius: 10px;
  margin-left: 10px;
  margin-bottom: 10px;
  box-shadow: rgb(177, 177, 177) 2px 2px;
}

</style>
