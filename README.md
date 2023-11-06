# Facial-Mapping-of-User-to-Avatar
## Introduction
Realistic face animation is a key element in 3D virtual environments that show the presence of characters, both human and non-human. Some of their uses include the 3D gaming industry, interactive software, and 3D animated movies. Facial Mapping of User to Avatar is rooted in the idea of capturing the intricacies of human facial expressions, mapping them onto digital characters or avatars, and enabling users to navigate the digital world while maintaining a sense of personal identity. 
## Motivation
* When people are preoccupied with various tasks being presentably ready for meetings and classes seems a little problematic.
* Online classes taken by teachers can seem monotonous and boring to students.
* Gaming in VR with our own avatar seems so much cooler than using existing animated characters in video games 
## Problem statement
To map i.e retarget user facial emotions example: happy, sad, surprised to an avatar.
## Objectives
* Detecting key points on a human face.
* Importing an avatar to blender software.
* Detecting key points on the avatar created.
* Retargeting facial key points to avatar key points.
## Procedure
* Face detection and facial keypoints detection is done using Dlib library.
* why Dlib library over Opencv?
   * Opencv detects all the faces while dlib detects only those faces which are bigger in size.
   * dlib provides a pre-trained facial landmark detector that can detect 68 points on the face.
   * each facial feature is mapped with a set of points.If we want for exammple to locate a mouth in the face,we can use the points from 49 to 68.
* The primary purpose is to perform facial animation based on facial landmarks detected in a camera feed and update the 3D model accordingly.
   * Once the face is detected, the system proceeds to localize 2D facial landmarks. These are the x and y coordinates of specific points on the 2D image of the face, such as the corners of the eyes, the tip of 
     the nose, and the corners of the mouth.
   * 3D Reconstruction: To obtain 3D facial landmarks, you need to estimate the depth or Z-coordinate of these 2D landmarks. This is typically achieved through 3D facial reconstruction techniques. Common methods 
     for 3D facial reconstruction include stereo vision, structured light, and photometric stereo. These methods can estimate the depth information from the 2D image.
   * Mapping Landmarks to the 3D Model: Once the facial landmarks are detected in the 2D camera feed, they need to be mapped to corresponding points on a 3D model of a face. This mapping is often done using a 
     process called 3D facial landmark localization, which aligns the detected 2D landmarks with the vertices of the 3D model.
   * Creating a Facial Rig: A facial rig is a system of bones and control points that are applied to the 3D model's face. These control points are used to deform the 3D mesh of the model to match the movements 
     of the detected facial landmarks.
   * Pose Estimation: Estimating the head pose (orientation) of the person is important for precise 3D landmark localization. This information helps in accurately aligning the 3D landmarks with the person's face.
   * Head pose estimation provides information about the orientation of the person's head in three-dimensional space. This orientation includes parameters such as pitch (tilt up or down), yaw (turn left or 
     right), and roll (tilt to the side). By knowing the head's orientation, it becomes possible to align the 3D landmarks correctly with the person's face.Once you have the head pose, you can apply a 
      transformation to the 3D landmarks to make them consistent with the person's head orientation. This alignment is essential for ensuring that the 3D landmarks are positioned accurately relative to the 
     person's face in the virtual environment.
     
   * With knowledge of the head pose,how can you adjust the position and orientation of the avatar's head to match that of the person being tracked?
      * Obtain Head Pose Information:First, you need to estimate the head pose of the person being tracked. This typically involves determining the orientation of the head in 3D space, including parameters like 
     pitch, yaw, and roll.
      * Define a Coordinate System: Establish a consistent coordinate system for both the person's head and the avatar's head. This coordinate system will serve as a reference for applying transformations.
     Compute the Transformation:
     * Calculate a transformation matrix that describes how the avatar's head needs to be adjusted to match the person's head pose. This transformation matrix should include translation (position) and rotation 
     (orientation) information.
     * Apply the Transformation: Use the calculated transformation matrix to adjust the position and orientation of the avatar's 3D model. This can be done using mathematical operations to transform the avatar's 
     head relative to its original position and orientation.
     *  For position adjustment (translation): Apply translation to move the avatar's head to the correct position in 3D space, matching the position of the tracked person's head. This involves adjusting the x, y, 
     and z coordinates.
     *  For orientation adjustment (rotation):Apply rotation to align the avatar's head with the orientation of the tracked person's head. This includes adjusting the pitch, yaw, and roll angles.
     * Update in Real Time:Continuously update the transformation as the person's head pose changes. Head pose can change due to natural head movements, allowing the avatar to respond in real-time and maintain 
     alignment with the person's head.
     *  Render the Avatar:Render the transformed avatar with the updated head position and orientation. This means that the avatar's head will appear to follow the movements and orientation of the person being 
     tracked.





  
     
