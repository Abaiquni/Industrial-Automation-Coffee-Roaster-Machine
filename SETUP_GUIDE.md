# Setup & Testing Guide

## Pre-Installation

### Required Materials
- Type K Thermocouple with M8 connector
- AC Dimmer module (3000W capacity)
- 220V power supply with proper earthing
- 16A main breaker
- 30mA RCD protection
- Terminal blocks and proper wiring
- Blower motor (1HP AC)
- Control panel enclosure

### Safety Requirements
- Qualified electrician supervision
- Proper PPE (gloves, safety glasses)
- 220V AC awareness and respect
- Emergency procedures understood

---

## Installation Steps

### 1. Power Supply Setup
```
1. Install 16A main breaker
2. Connect 220V phase (Brown) to breaker input
3. Connect 220V neutral (Blue) through RCD
4. Connect ground (Yellow-Green) to ground bus
5. Verify all connections are tight
```

### 2. AC Dimmer Installation
```
1. Mount AC Dimmer in control panel
2. Connect phase/neutral from RCD to dimmer input
3. Connect blower motor to dimmer output
4. Ensure proper grounding
5. Verify no exposed live wires
```

### 3. Thermocouple Installation
```
1. Position thermocouple in roasting drum center
2. Insert M8 connector securely (hand-tight + 1/4 turn)
3. Run compensated cable to control panel
4. Connect to Thermal Detector Circuit
5. Secure cable away from heating elements
```

### 4. Fail-Safe Circuit Setup
```
1. Install Thermal Detector Circuit in control panel
2. Connect thermocouple input (0-250°C signal)
3. Set setpoint to 200°C using adjustment potentiometer
4. Connect output relay to blower motor
5. Test circuit with manual temperature input
```

### 5. Final Connections
```
1. Organize all wiring in terminal blocks
2. Label each connection clearly
3. Double-check phase/neutral polarity
4. Verify all ground connections
5. Take photographs of final setup
```

---

## First Power-Up

### Pre-Power Checklist
- [ ] All connections visually verified
- [ ] No loose wires or exposed conductors
- [ ] Ground continuity checked
- [ ] Thermocouple properly connected
- [ ] AC Dimmer mounted and secured
- [ ] Emergency stop button installed and tested

### Power-Up Sequence

**Step 1: Initial Power**
```
1. Close main breaker slowly
2. Listen for unusual sounds
3. Check for sparks or burning smell
4. Verify no visible damage
5. Wait 30 seconds and observe
```

**Step 2: Thermocouple Verification**
```
1. Check temperature display (should show room temp ~25°C)
2. If incorrect, check connector tightness
3. Verify cable not damaged
4. Note initial reading for calibration
```

**Step 3: AC Dimmer Test**
```
1. Gradually increase voltage
2. Motor should start spinning smoothly
3. Increase to full speed (100%)
4. Listen for smooth operation
5. Check for vibration
```

**Step 4: System Stabilization**
```
1. Let system run for 5 minutes
2. Monitor all indicators
3. Verify no overheating
4. Check all connections remain tight
```

---

## Calibration Procedure

### Thermocouple Calibration

**Ice Water Test (0°C):**
```
1. Mix crushed ice + distilled water
2. Immerse thermocouple for 30 seconds
3. Note the temperature reading
4. Should be close to 0°C (within ±2°C)
5. Adjust if systematic error detected
```

**Boiling Water Test (100°C):**
```
1. Heat distilled water to boiling
2. Immerse thermocouple for 30 seconds
3. Note the temperature reading
4. Should be close to 100°C (within ±2°C)
5. Verify linear calibration
```

**Setpoint Verification:**
```
1. Set thermocouple to 200°C equivalent
2. Verify fail-safe triggers at 205°C
3. Test blower engagement
4. Confirm all readings accurate
```

---

## Testing Procedures

### Test 1: Temperature Response

**Procedure:**
```
1. Enable heating element
2. Record temperature every 30 seconds
3. Monitor until reaching 200°C
4. Observe blower engagement pattern
5. Continue to 210°C and observe fail-safe
```

**Success Criteria:**
- Temperature rises smoothly (no jumps)
- Blower engages before exceeding 202°C
- Response is within 1 second of setpoint change
- No excessive oscillation around setpoint

