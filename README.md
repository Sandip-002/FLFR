# FLFR

## V1 - PID Control LFR

### Description
A Line Follower Robot (LFR) is an autonomous robot designed to follow a predefined path, typically marked by a line, using sensor-based guidance and control systems. This LFR operates on a traditional PID control system using a static set of PID parameters. It employs an infrared (IR) sensor array as its main sensing component to track the line directly beneath the robot. Arduino Nano (ATmega328) acts as the main controller. This setup offers simplicity and an optimal balance between speed and accuracy, achieving speeds of up to 1.6 m/s. However, the static PID configuration limits adaptability, leading to occasional tracking errors on complex paths or sharp turns, as the parameters are not adjusted in real-time.

### Images
![V1 Robot](images/20240310_102713.jpg)
### Features

| Feature            | Description                                      |
|--------------------|--------------------------------------------------|
| Sensor type        | Infrared (IR) sensor array straight              |
| Motor type         | 180DC planetary gear (6:1) motor, 1300rpm        |
| Motor Driver       | 2 x single channel BTS7960                       |
| Main control unit  | ATMega328P                                       |
| Control system     | Basic PID                                        |
| Operating Voltage  | 8V                                               |
| Average Speed      | 1.6 m/s                                          |
| Tire               | Silicon Rubber                                   |



---

## V2 - Camera Integrated PID Control LFR 1

### Description
In this version, a hybrid sensing system is introduced by integrating a camera module (OV7607) along with a conventional IR sensor array. To predict the line type ahead of time, a machine learning model (decision tree) was trained on collected line images, which was further deployed on a Raspberry Pi Pico (RP2040). This real-time prediction of the line is transferred to the main control unit Arduino Nano using bitstream. This setup allows adjusting base speed according to the predicted line type: higher for straight paths and lower for curves improving stability and reducing off-track incidents. With this configuration, the LFR can reach average speeds up to 1.91 m/s. However, the increased weight and processing demand result in higher response times, making it less agile and slightly constrained in high-speed scenarios.

### Images


### Features

| Feature            | Description                                      |
|--------------------|--------------------------------------------------|
| Sensor type        | Infrared (IR) sensor array straight              |
| Camera module      | OV7607                                           |
| Motor type         | 180DC planetary gear (6:1) motor, 1300rpm        |
| Motor Driver       | 2 x single channel BTS7960                       |
| Main control unit  | ATMega328P                                       |
| Control system     | Basic PID                                        |
| Operating Voltage  | 8V                                               |
| Average Speed      | 1.9 m/s                                          |
| Tire               | Silicon Rubber                                   |


---

## V3 - Camera Integrated PID Control LFR 2

### Description
The third version refines the hybrid sensing approach. The mechanical structure is optimized to be lighter. Besides, in this setup, an RP Pico replaces Arduino Nano as the main control unit, which enhances the processing speed. Additionally, a dynamic parameter-based PID control scheme is introduced where the PID parameters are a function of errors generated from the current position of the IR sensor array: larger errors result in higher Kp values. This improves the robot’s ability to handle sharp turns more accurately. The functionality of the camera module remains the same as V2. The dynamic parameter PID adaptation enables rapid, accurate response in real-time. Now the LFR is highly efficient at navigating complex paths while retaining agility and stability at high speeds and can reach up to 2.57 m/s.

### Images


### Features

| Feature            | Description                                      |
|--------------------|--------------------------------------------------|
| Sensor type        | Infrared (IR) sensor array straight              |
| Camera module      | OV7607                                           |
| Motor type         | 180DC planetary gear (6:1) motor, 1300rpm        |
| Motor Driver       | Customized dual channel BTS7960                  |
| Main control unit  | RP2040                                           |
| Control system     | Dynamic PID                                      |
| Operating Voltage  | 8V                                               |
| Average Speed      | 2.5 m/s                                          |
| Tire               | TPU rubber                                       |


