# SmartFallMM: A Multimodal Dataset for Enhanced Human Activity Recognition

![Sensors and their placement](images/sensor_postions.png)
The SmartFallMM dataset is a multimodal resource for Wearable Sensor-based Human Activity Recognition (WSHAR), providing synchronized data from 32 skeleton joint positions, accelerometers, and gyroscopes placed on wrists and hips. Collected using smartwatches, smartphones, meta sensors, and cameras, it includes daily activity data from both younger and older populations. This unique dataset supports the development of advanced machine learning models combining visual and non-visual data for enhanced activity recognition.

## Activities and Labels

The following table provides a summary of the activities, their corresponding labels, and the participants involved:

| **Activity**                   | **Label** | **Participants**   |
|--------------------------------|-----------|--------------------|
| Drinking Water                | 1         | Young + Old        |
| Pick Up Object                | 2         | Young + Old        |
| Put On and Take Off Jacket    | 3         | Young + Old        |
| Stepping Up                   | 4         | Old                |
| Sweeping Floor                | 5         | Young + Old        |
| Washing Hand                  | 6         | Young + Old        |
| Waving Hand                   | 7         | Young + Old        |
| TUG Test/Walking              | 8         | Young + Old (TUG for Old) |
| Sit/Stand                     | 9         | Young              |
| Backfall                      | 10        | Young              |
| Frontfall                     | 11        | Young              |
| Leftfall                      | 12        | Young              |
| Rightfall                     | 13        | Young              |
| Rotatefall                    | 14        | Young              |

## Naming Conventions

Each trial of raw labeled activity data is stored in a CSV file named using the following format:

_SIDAIDTID_

- **SID:** Unique identifier of the participant (e.g., S01, S02, etc.).
- **AID:** Unique identifier of the activity type. See the activity labels in the Table above for details.
- **TID:** Trial number for the specific activity (e.g., T01 for trial 1, T05 for trial 5, etc.).

Example: _S01A10T05_ represents participant 1 performing activity 10 (backfall) during trial 5.

## Data Organization

The data is organized in a structured directory format to facilitate easy navigation and future scalability. The folder hierarchy is as follows:

- SmartFallMM
  - **Young Data:** Contains the labeled data collected from young participants.
    - Accelerometer: Accelerometer data collected from multiple devices.
      - Phone
      - Watch
      - Meta_wrist
      - Meta_hip
    - Gyroscope: Gyroscope data collected from multiple devices.
      - Phone
      - Watch
      - Meta_wrist
      - Meta_hip
    - Skeleton: Skeleton data extracted from recorded videos.

  - **Old Data:** Contains the labeled data collected from elder participants.
    - Accelerometer: Accelerometer data collected from multiple devices.
      - Phone
      - Watch
      - Meta_wrist
    - Gyroscope: Gyroscope data collected from multiple devices.
      - Phone
      - Watch
    - Skeleton: Skeleton data extracted from recorded videos.

## Dataset Summary

- We currently have ready-to-use datasets for the following number of participants across different modalities:
  - **Young:**
    - Accelerometer: 19 pariticpants' data of phone/watch, 16 participants' data of meta sensor.
    - Gyroscope: 16 participants data of phone and watch, and 10 participants' data of meta sensors.
    - Skeleton: 15 participants' data.
  - **Old:**
    - Acceleromter: 21 participants' data of phone/watch, and 19 participants' data of meta sensors.
    - Gyroscope: 21 participants' data of phone/watch, and meta sensors.
    - Skeleton: 19 participants' data.
      
**NOTE:** Some participants lack data for certain activities and trials due to various reasons, including data corruption, technical issues, or the inability or unwillingness of participants to engage in specific activities.

## Format of CSV Files:

- **Meta Sensors:** The CSV files consist of 6 columns, without headers, representing the following data from left to right: epoch (ms), time, elapsed time (s), and x, y, and z-axis values. The data was collected at 50Hz for both old and young participants.
- **Phone and Watch:** The CSV files consist of 4 columns, without headers, representing the following data from left to right: time, x, y, and z-axis values. The data was collected at 32Hz for both old and young participants.
- **Skeleton:** The CSV files consist of 96 columns without headers. Further detail is provided below:
   - Each skeleton data contains 32 joints, where each joint is represented by three coordinates x, y, and z. Therefore, there will be 32×3=96 columns representing the positions of all joints (x, y, z for each joint).
   - The system captures data at 30 frames per second (FPS). The number of rows will depend on the duration of the activity recorded. For example, if the recording lasts for T seconds, the number of rows will be approximately 30xT.

## Inquiry/Feedback:

If you have any questions, feedback, or suggestions regarding this dataset, please feel free to contact the following individual(s):

Dr. Anne Ngu | angu@txstate.edu
