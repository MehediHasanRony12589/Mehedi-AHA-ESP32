# Mehedi-AHA-ESP32
## **Reproducibility Steps**  
1. Hardware:  
   - ESP32 DevKitC + PN532 + MLX90640  
   - 5V/3A power supply  

2. Software:  
   ```bash
   git clone https://github.com/yourusername/aha-esp32.git
   platformio run --target upload --environment esp32dev

   # Thermal sensor calibration script
python calibrate_mlx.py --threshold 34.0

### **2. Unit Tests (`test/test_sensors.ino`)**
```cpp
void testHumanDetection() {
  mockPIR(HIGH);
  mockThermal(35.0); // Simulate human
  assert(detectHuman() == true); // Pass
}
