# AC-remote
Airwell RC5 and Daikin ARC466A33 remote controller protocols

# Daikin ARC466A33

## Frame1

### **Byte 0:** Header byte 0

| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 |   1 | 0 | 0 | 0 | 1 |

Fixed, always 0x11  

### **Byte 1:** Header byte1
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | 1 | 0 | 0 | 0 | 1 |

Fixed, always 0xDA

### **Byte 2:** Header byte2
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 1 | 0 | 0 | 1 | 1 | 1 |

Fixed, always 0x27

### **Byte 3:** Header byte3
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

Fixed, always 0x00

### **Byte 4:** Packet type
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | 1 | 0 | 0 | 0 | 1 | 0 | 1 |

Fixed, always 0xC5 for Frame 1

### **Byte 5:**
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 |

Fixed, always 0x10

### **Byte 6:**
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | c | 0 | 0 | 0 | 0 |

Bit7-Bit5: always 0  
Bit4: Comfort mode. 1 - ON, 0 - OFF  
Bit3-Bit0: always 0

### **Byte 7:** Checksum
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| chk7 | chk6 | chk5 | chk4 | chk3 | chk2 | chk1 | chk0 |

Bit7-Bit0: The LS byte of the sum of bytes 0 to 6

---

## Frame2

### **Byte 0:** Header byte 0

| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 |   1 | 0 | 0 | 0 | 1 |

Fixed, always 0x11  

### **Byte 1:** Header byte1
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | 1 | 0 | 0 | 0 | 1 |

Fixed, always 0xDA

### **Byte 2:** Header byte2
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 1 | 0 | 0 | 1 | 1 | 1 |

Fixed, always 0x27

### **Byte 3:** Header byte3
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

Fixed, always 0x00

### **Byte 4:** Packet type
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 1 | 0 | 0 | 0 | 0 | 1 | 0 |

Fixed, always 0x42 for Frame 2

### **Byte 5:** Current time LSB
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| t7 | t6 | t5 | t4 | t3 | t2 | t1 | t0 |

Bit7-Bit0: the current time in minutes, 7 lsb bits

### **Byte 6:** Day, Current time MSB
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | d2 | d1 | d0 | t10 | t9 | t8 |

Bit2-Bit0: the current time in minutes, upper 3 bits  
Bit5-Bit3: The day of the week  1 - Sun, 2 - Mon, 3 - Tue, 4 - Wed, 5 - Thu, 6 - Fri, 7 - Sat  
**Example:** The current time is 9:25, Wednesday. 9:25 in minutes is 9*60 + 25 = 565 = 0x235, Wednesday equals 4  
Byte5: the LSB of the time -> **0x35**  
Byte6: 4 << 3 + the 3 upper bits of the time -> 0x20 + 0x02 -> **0x22**

### **Byte 7:** Checksum
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| chk7 | chk6 | chk5 | chk4 | chk3 | chk2 | chk1 | chk0 |

Bit7-Bit0: The LS byte of the sum of bytes 0 to 6

---

## Frame3

### **Byte 0:** Header byte 0

| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 |   1 | 0 | 0 | 0 | 1 |

Fixed, always 0x11  

### **Byte 1:** Header byte1
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | 1 | 0 | 0 | 0 | 1 |

Fixed, always 0xDA

### **Byte 2:** Header byte2
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 1 | 0 | 0 | 1 | 1 | 1 |

Fixed, always 0x27

### **Byte 3:** Header byte3
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

Fixed, always 0x00

### **Byte 4:** Packet type
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

Fixed, always 0x00 for Frame 3

### **Byte 5:** Mode, Power on/off. Timer on/off
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| m3 | m2 | m1 | m0 | 0 | toff | ton | power |

