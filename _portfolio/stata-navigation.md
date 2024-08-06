An image-based system for navigating MIT's Stata Center, a notoriously complex building.

Methods: 
1. The user uploads an image from the first floor of the Stata Center and a desired destination.
2. The system uses ResNet-18 to identify the user's location based on the uploaded image.
3. The system uses Dijkstra's algorithm to find the shortest path between the user's location and their destination.
4. The system returns navigation instructions to the user.

Performance: 
- The location identification step achieves a top-1 accuracy of 46.5%, a top-5 accuracy of 63.8%, and a median error of 29 feet on our test set.
- Using the location identified by ResNet-18, the system produces high-quality navigation instructions, helping the user reach their destination easier.

This project was conducted in collaboration with Krish Datta and Sara Pasquino, as part of MIT's 6.8300: Advances in Computer Vision course.