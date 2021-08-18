<template>
  <div class="navbar-block clearfix">
    <ul class="navbar-header">
      <li><a href="#">Home</a></li>
      <li><a href="#">Products</a></li>
      <li><a href="#">Contact us</a></li>
      <li><a href="#">Log in</a></li>
    </ul>
  </div>
</template>

<script>
export default {}
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Playfair+Display&display=swap');

.navbar-header {
  margin-right: 50px;
  margin-top: 50px;
  float: right;
}

.clearfix:after {
  content: '';
  display: table;
  width: 100%;
  clear: both;
}

.navbar-header li {
  display: inline-block;
}
.navbar-header li a {
  font-family: 'Playfair Display', serif;
  color: white;
  font-size: 22px;
  font-weight: bold;
  margin-right: 40px;
  text-decoration: none;
}
.navbar-header li:hover a{
  color: darkgoldenrod;
  transition: 500ms;
}


</style>
