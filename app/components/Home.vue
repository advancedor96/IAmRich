<template>
  <Page class="page" actionBarHidden="true">
    <StackLayout>
      <!-- <Image src="~/diamond.png" stretch="none" /> -->
      <Carousel>
        <CarouselItem id="slide1" class="slide slide1">
          <Button text="Share" @tap="share"></Button>
        </CarouselItem>
        <CarouselItem id="slide2" class="slide slide2"></CarouselItem>
        <CarouselItem id="slide2" class="slide slide3"></CarouselItem>
        <CarouselItem id="slide2" class="slide slide4"></CarouselItem>
      </Carousel>
    </StackLayout>
  </Page>
</template>

<script>
var SocialShare = require("nativescript-social-share");
var imageSourceModule = require("image-source");
export default {
  methods:{
    share(){
      var image = imageSourceModule.fromFile("~/diamond.png");
      SocialShare.shareImage(image);
    }
  }
};
</script>

<style scoped lang="scss">
@import "../app-variables";
.slide{
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}
.slide1{
  background-image: url("~/diamond.png");
}
.slide2{
  background-image: url("~/dollar.jpg");
}
.slide3{
  background-image: url("~/gold.jpg");
}
.slide4{
  background-image: url("~/ring.jpg");
}





.fa {
  color: $accent-dark;
}

.info {
  font-size: 20;
}
</style>
