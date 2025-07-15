# Human Following Robot Using Arduino and Ultrasonic Sensors

## Overview

This project creates an autonomous human-following robot using Arduino UNO and three ultrasonic sensors. The robot can track and follow a person by measuring distances in three directions (front, left, and right) and making intelligent movement decisions based on sensor data.

## Features

- **Three-sensor setup** for 360-degree human identification
- **Real-time distance measurement** and decision-making
- **Autonomous navigation** without human assistance
- **Collision avoidance** and safe following distance maintenance
- **Bidirectional movement** (forward, backward, left, right)
- **Automatic stopping** when target is out of range

## Components Required

| Component | Quantity | Description |
|-----------|----------|-------------|
| Arduino UNO | 1 | Main microcontroller |
| HC-SR04 Ultrasonic Sensor | 3 | Distance measurement |
| L298N Motor Driver | 1 | Motor control |
| BO Motors | 2 | Drive motors |
| Wheels | 2 | Robot movement |
| Li-ion Battery 3.7V | 2 | Power supply |
| Battery Holder | 1 | Battery mounting |
| Robot Chassis | 1 | Robot frame |
| Breadboard | 1 | Circuit connections |
| Ultrasonic Sensor Holders | 3 | Sensor mounting |
| Switch | 1 | Power control |
| Jumper Wires | - | Connections |

## Circuit Connections

### Arduino to HC-SR04 Ultrasonic Sensors

| Sensor | Arduino Pin | HC-SR04 Pin |
|--------|-------------|-------------|
| Sensor 1 (Front) | Pin 2 | TRIG |
| Sensor 1 (Front) | Pin 3 | ECHO |
| Sensor 2 (Left) | Pin 4 | TRIG |
| Sensor 2 (Left) | Pin 5 | ECHO |
| Sensor 3 (Right) | Pin 6 | TRIG |
| Sensor 3 (Right) | Pin 7 | ECHO |
| All Sensors | 5V | VCC |
| All Sensors | GND | GND |

### Arduino to L298N Motor Driver

| Arduino Pin | L298N Pin |
|-------------|-----------|
| Pin 8 | IN1 |
| Pin 9 | IN2 |
| Pin 10 | IN3 |
| Pin 11 | IN4 |
| 5V | VCC |
| GND | GND |

### Motor Driver to Motors

| L298N Pin | Connection |
|-----------|------------|
| OUT1 | Left Motor + |
| OUT2 | Left Motor - |
| OUT3 | Right Motor + |
| OUT4 | Right Motor - |

### Power Supply

- Connect 2x 3.7V Li-ion batteries in series (7.4V total)
- Connect positive terminal to L298N +12V input
- Connect negative terminal to L298N GND
- Use switch for power control

## Code Configuration

### Distance Thresholds

```cpp
#define MAX_DISTANCE 40        // Maximum following distance (cm)
#define MIN_DISTANCE_BACK 5    // Minimum distance before backing up (cm)
```

### Motor Speed Settings

```cpp
#define MAX_SPEED 150          // Maximum motor speed (0-255)
#define MIN_SPEED 75           // Minimum motor speed (0-255)
```

## How It Works

1. **Distance Measurement**: Three ultrasonic sensors continuously measure distances in front, left, and right directions
2. **Decision Making**: Arduino processes sensor data and determines the closest object/person
3. **Movement Control**: Based on sensor readings, the robot:
   - Moves forward if person is directly ahead
   - Turns left if person is on the left side
   - Turns right if person is on the right side
   - Moves backward if too close to avoid collision
   - Stops if no person is detected within range

## Installation and Setup

1. **Hardware Assembly**:
   - Mount ultrasonic sensors on robot chassis
   - Connect components according to circuit diagram
   - Secure batteries and ensure proper power connections

2. **Software Setup**:
   - Install Arduino IDE
   - Connect Arduino UNO to computer
   - Upload the provided code
   - Open Serial Monitor for debugging

3. **Calibration**:
   - Adjust `MAX_DISTANCE` and `MIN_DISTANCE_BACK` values based on your requirements
   - Fine-tune motor speeds for optimal performance
   - Test in open area for proper functionality

## Usage

1. Power on the robot using the switch
2. The robot will start scanning for objects/persons
3. Stand in front of the robot within the detection range
4. The robot will automatically follow your movement
5. Move slowly to allow the robot to track properly

## Troubleshooting

### Common Issues

- **Robot doesn't move**: Check motor connections and battery voltage
- **Sensors not working**: Verify ultrasonic sensor connections and power supply
- **Moves in wrong direction**: Check motor wiring polarity
- **Erratic behavior**: Ensure proper grounding and stable power supply

### Debugging

- Use Serial Monitor (9600 baud) to view sensor readings
- Check distance values for all three sensors
- Verify movement commands in serial output

## Applications

- **Retail**: Shopping cart robots in malls
- **Hospitality**: Luggage-carrying robots in airports/hotels
- **Security**: Patrol robots for surveillance
- **Healthcare**: Elderly care assistance robots
- **Education**: Learning and demonstration projects
- **Entertainment**: Interactive companion robots

## Safety Considerations

- Always test in open areas first
- Ensure emergency stop mechanism
- Monitor battery levels regularly
- Keep safe distance during operation
- Avoid testing near stairs or hazardous areas

## Future Enhancements

- Add camera for visual tracking
- Implement voice control features
- Add obstacle avoidance algorithms
- Integrate GPS for outdoor navigation
- Add smartphone app control
- Implement machine learning for better tracking

## References

- Original Tutorial: [Human Following Robot Using Arduino and Ultrasonic Sensor](https://circuitdigest.com/microcontroller-projects/human-following-robot-using-arduino-and-ultrasonic-sensor)
- Arduino Documentation: [arduino.cc](https://www.arduino.cc)
- HC-SR04 Datasheet: Ultrasonic sensor specifications
- L298N Motor Driver Guide: Motor control documentation

## License

This project is open-source and available under the MIT License.

## Contributing

Contributions are welcome! Please feel free to submit issues, feature requests, or pull requests.

---

**Note**: This project is intended for educational and hobbyist purposes. Always follow safety guidelines when working with electronics and mechanical components.
