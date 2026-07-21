---
type: gdd-mechanics
version: 0.1
date: [วันที่]
---
# Mechanic Design — [Movement]

## State Diagram

```mermaid
stateDiagram-v2
    [*] --> Idle
    Idle --> Move : กด Arrow/WASD
    Move --> Jump : กด Space
    Jump --> Fall : ตกจากจุดสูงสุด
    Fall --> Idle : แตะพื้น
    Idle --> Climbing/interact : กด E
   Climbing/interact --> Idle : end animation

```

Mechanic Design — [fear]

```mermaid
stateDiagram-v2
    [*] --> fearน้อย
    [*] --> fearเยอะ
    fearน้อย --> เพิ่มfear : ถูกโจมตี/อยู่ใกล้สิ่งน่ากลัว/อยู่ในความมืด
    fearเยอะ --> fear
    fear --> เดินช้าขึ้น_ไฟสรัว_มอนเดินเร็วขึ้น
  

```

## Mechanic Design — [Torch]

```mermaid
stateDiagram-v2
    [*] --> Torch		  
    Torch --> light
    light --> ลดการเพิ่มค่าfear : เมื่ออยู่ใกล้แสง
    Dark --> เพิ่มFear : เมื่ออยู่ในที่มืด
    light --> Dark : กด t
    light --> Dark : เมื่อเวลาผ่านไป

```

## Rules

| State | เข้าเงื่อนไข                        | ออกเงื่อนไข                       | Note               |
| ----- | ----------------------------------------------- | -------------------------------------------- | ------------------ |
| Idle  | เริ่มเกม / หยุดเคลื่อนที่ | กด input ใดๆ                            | Animation loop     |
| Move  | กดปุ่มทิศทาง                        | ปล่อยปุ่ม / กระโดด            | Speed = [ค่า]   |
| Jump  | กด Space ขณะอยู่พื้น               | ถึงจุดสูงสุด                     | Gravity = [ค่า] |
| fear  | ค่า Fear ถึงระดับที่กำหนด    | หายไปเมื่อเวลาผ่านไป     | max 100            |
| ligh  | มี Torch อยู่ และกด T                | Torch หมด หรือกด T อีกครั้ง | dulability 100     |
