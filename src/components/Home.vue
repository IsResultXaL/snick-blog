<template>
    <div id="parent" class="container">
        <!-- Navigation -->
        <header>
            <div class="navbar">
                <a id="menu">
                    <div class="hamburger">
                        <div class="bar firstLine"></div>
                        <div class="bar secondLine"></div>
                        <div class="bar thirdLine"></div>
                    </div>
                </a>
                <div class="logo">
                    <div class="textLogo">Curated News</div>
                </div>
                <a  @click="search">
                    <div class="search">
                        <div class="searchIcon"></div>
                        <div class="tail"></div>
                    </div>
                </a>
            </div>
            <div id="searchBar" v-show="searchBar">
                <input id="search-bar" placeholder="Search feed" v-model="searchContent" type="search" >
                <input id="submit" @click="submit" type="submit">
            </div>
        </header>
        <!-- Card Layout -->
        <div class="cardLayout">
            <div class="firstRow">
                <div class="card card-long">
                    <div class="card-long-bg">
                        <a class="likesCounter" >
                            <span class="likes"  @click="likes" id="likes1">{{likeNum}}</span>
                        </a>
                    </div>
                    <div class="card-long-block">
                        <div class="card-long-header">Coventry City Guide Including Coventry Hotels</div>
                        <p>Planning a vacation to Europe? No doubt you have certain expectations about your upcoming
                            journey.</p>
                    </div>
                </div>
                <div class="card l-spacing card-reg card-reg-overlay">
                    <div class="card-reg-header">Always Look On The Bright Side Of Life</div>
                    <a class="likesCounter" >
                        <span class="likes" id="likes2">2,569</span>
                    </a>
                </div>
            </div>
            <div class="clear"></div>
            <div class="secondRow">
                <div class="card card-reg card-reg-bg">
                    <div class="card-reg-left-reg">Creating Remarkable Poster Prints Through 4 Color</div>
                    <a class="likesCounter" >
                        <span class="likes" id="likes3">582</span>
                    </a>
                </div>
                <div class="card card-long l-spacing">
                    <div class="card-long-bg-two">
                        <a class="likesCounter" >
                            <span class="likes" id="likes4">859</span>
                        </a>
                    </div>
                    <div class="card-long-block">
                        <div class="card-long-header">Become A Travel <br>Pro In One Easy Lesson</div>
                        <p>When choosing a static caravan you will probably look
                            for the holiday park which meets your requirements and then...</p>
                    </div>
                </div>
            </div>
            <div class="clear"></div>
            <div class="thirdRow">
                <div class="card r-spacing card-xl card-xl-bg">
                    <div class="card-reg-left-xl">A Great Way To Generate All The Motivation You Need To Get Fit</div>
                    <a class="likesCounter" >
                        <span class="likes" id="likes5">734</span>
                    </a>
                </div>
                <div class="card card-sm card-sm-bg">
                    <div class="card-reg-left-sm">Great Benefits Of Natural Skin Care Products</div>
                    <a class="likesCounter" >
                        <span class="likes" id="likes6">582</span>
                    </a>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
  export default {
    name: 'home',
    data () {
      return {
        searchBar: false,
        searchContent: '',
        likeNum: '2,000'
      }
    },
    created () {
    },
    methods: {
      search () {
        this.searchBar = !this.searchBar
      },
      submit () {
        alert(this.searchContent)
      },
      likes () {
        let number = parseInt(this.likeNum.replace(/,/g, ""))
        number++
        this.likeNum = this.numberWithCommas(String(number))
      },
      numberWithCommas(likes) {
        return likes.replace(/(.)(?=(.{3})+$)/g, "$1,")
      }
    }
  }
</script>