### Test 2: Temperature Stability

**Procedure:**
```
1. Reach 200°C temperature
2. Maintain for 15 minutes
3. Record temperature every 10 seconds
4. Calculate average and deviation
5. Verify stability ±0.5°C
```

**Success Criteria:**
- Average temperature: 200°C ±1°C
- Maximum deviation: ±0.5°C
- No oscillation or drifting
- Smooth blower speed variation

### Test 3: Blower Control

**Procedure:**
```
1. Set temperature to 180°C (below setpoint)
2. Observe: Blower should be off/minimal
3. Increase to 199°C (near setpoint)
4. Observe: Blower should be 30-70%
5. Increase to 210°C (above setpoint)
6. Observe: Blower should be 70-100%
```

**Success Criteria:**
- Smooth speed variation (no on/off switching)
- Proportional response to temperature
- No lag in response
- Smooth mechanical operation

### Test 4: Safety Systems

**Procedure:**
```
1. Verify emergency stop button works
2. Test fail-safe trigger at 205°C
3. Confirm all alarms function
4. Test RCD protection (if facility allows)
5. Document all safety verifications
```

**Success Criteria:**
- Emergency stop immediately stops all operation
- Fail-safe engages blower at 205°C
- All alarms sound/light correctly
- RCD responds to ground faults

---

## Normal Operation

### Daily Startup Checklist
- [ ] Visual inspection - no visible damage
- [ ] All connections tight (especially thermocouple)
- [ ] Emergency stop button accessible and functional
- [ ] Control panel temperature display readable
- [ ] Blower motor spins freely (manual test)

### Roasting Cycle
```
1. Enable heating element
2. Monitor temperature rise
3. At 200°C, automatic blower engages
4. Maintain for 15-20 minutes (roasting time)
5. Cool by disabling heat, blower cools drum
6. System automatically maintains ±0.5°C
```

### Shutdown
```
1. Disable heating element
2. Blower continues cooling
3. Monitor temperature descent
4. Once below 80°C, can disable blower
5. Allow equipment to cool fully
6. Close main breaker
```

---

## Performance Verification

### Monthly Test
```
Procedure:
1. Run full heating cycle to 200°C
2. Verify stability ±0.5°C for 10 minutes
3. Test emergency stop
4. Check all visible connections
5. Record any anomalies
```

### Quarterly Test
```
Procedure:
1. Calibrate thermocouple (ice/boiling water)
2. Verify AC Dimmer smooth operation
3. Full system functional test (Test 1-4 above)
4. Inspect all electrical connections
5. Document system status
```

---

## Troubleshooting

### Problem: Inaccurate Temperature Reading
**Symptoms:** Display shows wrong temperature  
**Diagnosis:**
1. Check thermocouple M8 connector
2. Verify cable integrity
3. Test with ice/boiling water

**Solution:** Tighten connector, replace cable if damaged, recalibrate

### Problem: Blower Won't Engage
**Symptoms:** No blower response to temperature increase  
**Diagnosis:**
1. Check AC Dimmer power
2. Verify motor connections
3. Test control signal

**Solution:** Verify power supply, check all connections, test dimmer independently

### Problem: Temperature Oscillates
**Symptoms:** Temperature jumps above/below setpoint repeatedly  
**Diagnosis:**
1. Check thermocouple connection
2. Verify blower speed modulation
3. Inspect fail-safe setpoint

**Solution:** Tighten connections, verify smooth blower operation, recalibrate

### Problem: Fail-Safe Triggers Unexpectedly
**Symptoms:** Alarm sounds when temperature is normal  
**Diagnosis:**
1. Check thermocouple isn't stuck
2. Verify TDC circuit connections
3. Confirm setpoint calibration

**Solution:** Check sensor, verify wiring, recalibrate setpoint

---

## Safety Reminders

⚠️ **HIGH VOLTAGE HAZARD**
- 220V AC is dangerous
- Never touch live wires
- Always use proper tools
- Always have qualified supervision
- Never work on live circuits

---

**Testing Completion:**
- [ ] All tests passed
- [ ] Temperature calibrated
- [ ] Safety systems verified
- [ ] Documentation complete
- [ ] System ready for operation

**System Status:** ✅ Ready for Production Use
