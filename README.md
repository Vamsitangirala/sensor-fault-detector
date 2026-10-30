# Smart Sensor Fault Detection & Condition Monitoring System

```{=html}
<p align="center">
```
`<strong>`{=html}An Arduino-based temperature monitoring and sensor
fault-detection prototype`</strong>`{=html}`<br>`{=html}
`<em>`{=html}Designed and simulated using Arduino Uno R3, TMP36, 16×2
LCD, LEDs and a piezo buzzer`</em>`{=html}
```{=html}
</p>
```
```{=html}
<p align="center">
```
`<a href="https://www.tinkercad.com/things/7gWcnvmMOPJ-fabulous-gaaris-blorr/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard%2Fdesigns%2Fall&sharecode=m_hNT7y3WzsNlk3MlF_z4citZpUsGVEnwZZp0xeMSeg">`{=html}
`<img src="https://img.shields.io/badge/Simulation-Open%20in%20Tinkercad-147D64?style=for-the-badge&logo=autodesk" alt="Open Tinkercad simulation">`{=html}
`</a>`{=html}
`<img src="https://img.shields.io/badge/Platform-Arduino%20Uno-00979D?style=for-the-badge&logo=arduino&logoColor=white" alt="Arduino Uno">`{=html}
`<img src="https://img.shields.io/badge/Status-Simulation%20Prototype-blue?style=for-the-badge" alt="Simulation prototype">`{=html}
```{=html}
</p>
```

------------------------------------------------------------------------

## 1. Project Overview

The **Smart Sensor Fault Detection & Condition Monitoring System** is a
small embedded-system prototype that monitors temperature using a TMP36
sensor and identifies selected abnormal operating conditions.

An Arduino Uno reads the sensor output, converts the analog reading into
temperature, and evaluates the reading against programmed conditions. A
16×2 LCD displays the temperature and current status. Green, yellow and
red LEDs provide a quick visual indication, while a piezo buzzer alerts
the user when the reported status changes. Serial Monitor output
provides additional diagnostic information.

The project demonstrates how basic sensor monitoring and
fault-identification logic can be implemented in an accessible
microcontroller-based system.

## 2. Project Objectives

-   Monitor temperature continuously using a TMP36 temperature sensor.
-   Display the measured temperature and system status on a 16×2 LCD.
-   Identify selected sensor faults and abnormal temperature conditions.
-   Provide visual alerts through three status LEDs.
-   Provide an audible alert through a piezo buzzer.
-   Report status changes and diagnostic information through the Serial
    Monitor.

## 3. System Demonstration

The images below show the Tinkercad circuit and example operating or
fault-detection states.

### Circuit and simulation

