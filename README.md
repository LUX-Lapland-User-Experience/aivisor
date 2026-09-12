# Cough-Activated Face Visor

A prototype wearable visor that uses **TinyML** to detect coughing in real time and automatically moves a transparent visor into a protective position.

The project explores how embedded machine learning and responsive wearables can be used to create personal protective equipment (PPE) that reacts to its environment.

## How it works

An **Arduino Nano 33 BLE Sense** continuously listens for audio through its built-in microphone. A TinyML model classifies the sound as either `cough` or `noise`.

When a cough is detected above a defined confidence threshold, two servo motors move the visor into position. After a defined period without further cough detection, the visor returns to its open position.

## Hardware

- Arduino Nano 33 BLE Sense
- 2× servo motors
- 3D-printed servo mounts
- Modified 3M face visor

## Machine Learning

The cough detection model was developed using **[Edge Impulse](https://www.edgeimpulse.com/)**.

The implementation is based on the cough detection approach described in the following tutorial:

> **Edge Impulse — Cough Detection with TinyML on Arduino**  
> https://www.hackster.io/edge-impulse/cough-detection-with-tinyml-on-arduino-417f37

The original approach uses **MFCC audio processing** and a small convolutional neural network to classify one-second audio samples as `cough` or `noise`.

The original dataset is small and intended for experimentation. As a result, the model has limited performance with different voices, coughs and background environments.

## Prototype

The original cough detection system was extended into a physical wearable prototype by integrating the TinyML model with a motorized visor mechanism.

The project combines:

- Embedded machine learning
- Audio classification
- Arduino programming
- Servo-controlled mechanisms
- 3D-printed components
- Wearable interaction design

## Credits

This project builds upon the work presented by **Edge Impulse** in:

**Cough Detection with TinyML on Arduino**  
https://www.hackster.io/edge-impulse/cough-detection-with-tinyml-on-arduino-417f37

The original project and dataset were developed as part of the **UN Covid Detect & Protect Challenge**.

## Disclaimer

This is an experimental prototype and **not a medical device**. The cough detection model should not be used for medical diagnosis, disease detection or reliable infection prevention.