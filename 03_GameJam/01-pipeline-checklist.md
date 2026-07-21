---
type: jam-pipeline
version: 0.1
date: [21/07/2026]
team: [ราชันย์บัลลังคุกกี้]
---
# Pipeline Function Checklist — [Deep in the Depth]

> เกมทุกแนวต้องมี pipeline ขั้นต่ำนี้ก่อนถึงจะเรียกว่า "เล่นได้" — เติมชื่อผู้รับผิดชอบและติ๊กสถานะระหว่างลงมือทำจริง เพิ่มแถวได้ถ้าเกมของทีมต้องการ module อื่น

## Must-Have (ต้องมีก่อน Hour 24 — Playable Build)

| Module (ตาม MonoGame Game Loop)             | หน้าที่                                                                      | สถานะ     | ผู้รับผิดชอบ |
| ---------------------------------------------- | ----------------------------------------------------------------------------------- | -------------- | ------------------------ |
| `GameStateManager`                           | สลับ state (Menu / Playing / Pause / GameOver)                                  | 🔲 Not Started | [gun]                    |
| `InputManager`                               | รับ input keyboard/gamepad แบบรวมศูนย์                                | 🔲 Not Started | [gun]                    |
| Core `Update()` logic ของกลไกหลัก | logic ของ core mechanic 1 อย่างที่เป็นหัวใจเกม               | 🔲 Not Started | [gun]                    |
| Collision / interaction พื้นฐาน         | ตรวจชน/ตรวจ trigger ระหว่าง entity                                 | 🔲 Not Started | [gun]                    |
| `SpriteBatch` render + camera/viewport       | วาดผ่าน `GraphicsDevice.Viewport` (ห้าม hardcode resolution)           | 🔲 Not Started | [gun]                    |
| Win / Lose condition                           | เงื่อนไขจบเกม/จบด่าน                                             | 🔲 Not Started | [gun]                    |
| Content pipeline (MGCB)                        | โหลด asset ผ่าน `Content.Load<T>()` เท่านั้น                      | 🔲 Not Started | [gun]                    |
| ระบบ sanity                                | ทำหน้าที่เป็น HP                                                       | 🔲 Not Started | [gun]                    |
| Toch Fire                                      | เป็นแสงสว่างให้กับผู้เล่น                                  | 🔲 Not Started | [gun]                    |
| monster the trapper                            | มอน ที่มากวนผู้เล่น ไล่โดย ยืนนิ่งๆกับปิดไฟ | 🔲 Not Started | [gun]                    |
| monster stillness                              | มอน ที่มากวนผู้เล่น ไล่โดย มองมันพร้อมถือไฟ | 🔲 Not Started | [gun]                    |
| asset Map                                      | ภาพสำหรับทำ lavel                                                        | 🔲 Not Started | [Ray,Deaw]               |
| asset character                                | ภาพสำหรับทำอนิเมชั่นตัวละครผู้เล่น                | 🔲 Not Started | [Ray,Deaw]               |
|                                                |                                                                                     |                |                          |

## Nice-to-Have (ทำถ้าเหลือเวลา — Hour 24–34)

| Module                                | หน้าที่                                                           | สถานะ     | ผู้รับผิดชอบ |
| ------------------------------------- | ------------------------------------------------------------------------ | -------------- | ------------------------ |
| `AudioManager` (SFX พื้นฐาน) | เสียงตอบสนอง action หลัก                                 | 🔲 Not Started | [gun]                    |
| UI/HUD (score, timer)                 | แสดงสถานะระหว่างเล่น                                 | 🔲 Not Started | [gun]                    |
| Music / เพลงประกอบ          |                                                                          | 🔲 Not Started | [Ray]                    |
| item loot                             | มอบ item สำหรับให้ผู้เล่นใช้เอาชีวิตรอด | 🔲 Not Started | [gun]                    |
| use items                             | ทำให้ผู้เล่นสามารถใช้ไอเทมได้               | 🔲 Not Started | [gun]                    |
| monster the shadow                    | ภัยคุกคามในความมืด คอยลด sanity ผู้เล่น    | 🔲 Not Started | [gun]                    |
| NOTE ข้อความ                   | เป็นเนื้อเรื่อง                                           | 🔲 Not Started | [Note]                   |
| asset Monster                         | ภาพสำหรับทำ Monster                                          | 🔲 Not Started | [Ray,Deaw]               |

## Cut-List (ตัดทิ้งก่อนถ้าเวลาไม่พอ — ห้ามเริ่มก่อน Must-Have เสร็จ)

- ❌ Save/Load
- ❌ Settings menu
- ❌ Leaderboard
- ❌ [feature อื่นที่ทีมตกลงตัดก่อน]

> เมื่อถึง **Feature Freeze (Hour 34)** ทุก module ในตารางนี้ต้องมีสถานะ ✅ Done หรือถูกย้ายไป Cut-List อย่างชัดเจน — ห้ามค้างเป็น 🔲/🟡