Bit7-Bit4: Mode, 0 - Auto, 2 - Dry, 3 - Cool, 4 - Heat, 6 - Fan  
Bit3: always 0  
Bit2: OFF Timer, 1 - active, 0 - inactive  
Bit1: ON Timer, 1 - active, 0 - inactive  
Bit0: Power On/Off, 1 - ON, 0 - OFF  

### **Byte 6:** Temperature
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| t7 | t6 | t5 | t4 | t3 | t2 | t1 | t0 |

Bit7-Bit0: The temperature in Celsius multiplied by 2.  
**Example:** 27.5C -> 27.5*2 = 55 = **0x37**

### **Byte 7:**
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

Fixed, always 0x00

### **Byte 8:** Fan speed, Vertical swing
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| f3 | f2 | f1 | f0 | vs | vs | vs | vs |

Bit7-Bit4: Fan mode, 0x3 - FAN1, 0x4 - FAN2, 0x5 - FAN3, 0x6 - FAN4, 0x7 - FAN5, 0xA - FAN AUTO, 0xB - ECO  
Bit3-Bit0: Vertical swing, 0xF - On, Ox00 - Off

### **Byte 9:** Horizontal swing
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | 0 | hs | hs | hs | hs |

Bit7-Bit4: always 0  
Bit3-Bit0: Horizontal swing, 0xF - On, 0x0 - Off

### **Byte 10:** ON time lower bits
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| on7 | on6 | on5 | on4 | on3 | on2 | on1 | on0 |

Bit7-Bit0: ON time in minutes, 7 lsb bits

### **Byte 11:** ON time upper bits, OFF time lower bits
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| off3| off2 | off1 | off0 | on11 | on10 | on9 | on8 |

Bit7-Bit4: OFF time in minutes, 4 lsb bits  
Bit3-Bit0: ON time in minutes, 4 upper bits

### **Byte 12:** OFF time upper bits
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| off11 | off10 | off9 | off8 | off7 | off6 | off5 | off4 |

Bit7-Bit0: OFF time in minutes, 7 upper bits  
**Example:** Turn ON at 6:00, turn OFF at 2:30  
6:00 in minutes is 6 * 60 + 0 = 360 = 0x168  
2:30 in minutes is 2 * 60 + 30 = 0x096  
Byte10: the LSB of the ON time -> **0x68**  
Byte11: OFF time 4 lsb bits and the ON time 4 upper bits -> 0x6 << 4 + 0x1 = **0x61**  
Byte12: OFF time 7 upper bits ->  **0x09**

### **Byte 13:** Quiet / Powerful mode
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | q | 0 | 0 | 0 | 0 | p |

Bit7-Bit6: always 0  
Bit5: Quiet mode, 1 - On, 0 - Off  
Bit4-Bit1: always 0  
Bit0: Powerful mode, 1 - On, 0 - Off  

### **Byte 14:**
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

Fixed, always 0x00

### **Byte 15:**
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | 1 | 0 | 0 | 0 | 0 | 0 | 1 |

Fixed, always 0xC1

### **Byte 16:** Econon / Sensor / Clean mode
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | c | e | 0 | s | 0 |

Bit7-Bit5: always 0  
Bit4: Clean mode, 1 - On, 0 - Off  
Bit3: Econo mode, 1 - On, 0 - Off  
Bit2: always 0  
Bit1: Sensor mode, 1 - On, 0 - Off  
Bit0: always 0  

### **Byte 17:**
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

Fixed, always 0x00

### **Byte 18:** Checksum
| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| chk7 | chk6 | chk5 | chk4 | chk3 | chk2 | chk1 | chk0 |

Bit7-Bit0: The LS byte of the sum of bytes 0 to 17  
**Example:** Byte0 to Byte17 are: 0x11, 0xDA, 0x27, 0x00, 0x00, 0x3D, 0x24, 0x00, 0xA0, 0x00, 0x00, 0xC6, 0x1C, 0x00, 0x00, 0xC1, 0x80, 0x00 -> the sum of these bytes: 0x436, the LS byte is **0x36**  
