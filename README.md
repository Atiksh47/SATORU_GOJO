# SATORU GOJO - Cursed Technique Visualizer

An interactive web application that brings Jujutsu Kaisen's cursed techniques to life through hand gesture recognition and real-time 3D particle visualization.

## Overview

This project uses computer vision and 3D graphics to create an immersive experience where users can control different cursed energy manifestations by performing specific hand gestures in front of their webcam. Inspired by Satoru Gojo's abilities from Jujutsu Kaisen, the app features four main cursed techniques: Red, Void, Purple, and Domain Expansion: Malevolent Shrine.

## Features

- **Real-time Hand Tracking**: Uses MediaPipe's hand detection for gesture recognition
- **3D Particle Systems**: Powered by Three.js with bloom effects for stunning visuals
- **Gesture-Based Controls**:
  - **Neutral**: Default state with minimal particles
  - **Red**: Reverse cursed technique with spiraling red energy
  - **Void**: Domain expansion with infinite void particles
  - **Purple**: Hollow purple with explosive particle effects
  - **Shrine**: Malevolent shrine domain with structured formations
- **Responsive Design**: Adapts to different screen sizes
- **Film Grain Effect**: Adds cinematic atmosphere

## How to Use

1. Open `index.html` in a modern web browser
2. Grant camera permissions when prompted
3. Position your hand in front of the webcam
4. Perform gestures to activate different techniques:

   - **Red**: Extend index finger only
   - **Void**: Extend index and middle fingers
   - **Purple**: Pinch thumb and index finger together
   - **Shrine**: Extend all fingers (open palm)

## Requirements

- Modern web browser with WebGL support (Chrome, Firefox, Safari, Edge)
- Webcam access
- Internet connection (for loading external libraries)

## Technologies Used

- **Three.js**: 3D graphics and particle systems
- **MediaPipe**: Hand tracking and gesture recognition
- **HTML5 Canvas**: Video processing and overlay
- **Post-processing Effects**: Bloom and grain effects

## Browser Compatibility

Works best in:
- Google Chrome 88+
- Mozilla Firefox 85+
- Microsoft Edge 88+
- Safari 14+

## Performance Notes

- The application uses GPU-accelerated rendering
- Particle count is optimized for smooth performance
- May require a decent graphics card for best experience

## Credits

Inspired by Jujutsu Kaisen manga/anime series by Gege Akutami.

## License

This project is for educational and entertainment purposes only.