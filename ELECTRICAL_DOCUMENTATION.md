# Electrical System Documentation

## System Architecture

### Control System Block Diagram

```
INPUT                  CONTROL                OUTPUT
┌─────────────────┐   ┌──────────────┐   ┌──────────────┐
│  Thermocouple   │   │  Thermal     │   │  AC Dimmer   │
│  (0-250°C)      ├──→│  Detector    ├──→│  Module      │──→ Blower Motor
│                 │   │  Circuit     │   │  (0-220V)    │    (0-100%)
└─────────────────┘   └──────────────┘   └──────────────┘
                            ↑
                      Setpoint: 200°C
```

## Main Components

### 1. Temperature Sensor
**Type K Thermocouple**
- Range: -200°C to +1350°C
- Accuracy: ±0.75% of reading
- Response time: < 1 second
- Location: Roasting drum center
- Connector: M8 threaded fitting
- Cable length: 2 meters (compensated)

### 2. Thermal Detector Circuit (TDC)
**Hardware Fail-Safe System**
- Independent of any control board
- Setpoint: 200°C ±2°C (adjustable)
- High-temperature cutoff: 205°C
- Response time: < 100ms
- Function: Engages blower at 100% if temperature exceeds limit

### 3. AC Dimmer Module
**Power Control Unit**
- Input: 220V AC ±10%, 50Hz
- Output: 0-220V variable voltage
- Power rating: 3000W continuous
- Control signal: Analog 0-5V
- Function: Modulates power to blower motor
- Enables smooth speed control (0-100%)

### 4. Main Power Distribution
- **Supply voltage:** 220V AC single phase
- **Main breaker:** 16A (protects entire circuit)
- **RCD protection:** 30mA (ground fault detection)
- **Grounding:** Proper earth connection to all metal frames

### 5. Blower Motor
- **Type:** 1HP AC motor
- **Speed range:** 0-100% via AC Dimmer
- **Function:** Cooling and chaff extraction
- **Control:** Variable speed modulation

## Wiring Configuration

### Power Circuit
```
220V Phase (Brown) ──→ [16A Breaker] ──→ [30mA RCD] ──→ [Distribution]
220V Neutral (Blue) ─────────────────────────────────→ [Distribution]
Ground (Yellow-Green) ──────────────────────────────→ [Ground Bus]
```

### AC Dimmer Connection
```
AC Dimmer Input:  220V Phase + Neutral from RCD
AC Dimmer Output: 0-220V variable to Blower Motor
Control Signal:   0-5V from Thermal Detector Circuit
```

### Thermocouple Connection
```
Thermocouple (in drum) ──→ M8 Connector ──→ Control Panel ──→ TDC Input
```

## Control Logic

### Temperature Control Operation

**Below Setpoint (< 198°C):**
- Blower: OFF (0%)
- Purpose: Allow heating

**Near Setpoint (198-202°C):**
- Blower: 30-70% speed
- Purpose: Maintain temperature

**Above Setpoint (> 202°C):**
- Blower: 70-100% speed
- Purpose: Cool rapidly

**Emergency (> 205°C):**
- Blower: 100% (fail-safe engaged)
- Alarm: Active
- Purpose: Prevent overheat damage

## Electrical Protection

### Circuit Protection
- **Main Breaker:** 16A protects main supply
- **RCD:** 30mA ground fault protection
- **Thermal Cutoff:** TDC fail-safe at 205°C
- **Emergency Stop:** Manual circuit disconnection

### Safety Features
- Hardware fail-safe independent of software
- Ground fault detection (RCD)
- Over-current protection (breaker)
- Emergency shutdown button
- Temperature monitoring with alarms

## Component Specifications

### Thermocouple Specifications
```
Type: K (Chromel-Alumel)
Range: -200 to +1350°C
Accuracy: ±0.75% of reading
Tolerance: Class 1
Response time: < 1 second
Color code: Red (positive), Green (negative)
```

### AC Dimmer Specifications
```
Input voltage: 220V AC ±10%
Input frequency: 50Hz
Output voltage: 0-220V AC
Power capacity: 3000W
Control input: 0-5V DC
Dimming range: 0-100% smooth
Response time: < 100ms
Heat dissipation: ~20W @ 50% load
```

### Thermal Detector Circuit
```
Technology: Analog comparator
Reference voltage: 200°C setpoint
Hysteresis: ±2°C
High-temp trigger: 205°C
Response: < 100ms
Output: Relay activation
Power supply: 24V DC (independent)
```

## Testing & Verification

### Thermocouple Calibration
- **0°C:** Ice water test (verify reading ~0°C)
- **100°C:** Boiling water test (verify reading ~100°C)
- **Accuracy tolerance:** ±2°C

### AC Dimmer Testing
- **0V input:** Motor 0% (not running)
- **2.5V input:** Motor 50% (medium speed)
- **5V input:** Motor 100% (full speed)
- **Smoothness:** No abrupt speed changes

### System Response Testing
- **Ramp rate:** ~1°C per 30 seconds
- **Stability band:** ±0.5°C at setpoint
- **Response time:** < 1 second to disturbance
- **Noise level:** < 55 dB at 1m distance

## Maintenance

### Regular Checks (Monthly)
- Visual inspection of all connections
- Verify thermocouple connector is tight
- Test emergency stop button
- Check for any burnt smell or discoloration

### Quarterly Checks
- Thermocouple accuracy verification
- AC Dimmer operation check
- Breaker and RCD testing
- Full system functional test

### Annual Maintenance
- Complete electrical system inspection
- Thermal imaging of connections
- Component replacement if degraded
- Safety certification review

## Troubleshooting

### Temperature Reading Error
**Symptoms:** Display shows wrong temperature  
**Solutions:**
- Tighten thermocouple M8 connector
- Check cable for damage
- Verify no loose connections
- Recalibrate with ice/boiling water

### Blower Not Responding
**Symptoms:** Blower doesn't change speed with temperature  
**Solutions:**
- Verify AC Dimmer has power
- Check motor connections
- Test motor manually with known voltage
- Verify control signal (0-5V) is present

### Fail-Safe Triggering
**Symptoms:** Alarm sounds when temperature is normal  
**Solutions:**
- Check thermocouple isn't stuck
- Verify TDC circuit connections
- Recalibrate setpoint
- Test with manual temperature input

---

**Last Updated:** December 2025  
**Documentation Status:** Complete
