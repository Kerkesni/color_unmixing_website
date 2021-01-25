<template>
  <div class="app_container">
    <v-card id="title" outlined>
      <div id="article">Unmixing-Based Soft Color Segmentation for Image Manipulation</div>
      <div id="authors">Yagiz Aksoy, Tunc Ozan Aydin, Aljoscha Smolic and Marc Pollefeys</div>
      <div id="implementer">Implemented By <b>Walid El Ansari</b></div>
      <a href="https://github.com/Kerkesni/Color_Unmixing_Based_Soft_Segmentation" target="_blank">
        <img class="img" src="/GitHub-Logo.png"></img> 
      </a>
    </v-card>
    <v-card id="problem" outlined>
      <v-img class="img" src="/problem.png"></v-img>
      <div id="p_definition">
        <b>Problem Definition : </b>The goal of this article is to automatically decompose an image into a set of homogenous color layers that have smooth opacity transitions, so that 
        the layers could be used as an intermediate image representation to do image editing such as layer editing or even compositing.
      </div>
    </v-card>
     <v-card id="approach" outlined>
       <div class="ap_decription">
         <b>Approach Description : </b> The proposed approach is composed of four different steps each with a role and they are as follows :
       </div>
       <v-img class="img" src="/approach.png"></v-img>
       <div class="ap_decription">
         First, <b>Color Model Estimation : </b>This first step is used to automatically extract the color distributions that most represent the colors
         in the images. 
       </div>
       <div class="ap_decription">
         Next we do, <b>Color Model Estimation : </b> This is where we get the initial homogenous color layers, this is done by minimizing for each pixel 
         an energy function with a set of constraints that ensure the quality of the color layers we get.
       </div>
       <div class="ap_decription">
         <b>Mate Regularization : </b> In the initial homogenous color layers we get from the previous step, the transitions of opacity between the pixels can
          be very rough, that's why in this step we proceed by smoothing the alpha values of each layer using a guided filter.  
       </div>
       <div class="ap_decription">
         Finaly, <b>Color Re-Estimation : </b> A final pixel wise energy minimization step is done similar to the previous one, and that ensures that the quality 
         constraints are met for all the pixels in each one of the layers.
       </div>
    </v-card>
    <v-card id="q_results" outlined>
      <div id="res_tit">
        <b>Results : </b> Here are some examples of the color layers we obtain using this approach as well as the reconstructed images.
      </div>
      <v-img class="img" src="/re1.png"></v-img>
      <v-img class="img" src="/re2.png"></v-img>
      <div id="res_tit">
        <b>Remarks</b>
        <ul>
          <li>We get compact layers that represent multiple ressembling color values which makes layer editing very intuitive</li>
          <li>The reconstructed image is very similar to the original input image, so we don't have to worry about quality loss</li>
        </ul>
      </div>
    </v-card>
    <v-card id="applications" outlined>
      <div id="app_tit">
        <b>Example of Applications : </b><br/>As discussed before this method can be used for various image editing applications, like :
      </div>
      <div id="app_tit">
        <ul>
          <li>Color Correction</li>
          <li>Layer Deletion</li>
          <li>Compositing</li>
          <li>Masking</li>
        </ul>
      </div>
      <div id="app_tit">
        Here are some basic examples of that:
      </div>
      <v-img class="img" src="/app.png"></v-img>
    </v-card>
  </div>
</template>

<style lang="scss">
#app{
  background-color: rgb(252, 252, 252);
}
.app_container{
  margin: auto;
  margin-top: 1rem;
  max-width: 60rem;

  .v-card{
    margin-bottom: 1rem;
    padding: 1rem;
  }

  #title{
    text-align: center;
    color: black;
    #article{
      font-size: x-large;
      color: black;
    }
    .img{
      margin: auto;
      max-width: 4rem;
    }
  }
  #problem{
    .img{
      max-width: 50rem;
      margin: auto;
      margin-bottom: 1rem;
    }
    #p_definition{
      max-width: 50rem;
      text-align: justify;
      margin: auto;
      font-size: large;
      font-weight: 300;
      color: black;
    }
  }
  #approach{
    .img{
      max-width: 51rem;
      margin: auto;
      margin-bottom: 1rem;
    }
    .ap_decription{
      max-width: 50rem;
      text-align: justify;
      margin: auto;
      font-size: large;
      font-weight: 300;
      color: black;
      margin-bottom: 1rem;
    }
  }
  #q_results{
    .img{
      max-width: 50rem;
      margin: auto;
      margin-bottom: 1rem;
    }
    #res_tit{
      max-width: 50rem;
      text-align: justify;
      margin: auto;
      font-size: large;
      font-weight: 300;
      color: black;
      margin-bottom: 1rem;
    }
  }
  #applications{
    .img{
      max-width: 50rem;
      margin: auto;
      margin-bottom: 1rem;
    }
    #app_tit{
      max-width: 50rem;
      text-align: justify;
      margin: auto;
      font-size: large;
      font-weight: 300;
      color: black;
      margin-bottom: 0.5rem;
    }
  }
}
</style>
