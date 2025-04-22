# η-SLAM: Navigating the World, Lightly and Brightly! ✨


## What's the Buzz About η-SLAM?

Introducing η-SLAM (pronounced "eta-slam"), a cutting-edge, multi-sensor SLAM (Simultaneous Localization And Mapping) framework meticulously crafted for low to medium-spec hardware. Think of it as giving your robots the superpower of knowing where they are and what's around them, all without breaking a sweat (or the bank on hardware!).

We're talking state-of-the-art, folks! η-SLAM cleverly blends the brilliance of deep learning with the accuracy of classical SLAM techniques, creating a synergy that's greater than the sum of its already impressive parts.

## Why η-SLAM is Your Robot's New Best Friend? 🤖

Here's the lowdown on why η-SLAM is a game-changer for your autonomous endeavors:

* **Lean and Mean on Resources:** Forget about those power-hungry SLAM behemoths! η-SLAM boasts a remarkably low computational cost. We're talking significant reductions in CPU and GPU (or NPU) utilization, leaving precious processing power for all those *other* cool things your robot needs to do. Think benchmarks that'll make your current system breathe a sigh of relief!
* **Tiny Footprint, Mighty Performance:** Memory constraints? No sweat! η-SLAM's minimal RAM usage makes it the perfect companion for resource-limited devices. We've squeezed every last bit of efficiency out so your robot can remember its world without forgetting its own name.
* **Rock-Solid Perception:** Prepare for enhanced robustness and accuracy! Our intelligent multi-sensor fusion approach expertly blends data from various sensors, making your robot resilient to sensor noise, pesky occlusions, and even those slightly chaotic dynamic environments. It's like giving your robot extra eyes (and ears, and more!) that work together seamlessly.
* **Sips Power, Goes the Distance:** Say goodbye to short battery life woes! η-SLAM's efficient algorithms are designed to minimize power consumption, allowing your mobile robots and embedded systems to roam free for longer. More exploring, less charging – that's the η-SLAM promise.
* **Real-Time Awareness, Real-World Impact:** Get ready for accurate localization and mapping in the blink of an eye! η-SLAM delivers real-time performance, which is absolutely crucial for smooth autonomous navigation and seamless interaction with the world.
* **Plays Well with Others:** Integration shouldn't be a headache! η-SLAM offers user-friendly software interfaces (think ROS, APIs) and broad hardware compatibility, making it a breeze to integrate with your existing robotic platforms. Plug and play, almost literally!
* **Your Way, Right Away:** Need something a little different? η-SLAM offers customization and flexibility options to tailor the solution to your specific application requirements. It's like having a bespoke SLAM solution without the bespoke price tag.

### Under the Hood (But Not Too Deep!) ⚙️

η-SLAM is engineered to thrive on low-spec hardware, ideally with an NPU for an extra boost, though it's not strictly mandatory. This clever design means:

* **More Brainpower for the Fun Stuff:** By keeping TPU/GPU/NPU usage low, you're free to run those fancy AI models for object detection & recognition, decision-making, or whatever else tickles your robot's fancy!
* **CPU Efficiency!** Our optimized and performant code keeps CPU usage to a minimum, ensuring smooth operation without bogging down your system.
* **Future-Proof Flexibility:** η-SLAM is designed to easily incorporate the latest and greatest deep or shallow models, so you can always leverage cutting-edge AI for enhanced accuracy.
* **Our Secret Sauce, Your Winning Formula:** Being proprietary code means we have the ultimate control to optimize and fine-tune every single piece of η-SLAM specifically for your unique domain and application. It's like having a dedicated team of SLAM wizards working just for you!
* **Built on Solid Ground:** We're not just playing around! η-SLAM incorporates the latest research that actually *works*, ensuring a robust and reliable solution you can count on.


## Integration and Ecosystem 🤝

η-SLAM prioritizes easy integration into your existing systems:

* **Software Integration:** Robust ROS (Humble+) support and well-documented C++ APIs for flexible integration.
* **Sensors:** Wide sensor support including various cameras (mono, stereo, RGB-D), IMUs, wheel encoders, GNSS, Wifi/Bluetooth/Ultra-Wideband (UWB) beacons with ongoing expansion (2D & 3D Lidars).
* **Hardware Compatibility:** We support low to high end CPUs and can adjust the configs based on your specs.
* **Development Tools & Support:** Comprehensive SDK with examples, tutorials, clear documentation, and dedicated support for smooth onboarding.
* **Ecosystem & Partnerships:** Actively building collaborations with sensor and hardware leaders to enhance compatibility and accessibility.


