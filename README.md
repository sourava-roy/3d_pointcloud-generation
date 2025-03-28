# 2D-Image-to-3D-Pointcloud
System that converts a single 2D image into a 3D model using Depth Anything model to predict depth image then constructing point cloud and 3D mesh of the image. Users can upload images in .png or .jpg formats, and the system outputs the 3D model as a .obj file.


## Workflow
1- Image Upload: Users upload a 2D image using the web interface.

2- Depth Estimation: The uploaded image is passed through a pre-trained depth estimation model (using Hugging Face transformers) to predict depth maps.

3- Point Cloud Generation:
The depth map is used to generate a 3D point cloud using camera intrinsics.
Background pixels are excluded from the point cloud based on a threshold to focus on the foreground object.

4- 3D Mesh Construction:
The point cloud is processed using Open3D's Poisson surface reconstruction to create a 3D mesh.
The final 3D mesh is exported as a .obj file.