```{=html}
<p align="center">
```
`<img src="https://github.com/user-attachments/assets/90b07579-ae21-4793-b601-f12b4cc52167" alt="Tinkercad circuit overview" width="80%">`{=html}
```{=html}
</p>
```
**[Open the interactive Tinkercad
simulation](https://www.tinkercad.com/things/7gWcnvmMOPJ-fabulous-gaaris-blorr/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard%2Fdesigns%2Fall&sharecode=m_hNT7y3WzsNlk3MlF_z4citZpUsGVEnwZZp0xeMSeg)**

### Simulation screenshots

```{=html}
<p align="center">
```
`<img src="https://github.com/user-attachments/assets/4da10ff1-31d2-4a8f-9d93-7b6f1f924210" alt="System simulation screenshot 1" width="90%">`{=html}
```{=html}
</p>
```
```{=html}
<p align="center">
```
`<img src="https://github.com/user-attachments/assets/fdd59978-b3ad-46e6-b579-c15efb03123c" alt="System simulation screenshot 2" width="90%">`{=html}
```{=html}
</p>
```
```{=html}
<p align="center">
```
`<img src="https://github.com/user-attachments/assets/0c9191fe-297c-4c13-9d12-043e6d222892" alt="System simulation screenshot 3" width="90%">`{=html}
```{=html}
</p>
```
```{=html}
<p align="center">
```
`<img src="https://github.com/user-attachments/assets/e1c69c9f-add5-4cdc-814b-66f5cf38ec37" alt="System simulation screenshot 4" width="90%">`{=html}
```{=html}
</p>
```
```{=html}
<p align="center">
```
`<img src="https://github.com/user-attachments/assets/ebca6369-095e-46b7-b852-0e341bb0a288" alt="System simulation screenshot 5" width="90%">`{=html}
```{=html}
</p>
```
```{=html}
<p align="center">
```
`<img src="https://github.com/user-attachments/assets/82bcc5f5-200a-4461-94d9-9aa9497f5f75" alt="System simulation screenshot 6" width="90%">`{=html}
```{=html}
</p>
```
## 4. Components Required

  ------------------------------------------------------------------------
  Component                                 Quantity Purpose
  --------------------- ---------------------------- ---------------------
  Arduino Uno R3                                   1 Reads the sensor and
                                                     executes the
                                                     monitoring logic

  TMP36 temperature                                1 Measures temperature
  sensor                                             and provides an
                                                     analog output

  16×2 LCD                                         1 Displays temperature
                                                     and system status

  Piezo buzzer                                     1 Provides an audible
                                                     alert

  Green LED                                        1 Indicates normal
                                                     operation

  Yellow LED                                       1 Indicates warning or
                                                     temperature-change
                                                     conditions

  Red LED                                          1 Indicates fault or
                                                     critical conditions

  220 Ω resistors                               3--4 Current limiting for
                                                     LEDs / circuit
                                                     connections

  100 kΩ resistor                                  1 Pull-down arrangement
                                                     on the sensor signal

  Breadboard and jumper                  As required Circuit assembly
  wires                                              
  ------------------------------------------------------------------------

## 5. Pin Configuration

  Module / Signal   Arduino Uno pin
  ----------------- -----------------
  LCD RS            D2
  LCD Enable (E)    D3
  LCD D4            D4
  LCD D5            D5
  LCD D6            D6
  LCD D7            D7
  TMP36 output      A0
  Piezo buzzer      D8
  Green LED         D9
  Yellow LED        D10
  Red LED           D11

### TMP36 connections

With the **flat face of the TMP36 facing you**:

-   Left pin → 5V
-   Middle pin → A0 (signal output)
-   Right pin → GND

The 100 kΩ pull-down resistor is connected between the sensor signal
line and GND as used in this prototype.

## 6. Working Principle

1.  The TMP36 senses the surrounding temperature and produces an analog
    voltage.
2.  The Arduino reads this voltage through analog input A0.
3.  The program converts the analog reading into voltage and then
    temperature.
4.  The measured value is checked against programmed limits and
    sensor-condition checks.
5.  The LCD displays the temperature and detected status.
6.  LEDs and the buzzer provide visual and audible indications.
7.  The Serial Monitor reports status changes and event information.

### TMP36 temperature calculation

The TMP36 has a nominal 500 mV offset and a scale factor of 10 mV/°C.
The temperature conversion used is:

\[ T(°C) = (V\_{OUT} - 0.5) `\times 100`{=tex} \]

Here, (V\_{OUT}) is the sensor output voltage in volts.

## 7. Fault and Condition Detection

The prototype uses programmed rules to classify selected readings and
conditions.

  -----------------------------------------------------------------------
  Detected status                     Programmed condition
  ----------------------------------- -----------------------------------
  Open / GND fault                    ADC reading ≤ 10

  Short to 5V                         ADC reading ≥ 1015

  Invalid temperature                 Calculated temperature outside
                                      −40°C to 125°C

  Overheat                            Temperature ≥ 80°C

  Signal noise                        Change greater than 10°C between
                                      consecutive readings

  Sensor stuck                        ADC reading remains unchanged for
                                      30 loop iterations

  Temperature rising                  Increase greater than 3°C between
                                      consecutive readings

  Temperature dropping                Decrease greater than 3°C between
                                      consecutive readings

  Low temperature                     Temperature below 5°C

  High temperature                    Temperature ≥ 60°C and below the
                                      overheat threshold

  Normal                              None of the above conditions is
                                      detected
  -----------------------------------------------------------------------

**Note:** These are demonstration thresholds selected for this
prototype. They are not universal industrial alarm limits.

## 8. Alert Indication

  Indication       Meaning
  ---------------- -------------------------------------------------------
  Green LED        Normal operating condition
  Yellow LED       Warning or temperature-change condition
  Red LED          Sensor fault or critical temperature condition
  Piezo buzzer     Audible notification when the reported status changes
  LCD              Live temperature and current status
  Serial Monitor   Status messages and event information

## 9. Software and Tools

-   **Arduino IDE / Arduino-compatible C++** -- program development
-   **Tinkercad Circuits** -- circuit simulation and demonstration
-   **Serial Monitor** -- diagnostic output

## 10. Applications

The concepts demonstrated in this project are relevant to:

-   Temperature monitoring of motors and electrical panels
-   Basic process-equipment condition monitoring
-   Embedded sensor-monitoring systems
-   Educational demonstrations of sensor faults and alarm logic
-   Introductory predictive-maintenance concepts

These are potential application areas; this prototype has not been
validated for industrial deployment.

## 11. Limitations

-   The current prototype monitors temperature using a single TMP36
    sensor.
-   Fault identification is based on fixed thresholds and simple
    rule-based checks.
-   A stable reading may represent a genuinely stable temperature;
    therefore, a stuck-sensor warning needs further validation.
-   A sudden temperature change may be real rather than electrical
    noise.
-   The pull-down arrangement does not reliably distinguish a
    disconnected signal from every possible short-to-ground condition.
-   The selected thresholds are demonstration values and require
    application-specific calibration.
-   The project has been demonstrated in simulation; physical hardware
    testing and validation are still required.

## 12. Future Scope

The project can be extended in several ways:

1.  **Physical prototype:** Build the circuit on hardware and validate
    it under controlled temperature conditions.
2.  **Calibration:** Compare readings with a reference thermometer and
    implement calibration and drift checks.
3.  **Multi-sensor monitoring:** Add sensors for vibration, humidity,
    current or other relevant parameters.
4.  **Improved fault diagnosis:** Use more robust checks to distinguish
    wiring faults, sensor failure and genuine process changes.
5.  **Data logging:** Store readings and fault events for later analysis
    and visualisation.
6.  **IoT monitoring:** Add wireless connectivity for remote status
    updates and alerts.
7.  **Predictive maintenance:** Explore data-driven or machine-learning
    methods after collecting and validating sufficient real-world data.
8.  **Industrial implementation:** Evaluate suitable industrial sensors,
    protection, isolation, enclosures and safety requirements.

## 13. Project Documentation

The detailed project report includes the introduction, objectives,
components, circuit connections, working principle, detection logic,
simulation observations, limitations and future scope.

**[View / download the project
report](https://github.com/user-attachments/files/34194810/Smart_Sensor_Fault_Detection_Project_Report.docx)**

## 14. Project Information

  -----------------------------------------------------------------------
  Field                               Details
  ----------------------------------- -----------------------------------
  Project title                       Smart Sensor Fault Detection &
                                      Condition Monitoring System

  Student                             TVNN Vamsi Krishna

  Roll number                         25891A1023

  Branch                              Electronics & Instrumentation
                                      Engineering (EIE)

  Year / Semester                     II Year -- I Semester (2.1)

  Institution                         Vignan Institute of Technology &
                                      Science
  -----------------------------------------------------------------------

------------------------------------------------------------------------

```{=html}
<p align="center">
```
`<strong>`{=html}Built as an academic embedded-systems
project.`</strong>`{=html}`<br>`{=html} `<sub>`{=html}Simulation
prototype • Sensor monitoring • Rule-based fault
detection`</sub>`{=html}
```{=html}
</p>
```
