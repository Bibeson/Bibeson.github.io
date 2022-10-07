---
title:  "Dean's Choice Awarded Capstone Project"
header:
  video:
    id: 753615464
    provider: vimeo
# search: false
# categories: 
#  - Jekyll
last_modified_at: 2022-09-25 T08:06:00-05:00
---

In addition to my practice in nuclear research, I also have experience in Software design and development. These skills were honed throughout my final year capstone project, in which I was one part of the 5 student team in developing and manufacturing an automated motion tracking and response system for advanced soccer training.

The goal of this device was to be an accurate, portable, versatile and an accessible means of soccer training for a variety of skill levels. S.T.A.R.S. is an automated ball launching machine capable of tracking a player while pivoting. Coupled with the launcher are four small net-like targets that can detect if a ball passes through the target. From the launcher and target tracking systems, information about how well passing drills are performed (pass speed, pass timing, etc.), will be collected. The system has the added functionality of being able to anticipate player movements and launch a ball to where they are predicted to be, specifically target areas of the body (feet, chest, head). S.T.A.R.S. selectively passes to those areas, which is controllable via voice commands remotely or through a touch screen on the ball launcher. S.T.A.R.S is split up into 8 modules, which are stereoscopic vision, laser range finder, pitch and yaw motor control, launcher motor control, wireless communication, voice control/wearable device, player targets and graphical user interface.

## Module 1 Stereoscopic
The stereoscopic vision system utilizes two cameras housed on the body of the launcher that provides the system with a large field of view. The tracking system is able to recognize a player and determine the distance in the X and Y planes from the launcher to the player within 0.5 seconds using a colour tracking algorithm. For this to work, the player is required to wear a jersey of a specfic colour. This data is used to rotate and aim the launcher toward the player and adjust the speed of launcher motors to deliver the ball to the target player with a high degree of accuracy.

## Module 2 Laser Range Finder
In addition to the stereoscopic vision system, a Laser Range Finder (LRF) will be used for a more precise distance measurement, making use of an optical time-of-flight (TOF) modality. This allows for the sensor to only be located on the launcher, without necessitating a receiver on the player. Having redundant distance sensors, especially ones that are each optimal at a certain range, allows for sensor fusion to select the most reliable readings.

## Module 3 Pitch & Yaw
The pitch and yaw of the launcher will be controlled by a linear actuator and a planetary gear motor respectively. The accuracy performance will be tested indoors and will be expected to follow a soccer player traveling perpendicular to the launcher, at a maximum speed of 44 km/h, or 12m/s (Usain Bolt's record) at a distance of 10 meters in front of the launcher. With these specifications straining the pitch and yaw motor controls the most, the launcher will be able to follow any person within the range of our sensors.

## Module 4 Ball Launcher
The ball launching system consists of a hopper that is capable of storing five balls that feed into the launching mechanism, which is itself comprised of two motors rotating in opposite directions mounted on either side of a rail to guide the balls. Varying the rotational speed of the launcher motors will modify the speed at which the ball leaves the launcher, and by extension the distance it is able to travel. The central program of the device will determine an appropriate launching speed based on the distance that the player is from the target, where on the target (head, chest, feet) the ball is set to be aimed, and the level of speed at which the ball should be travelling when it reaches the player. For stationary targets and moving target, the launcher is be able to launch the ball within a range of 5 to 25 meters. 

## Module 5 Wireless Comunication

## Module 6 Voice Control/Wearable Device
Player and device interaction will utilize voice recognition features and a touch screen interface on the launcher. This software is known to be reliable, has shown positive results when tested and allows the voice recognition system on S.T.A.R.S. to achieve a final success rate for processing voice commands at an acceptable rate. This task is made easier through the use of keyword recognition, as opposed to more general recognition. This will include an activation word and preset command phrases for which the system is trained on. The communication between the wearable microphone and launcher will likely result in some lag, meaning the collective system should be able to display a speech to text output on the touchscreen interface within an acceptable time

## Module 7 Player Targets

## Module 8 Graphical User Interface
This post should not appear in the search index because it has the following YAML Front Matter:

```yaml
search: false
```

**Note:** `search: false` only works to exclude posts when using Lunr as a search provider.
{: .notice--info}

To exclude files when using Algolia as a search provider add an array to `algolia.files_to_exclude` in your `_config.yml`. For more configuration options be sure to check their [full documentation](https://community.algolia.com/jekyll-algolia/options.html).

```yaml
algolia:
  # Exclude more files from indexing
  files_to_exclude:
    - index.html
    - index.md
    - excluded-file.html
    - _posts/2017-11-28-post-exclude-search.md
    - subdirectory/*.html
```
