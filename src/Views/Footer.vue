<template>
  <footer>
    <div class="extrass">
      <div class="title extrass">
        <h3>Extrass</h3>
      </div>
      <div class="list-extrass">
        <ul>
          <li><a href="#brands">Brands</a></li>
          <li><a href="#git_certification">Git Certification</a></li>
          <li><a href="#affiliate">Affiliate</a></li>
          <li><a href="#specials">Specials</a></li>
          <li><a href="#sitemap">Site Map</a></li>
        </ul>
      </div>
    </div>
    <div class="information">
      <div class="title information">
        <h3>Information</h3>
      </div>
      <div class="list-information">
        <ul>
          <li><a href="#about">About Us</a></li>
          <li><a href="#privacy_policy">Privacy Policy</a></li>
          <li><a href="#terms and condition">Termss And Condition</a></li>
          <li><a href="#contact">COntact Us</a></li>
          <li><a href="#sitemap">Site Map</a></li>
        </ul>
      </div>
    </div>
    <div class="myaccount">
      <div class="title myaccount">
        <h3>My Account</h3>
      </div>
      <div class="list-myaccount">
        <ul>
          <li><a href="#myaccount">My Account</a></li>
          <li><a href="#order_history">Order History</a></li>
          <li><a href="#wish_list">Wish List</a></li>
          <li><a href="#newsletter">News Letter</a></li>
          <li><a href="#returns">Returns</a></li>
        </ul>
      </div>
    </div>
    <div class="contact">
      <div class="title contact">
        <h3>Contact Us</h3>
      </div>
      <div class="list-contact">
        <ul>
          <li class="address-site"><a href="#address">42 Dream House, Dreammy street, 7131 Dreamville, USA</a></li>
          <li><a href="#gmail">company@gmail.com</a></li>
          <li><a href="#tlp">456-456-121</a></li>
          <li><a href="#city">Dream City, USA</a></li>
        </ul>
      </div>
    </div>
  </footer>
</template>

<style media="screen">
  footer{
    width: 100%;
    background-color: black;
    display: flex;
    justify-content: space-around;
    margin-top: 150px;
    padding: 10px 0;
  }

  .list-contact ul .address-site{
    text-indent: 20px;
    width: 90%;
  }

  .title{
    margin-bottom: 40px;
  }

  h3{
    color: white;
    font-size: 1.2rem;
    font-weight: var(--font-weight-600);
  }

  @media (min-width: 450px) and (max-width:650px){
    footer{
      flex-direction: column;
    }

    .title{
      margin-top: 20px;
    }
  }
</style>