<style lang="less">

    .likes {
        font-family: 'Open Sans', sans-serif;
        color: #dadfd8;
        font-size: 8px;
        position: absolute;
        bottom: 17px;
        left: 16px;
    }

    .likes:before {
        content: '\2665';
        color: #dadfd8;
        padding-right: 6px;
    }

    .clear {
        clear: both;
    }

    /* Navigation */

    header {
        margin: 60px 0px;
    }

    .navbar {
        display: inline-block;
        width: 100%;
    }

    .hamburger {
        float: left;
        position: relative;
        top: 5px;
    }

    .bar {
        border-radius: 6px;
    }

    .firstLine {
        background-color: #7e8186;
        width: 17px;
        height: 3px;
        margin-bottom: 2px;
    }

    .secondLine {
        background-color: #7e8186;
        width: 10px;
        height: 3px;
        margin-bottom: 2px;
    }

    .thirdLine {
        background-color: #7e8186;
        width: 14px;
        height: 3px;
    }

    .search {
        float: right;
        position: relative;
        bottom: 20px;
    }

    .searchIcon {
        border: 2px solid #7e8186;
        width: 11px;
        height: 11px;
        border-radius: 50%;
    }

    .tail {
        border-radius: 8px;
        position: relative;
        left: 11px;
        bottom: 2px;
        content: '';
        height: 3px;
        width: 5px;
        background-color: #7e8186;
        -ms-transform: rotate(40deg); /* IE 9 */
        -webkit-transform: rotate(40deg); /* Safari */
        transform: rotate(40deg); /* Standard syntax */
    }

    #search-bar {
        width: 75%;
        padding: 15px;
        float: left;
    }

    #submit {
        width: 25%;
        padding: 15px;
        float: right;
    }

    .textLogo {
        text-transform: uppercase;
        color: #7e8186;
        text-align: center;
        font-family: 'Oswald', sans-serif;
    }

    /* Layout */

    .container {
        max-width: 600px;
        margin: 0 auto;
    }

    /* Cards */

    .card {
        box-shadow: 2px 0px 120px -6px rgba(0, 0, 0, 0.17);
    }

    .card-long {
        position: relative;
        background-color: black;
        width: 335px;
        height: 150px;
        float: left;
    }

    .card-reg {
        position: relative;
        background-color: #000;
        width: 240px;
        height: 150px;
        float: left;
    }

    .card-xl {
        position: relative;
        background-color: #000;
        width: 360px;
        height: 150px;
        float: left;
    }

    .card-sm {
        position: relative;
        background-color: #000;
        width: 215px;
        height: 150px;
        float: left;
    }

    /* Card Styles */

    .card-long-bg {
        position: relative;
        width: 150px;
        height: 150px;
        background-color: #000;
        float: left;
        background: url('../assets/images/5.png');
        background-size: cover;
    }

    .card-long-bg-two {
        width: 150px;
        height: 150px;
        background-color: #000;
        float: left;
        background: url('../assets/images/3.png');
        background-size: cover;
        background-position: 100% 0;
    }

    .card-long-block {
        background-color: #fff;
        width: 185px;
        height: 150px;
        float: right;
    }

    .card-long-header {
        font-family: 'Playfair Display', sans-serif;
        line-height: 22px;
        font-weight: bold;
        padding-top: 17px;
        padding-left: 17px;
    }

    .card-reg-left-reg {
        font-family: 'Playfair Display', sans-serif;
        line-height: 22px;
        font-weight: bold;
        padding: 20px 0px 25px 17px;
        width: 130px;
    }

    .card-reg-left-xl {
        font-family: 'Playfair Display', sans-serif;
        line-height: 22px;
        font-weight: bold;
        padding: 20px 0px 25px 17px;
        width: 130px;
    }

    .card-reg-left-sm {
        font-family: 'Playfair Display', sans-serif;
        color: #fff;
        line-height: 22px;
        font-weight: bold;
        padding: 20px 0px 25px 17px;
        width: 130px;
    }

    .card-reg-header {
        font-family: 'Playfair Display', sans-serif;
        text-align: center;
        color: white;
        font-weight: 700;
        position: relative;
        top: 33%;
        padding: 0px 25px;
        line-height: 24px;
    }

    .card-long-block p {
        font-family: 'Roboto', sans-serif;
        font-size: 8px;
        padding-top: 15px;
        padding-left: 17px;
        padding-right: 17px;
        line-height: 12px;
        overflow: hidden;
        text-overflow: ellipsis;
        display: -webkit-box;
        -webkit-line-clamp: 4;
        -webkit-box-orient: vertical;
    }

    .card-reg-bg {
        background: url('../assets/images/4.png') no-repeat;
        background-position: 0% 100%;
        background-size: 200%;
    }

    .card-xl-bg {
        background: url('../assets/images/2.png') no-repeat;
        background-position: 38% 70%;
    }

    .card-reg-overlay {
        background: linear-gradient(
                rgba(204, 58, 77, 0.85),
                rgba(229, 109, 99, 0.85)
        ),left top no-repeat;
        background-size: 140%;
        background-position: 50% 35%;
    }

    .card-sm-bg {
        background: url('../assets/images/1.png') no-repeat;
        background-size: 190%;
        background-position: 20% 50%;
    }

    .l-spacing {
        margin-left: 25px;
    }

    .r-spacing {
        margin-right: 25px;
    }

    .secondRow,
    .thirdRow {
        margin-top: 20px;
    }

    /* Media Queries */

    @media screen and (max-width: 615px) {
        .container {
            width: 90%;
        }

        .card {
            width: 100%;
            margin: 10px 0 !important;
        }

        .card-reg-header {
            top: 40%;
        }

        .card-long-bg,
        .card-long-bg-two {
            width: 45%;
        }

        .card-long-block {
            width: 55%;
        }

        .l-spacing,
        .r-spacing,
        .secondRow,
        .thirdRow {
            margin: 0;
        }
    }

    .credits-wrap {
        font-family: 'Open Sans', sans-serif;
        text-align: center;
        padding-top: 10px;
    }

    .credit {
        text-decoration: none;
        color: #000;
        font-weight: bold;
    }

</style>