## Where Will η-SLAM Take You? 🚀

η-SLAM isn't just about navigating robots; it's about empowering a whole new generation of autonomous systems to interact with the world intelligently and efficiently. Here's a glimpse into the exciting applications where η-SLAM shines:

* **Humanoid Robots:** Imagine robots that can walk, interact, and perform complex tasks in human-centric environments with a deep understanding of their surroundings. η-SLAM provides the crucial spatial intelligence for humanoid robots to navigate cities, workplaces, and even disaster zones with grace and autonomy, opening up exciting possibilities in assistance, caregiving, and more.
* **Mobile Robotics:** Guiding robots through the bustling aisles of warehouses, the corridors of hospitals, and the unpredictable paths of indoor and outdoor environments with confidence.
* **Drones and UAVs:** Enabling efficient and accurate mapping and localization for critical tasks like infrastructure inspection, package delivery that hits the mark every time, and comprehensive surveillance.
* **Service Robots:** Helping robots navigate and interact seamlessly in our  busy offices, and dynamic public spaces, making everyday life a little more automated and a lot more convenient.
* **IoT Devices:** Empowering resource-constrained smart devices with the ability to understand their location, opening up exciting new location-aware functionalities.
* **AGVs and AMRs:** Driving down costs and boosting efficiency in industrial settings with reliable and precise autonomous navigation for automated guided vehicles and autonomous mobile robots.

## The Magic Behind the Map: How η-SLAM Works (The Algorithms) 🧙‍♂️

Let's peek under the hood at the key components that make η-SLAM tick:

### Seeing is Believing: Perception 👀

* **AI Vision Integration:** η-SLAM can seamlessly process outputs from your favorite object detectors, classifiers, and image segmentation models, leveraging high-level understanding of the environment.
* **Robust Visual Features:** We've got some seriously clever visual features for tracking the system reliably, even when the lighting changes or the viewpoint shifts (up to a point). These features are so good, they even help us figure out when we've been somewhere before (loop detection & relocalization!).

### Knowing Where You're Going: Odometries 🧭

* **From Simple to Sophisticated:** η-SLAM supports a range of dead reckoning techniques, from the trusty Extended Kalman Filter (EKF) to cutting-edge trained models.
* **Eyes and Inertia Unite:** We handle both Visual Odometry (VO) and Visual-Inertial Odometry (VIO), whether you're using a single camera or multiple. This fusion of visual and inertial data provides a more robust and accurate estimate of motion.
* **Depth Perception Power-Up:** Integrating RGB-D or Depth sensors (and even monodepth models that cleverly estimate depth from a single image) is a breeze, because having depth information is always a big plus in the world of SLAM!

### The Grand Finale: η-BA, the Core Optimization ✨

Our ultimate goal? To minimize those pesky accumulated errors over time. That's where η-BA comes in! We've implemented a **super-fast** multi-sensor Bundle Adjustment (BA) that's versatile enough to be used in both the front-end (odometry) and back-end (global map optimization) of the SLAM process.

And the secret ingredient? It's built upon the amazing foundation of [Tinyopt](https://github.com/julien-michot/tinyopt) – because even our core optimization likes to be sleek and efficient!
Besides, we've implemented some ultra fast covariance extraction and the powerful ideas behind [Gtsam](https://gtsam.org)!

We've got a few handy variations of η-BA to suit different needs:

* **Full Multi-Sensor BA:** The big kahuna! This optimizes everything at once, from camera poses and states to map points as well as other sensors states such as IMU biases.
* **Pose Graph (Loop Closing):** Focusing on the bigger picture, this variant optimizes the entire trajectory of your system, especially when it recognizes a previously visited location (loop closure).
* **Smart Incremental BA (à la Gtsam):** Perfect for the odometry front-end, this efficiently optimizes only the most recent data, keeping things snappy.
* **Sensor Calibration (Intrinsic and Extrinsic):** For those meticulous moments, this allows for precise offline calibration of your sensors, ensuring they all play nicely together or simply to refine a large trajectory offline.

## Ready to Experience the η-SLAM Difference? 🤝

η-SLAM is available now and eager to empower your low-spec hardware with high-performance SLAM capabilities!

For more information, to discuss your specific needs, or to explore potential collaborations, don't hesitate to reach out [Julien](https://github.com/julien-michot).

Let's navigate the future of autonomy together!
