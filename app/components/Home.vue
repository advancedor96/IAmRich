<template>
  <Page class="page" actionBarHidden="true">
    <GridLayout>
      <Carousel height="100%" width="100%" 
                pageChanged="myChangeEvent" pageTapped="mySelectedEvent" 
                showIndicator="true" verticalAlignment="top" 
                indicatorAnimation="slide" color="white"
      >
        <CarouselItem class="slide slide1">
          <FlexboxLayout height="100%" width="100%" class="myLayout">
            <Label class="fa share_icon" color="#fff" text.decode="&#xf1e0;" @tap="share('diamond.png')"></Label>
          </FlexboxLayout>
        </CarouselItem>
        <CarouselItem class="slide slide2">
          <FlexboxLayout height="100%" width="100%" class="myLayout">
            <Label class="fa share_icon" color="#fff" text.decode="&#xf1e0;" @tap="share('dollar.png')"></Label>
          </FlexboxLayout>
        </CarouselItem>
        <CarouselItem class="slide slide3">
          <FlexboxLayout height="100%" width="100%" class="myLayout">
            <Label class="fa share_icon" color="#fff" text.decode="&#xf1e0;" @tap="share('gold.png')"></Label>
          </FlexboxLayout>
        </CarouselItem>
        <CarouselItem class="slide slide4">
          <FlexboxLayout height="100%" width="100%" class="myLayout">
            <Label class="fa share_icon" color="#fff" text.decode="&#xf1e0;" @tap="share('ring.png')"></Label>
          </FlexboxLayout>
        </CarouselItem>
        <CarouselItem class="slide slide5">
          <FlexboxLayout height="100%" width="100%" class="myLayout">
            <Label class="fa share_icon" color="#fff" text.decode="&#xf1e0;" @tap="share('gold2.png')"></Label>
          </FlexboxLayout>
        </CarouselItem>
        <CarouselItem class="slide slide6">
          <FlexboxLayout height="100%" width="100%" class="myLayout">
            <Label class="fa share_icon" color="#fff" text.decode="&#xf1e0;" @tap="share('ship.png')"></Label>
          </FlexboxLayout>
        </CarouselItem>
        <CarouselItem class="slide slide7">
          <FlexboxLayout height="100%" width="100%" class="myLayout">
            <Label class="fa share_icon" color="#fff" text.decode="&#xf1e0;" @tap="share('shoes.png')"></Label>
          </FlexboxLayout>
        </CarouselItem>
      </Carousel>
    </GridLayout>
  </Page>
</template>

<script>
var SocialShare = require("nativescript-social-share");
var imageSourceModule = require("image-source");
export default {
  methods:{
    share(filename){
      var image = imageSourceModule.fromFile(`~/images/${filename}`);
      SocialShare.shareImage(image, "How would you like to share this image?");
    },
    mySelectedEvent(){
      console.log('tapped')
    }
  }
};
</script>

<style scoped lang="scss">
@import "../app-variables";
.myLayout{
  justify-content: flex-end;
  align-items: flex-start;
}
.share_icon{
  font-size: 38;
  padding-top:10;
  padding-right:10;
}
.slide{
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}
.slide1{
  background-image: url("~/images/diamond.png");
}
.slide2{
  background-image: url("~/images/dollar.jpg");
}
.slide3{
  background-image: url("~/images/gold.jpg");
}
.slide4{
  background-image: url("~/images/ring.jpg");
}
.slide5{
  background-image: url("~/images/gold2.jpg");
}
.slide6{
  background-image: url("~/images/ship.jpg");
}
.slide7{
  background-image: url("~/images/shoes.jpg");
}




.fa {
  color: $accent-dark;
}

.info {
  font-size: 20;
}
</style>
