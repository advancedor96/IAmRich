<template>
  <Page class="page" actionBarHidden="true">
    <StackLayout>
      <!-- <Image src="~/diamond.png" stretch="none" /> -->
      <Carousel>
        <CarouselItem id="slide1" class="slide slide1">
          <FlexboxLayout flexDirection="column-reverse" height="100%" width="100%">
            <Button text="Share" class="btn btn-primary" @tap="share('diamond.png')"></Button>
          </FlexboxLayout>
        </CarouselItem>
        <CarouselItem id="slide2" class="slide slide2">
          <FlexboxLayout flexDirection="column-reverse" height="100%" width="100%">
            <Button text="Share" class="btn btn-primary" @tap="share('dollar.jpg')"></Button>
          </FlexboxLayout>
        </CarouselItem>
        <CarouselItem id="slide2" class="slide slide3">
          <FlexboxLayout flexDirection="column-reverse" height="100%" width="100%">
            <Button text="Share" class="btn btn-primary" @tap="share('gold.jpg')"></Button>
          </FlexboxLayout>
        </CarouselItem>
        <CarouselItem id="slide2" class="slide slide4">
          <FlexboxLayout flexDirection="column-reverse" height="100%" width="100%">
            <Button text="Share" class="btn btn-primary" @tap="share('ring.jpg')"></Button>
          </FlexboxLayout>
        </CarouselItem>
      </Carousel>
    </StackLayout>
  </Page>
</template>

<script>
var SocialShare = require("nativescript-social-share");
var imageSourceModule = require("image-source");
export default {
  methods:{
    share(filename){
      var image = imageSourceModule.fromFile(`~/${filename}`);
      SocialShare.shareImage(image, "How would you like to share this image?");
    }
  }
};
</script>

<style scoped lang="scss">
@import "../app-variables";
// .container{
//   border-width: 5;
//   border-color: yellow;
// }
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
