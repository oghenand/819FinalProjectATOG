# Image Colorizatiom Using Panoptic Segmentation and Style Transfer
Hello! We're Amanda Tong and Omkar Ghenand, and welcome to the GitHub repository for our 6.819 (Advances in Computer Vision) Final Project. For this project, we chose the Image Colorization topic. Most recently, image colorization methods have involved convolutional neural network architectures (such as those of Zhang et al.). In our approach, we combine two areas of Computer Vision research to colorize images: Image Segmentation and Style Transfer. 

The idea for our approach comes from the style transfer problem set problem we had earlier in the semester. We played around with the style and content images, and tried to see if we could colorize a grayscale "content image" through style transfer with a color "style" image of the same object in the grayscale image. We attempted this with a grayscale image of bananas as the "content image" and a color image of bananas as the "style image," and the results are shown below. To our excitement, the style transfer resulted in a plausible colorization of the grayscale image. 

![Screen Shot 2022-05-10 at 9 11 52 PM](https://user-images.githubusercontent.com/68125413/168917514-d89adf16-1a2a-4cdc-93b7-d4af56c5c51e.png)

Although our results look decent from the first trial of the image look plausible, we realize that this is only so because of the fact that there is only one object in the image (bananas). To be able to colorize a larger variety of images with multiple objects, we need to colorize each object with a reference image - a color image containing the object to colorize. To do this, we would need to first segment and identify different segments of the image. Then, for each segment/object in the image, we would need to a perform style transfer with a reference image to colorize the segment/object. Since we have multiple style transfer operations, we would need to make use of binary masking: for each object in an input grayscale image, we perform style transfer over the entire image and then a binary mask to isolate the now-colorized object. In the end, we sum over each binary mask of each object to recreate the image, which would now be colorized. In our approach, we use photorealistic style transfer since this method of style transfer maintains photorealism during style trasnfer between arbitrary images. An example of our approach is shown below: 

![6 819 Github Images 001](https://user-images.githubusercontent.com/68125413/168920746-02528910-be60-4e77-a6f1-c64cf45f481e.jpeg)
![6 819 Github Images 002](https://user-images.githubusercontent.com/68125413/168920775-eb78df91-2d4d-44fa-9b98-82a24f136d1b.jpeg)
![6 819 Github Images 003](https://user-images.githubusercontent.com/68125413/168920866-c62965b6-819d-4222-ad6a-ddaba55745c3.jpeg)
![6 819 Github Images 004](https://user-images.githubusercontent.com/68125413/168920969-8f7fc100-e27d-4d5b-8fb3-58de15beda7b.jpeg)
![6 819 Github Images 005](https://user-images.githubusercontent.com/68125413/168921044-8293e9fa-4630-438b-b889-1dd8e57c9001.jpeg)

Here are more examples of our colorization approach in action:
![Uploading Screen Shot 2022-05-10 at 11.28.34 PM.png…]()

You can find the report and code for our project on this GitHub. 
