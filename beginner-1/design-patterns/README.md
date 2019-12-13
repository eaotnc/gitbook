---
description: หลักในการออกแบบซอฟต์แวร์โดยการนำ Design Patterns มาประยุกต์ใช้
---

# 👦 Design Patterns

## 🤨 Design Patterns คือไรหว่า ?

เวลาที่เราเจอ **ปัญหา** ในการออกแบบโค้ดนั้น เชื่อไหมว่าส่วนใหญ่มันจะเป็นปัญหาเรื่องเดิมๆที่เหล่า Programmer ทั่วโลกก็เจอกัน ดังนั้นมันเลยมีกลุ่มคนที่คิด **วิธีการแก้ปัญหาที่เรามักจะเจอในการออกแบบซอฟต์แวร์** เอาไว้ โดยเรียกวิธีการแก้ปัญหาต่างๆว่า **Design Patterns** นั่นเอง ดังนั้นในรอบนี้เราจะทำความเข้าใจ **หัวใจ** และ **ข้อดีข้อเสีย** พร้อมกับการทำ **Good practices** ต่างๆในการออกแบบโดยใช้ **Object-Oriented Programming \(OOP\)** ไปพร้อมๆกันเลย

ดังนั้นโดยสรุป **Design Patterns** คือ `แนวคิด` ในการแก้ปัญหาของการออกแบบซอฟต์แวร์ ที่เรามักจะเจอบ่อยๆนั่นเอง

{% hint style="info" %}
**เกร็ดความรู้**  
กลุ่มคนที่ประกาศให้โลกได้รู้จักคำว่า Design Patterns นั้นมีด้วยกัน 4 คน ดังนั้นเรามักจะได้ยินคำว่า **Gang of Four \(GoF\)** เมื่อพูดถึงเรื่องนี้ด้วย โดยพวกเขาเขียนหนังสือที่ชื่อว่า **Design Patterns: Elements of Reusable Object-Oriented Software** ขึ้นมา ซึ่งภายในหนังสือนั้นอธิบายถึง Design Patterns 23 ตัว ที่เรากำลังจะได้เรียนรู้จักคอร์สนี้นั่นเอง
{% endhint %}

## 🤨 ทำไมต้องเรียนตัวนี้ ?

ผมมี 3 คำตอบที่น่าจะหนักแน่นพอให้เราสละเวลาทำความเข้าใจเรื่อง Design Patterns ต่างๆตามนี้

1. **ได้เรียนรู้การออกแบบ** - เพราะ Design Patterns แต่ละตัวจะสอนการออกแบบให้รู้ถึง ข้อดี/ข้อเสีย ของมัน และแบบอื่นๆไปในตัว ดังนั้นมันเลยเป็นบทเรียนที่เหมาะกับ คนที่กำลังศึกษาการออกแบบ เพราะมันจะช่วยเปิดโลกให้เห็นหลักในการออกแบบ และ Practices หลายๆอย่างรวมอยู่ในนั้นเลย
2. **ประหยัดเวลา** - เพราะมันคือ **บทสรุปในการแก้ปัญหา** ที่ทั่วโลกนิยมและรู้จักกัน ดังนั้นเราไปเจอปัญหาแบบเดียวกับเขา เราก็สามารถ **ลอกคำตอบ** ที่เขาคิดไว้แล้วไปใช้ได้เลยนั่นเอง
3. **มันเป็นคำศัพท์** - เพราะเวลาที่เราคุยกับ Developer คนอื่นๆว่าเรากำลังเจอปัญหาอะไรอยู่ หรือจะแก้มันยังไง บางทีแค่พูดชื่อของ Design Patterns ก็อาจจะทำให้ทุกคนเข้าใจสถานะการณ์หรือคำตอบได้เร็วขึ้น เลยทำให้มันเป็นหนึ่งใน **คำศัพท์** ที่ช่วยให้พวก Developer เข้าใจกันได้มากขึ้นนั่นเอง

## 😈 ข้อควรระวัง

แม้ว่า Design Patterns จะเป็นเหมือนบทสรุปในการแก้ปัญหา ที่รอให้เราไปลอกคำตอบเขามาก็ใช้ได้เลย แต่อย่าลืมว่า  **ของฟรีและดีไม่มีอยู่จริง** เพราะทุก Design Patterns นั้นจะมีข้อเสียที่ตามมากับมันด้วยเสมอ ดังนั้น **อย่าเมากาว** ตะบี้ตะบันเอา pattern ไปใช้กับงานเสมอ เราต้อง **ชั่งน้ำหนักว่ามันคุ้มไหม** ที่เราจะนำ pattern แต่ละตัวมาใช้นั่นเอง

{% hint style="danger" %}
**คำเตือน**  
การนำ Design Pattern ไปใช้ไม่ใช่เรื่องเท่ เพราะมันมี **Cost** \(memory, processing overhead & complexity\) ของมันค่อนข้างสูง ดังนั้นก่อนใช้ให้ **ชั่งน้ำหนัก ข้อดี/ข้อเสีย** ให้ดีก่อน ไม่งั้นโค้ดจะทำงานได้แต่ maintenance ยากขึ้นโดยใช่เหตุ **ดังนั้นอย่าเมากาวแล้วตะบี้ตะบันเอา pattern ไปใช้เลยตลอดเวลา** ซึ่ง pattern แต่ละตัวมันต้องอาศัยประสบการณ์มาถึงระดับหนึ่ง มันถึงจะเข้าใจข้อดีข้อเสียของมันได้จริงๆเท่านั้น \(แมวน้ำได้เตือนแล้วนะ\)
{% endhint %}

![iconka.com](../../.gitbook/assets/image%20%2854%29.png)

{% hint style="success" %}
### Master of Design จะไม่ใช้ Design Patterns จนกว่ามันจะจำเป็นจริงๆเท่านั้น
{% endhint %}

## ❤️ แนวคิดในการศึกษาเรื่องนี้

หัวใจหลักในการศึกษา Design Patterns ต่างๆนั้น \(ส่วนตัวของผม\) คือ

> **เรียนรู้หลักปฎิบัติในการออกแบบ** - เพราะ patterns ทุกตัวมันจะบอกข้อเสียของการออกแบบ Object-Oriented ที่ไม่ดี และวิธีการออกแบบที่ควรจะเป็น หรือที่เราเรียกว่า **Best Practices** เอาไว้ ซึ่งเจ้าสิ่งนั้นต่างหากที่มันเป็นสิ่งที่ Developer ควรที่จะศึกษา เพื่อที่จะได้นำเป็นเป็น **ทางเลือก** ในการแก้ปัญหาหน้างานของตัวเอง

ส่วนรายละเอียดของ Design Patterns ทั้ง 23 ตัวถือว่าเป็นความรู้โบนัสที่ **รู้ติดตัวก็ดีไม่รู้ก็ได้** เพราะสิ่งที่เราควรศึกษาจริงๆคือ **แนวคิด** ต่างหาก เพราะผมคิดว่า Software มันเป็นงานที่ต้องออกแบบเฉพาะเรื่องของมันนั่นเอง

## 💎 กลุ่มของ Patterns

Design Patterns พื้นฐานทั้ง 23 ตัวนั้น มันถูก **แบ่งออกเป็น 3 กลุ่มตามลักษณะในการแก้ไขปัญหาของมัน** นั่นเอง ดังนั้นเวลาที่เราเจอปัญหา แล้วเราจะเลือก Design Patterns มาใช้นั้น เราก็จะดูว่า **ปัญหา** ของเรานั้นมันเป็นกลุ่มไหน แล้วค่อยเลือกต่อว่า Patterns ในกลุ่มนั้นๆ มันแก้ปัญหาเรื่องอะไร แล้วเราค่อยหยิบมันไปแก้ไขปัญหาของเรานั่นเอง ดังนั้นเรามาเรียนรู้ว่าแต่ละกลุ่มจะแก้ปัญหาเรื่องอะไรกันดีกว่า

### 🔥 Creational Patterns

![](../../.gitbook/assets/image%20%28694%29.png)

กลุ่มนี้จะช่วยให้ developer ไม่ต้องเสียเวลาในการ **สร้าง object** ซึ่งแม้ว่ามันจะสร้างง่ายๆด้วยคำสั่ง `new` เท่านั้นก็ตาม เพราะการสร้าง object ด้วยตัวเองมันคือ **Hardcode** แบบหนึ่งนั่นเอง ดังนั้นถ้าเรามีปัญหาเรื่อง การสร้าง object ให้เรามองมาที่ Patterns ต่างๆที่อยู่ในกลุ่มนี้ได้เลย

{% hint style="info" %}
**Hardcode**  
คือการทำอะไรบางอย่างลงไปในโค้ดของเรา ที่เวลาเราแก้ไขเจ้าสิ่งนั้นเราจะต้องทำการ Compile ตัวโค้ดเราใหม่ทั้งหมด ไม่งั้นจะแก้ไขมันไม่ได้
{% endhint %}

### 🔥 Structural Patterns

![](../../.gitbook/assets/image%20%28459%29.png)

กลุ่มนี้จะช่วยให้เราออกแบบและทำงานกับ **โครงสร้างที่ซับซ้อน** ได้แบบง่ายๆ เช่น โค้ดเราต้องไปทำงานกับ module ที่มีความซับซ้อนสูง หรือยิ่งนานโค้ดที่เราทำงานอยู่มันก็จะยิ่งซับซ้อนเข้าไปเรื่อยๆ ดังนั้นเจ้ากลุ่มนี้จะช่วยละลายความซับซ้อนที่จะเกิดขึ้นเหล่านั้นให้หายไป ให้เราสามารถใช้งานได้โดยไม่ต้องไปสนใจความซับซ้อนที่อยู่เบื่องหลังของมันนั่นเอง

### 🔥 **Behavioral patterns**

![](../../.gitbook/assets/image%20%28728%29.png)

กลุ่มนี้จะช่วยให้คลาสต่างๆ **ทำงานร่วมกัน** ได้ง่ายๆ เพราะทุกครั้งที่เราเพิ่มความสามารถใหม่ๆเข้าไปในโค้ด นั่นหมายถึง คลาสต่างๆที่เรามีอยู่ ไม่ว่าจะเป็นตัวใหม่ หรือ ตัวเก่า มันก็จะต้องทำงานร่วมกันได้อย่างเหมาะสม ดังนั้นเจ้ากลุ่มนี้จะเป็นตัวชี้ทางสว่างว่า ถ้าเจอสถานะการณ์แบบนี้ เราควรจะออกแบบยังไงนั่นเอง

## 🧭 เนื้อหาทั้งหมดของคอร์สนี้

{% hint style="info" %}
คอร์สนี้กำลังค่อยๆเขียนอยู่ ใครที่ไม่อยากพลาดอัพเดทก็เข้าไปกดติดตามที่ลิงค์นี้ [**Mr.Saladpuk**](https://www.facebook.com/mr.saladpuk) ได้เลย ส่วนใครที่อยากศึกษา pattern ตัวไหนล่วงหน้าก็ไปอ่านบทความเก่าได้ที่ลิงค์นี้ [🤴 Design Patterns](https://saladpuk.gitbook.io/learn/software-design/designpatterns) \(อ่านแล้วเมากาวไม่รู้ด้วยนะ\)
{% endhint %}

### 🤰 [Creational Patterns](https://saladpuk.gitbook.io/learn/beginner-1/design-patterns/creational)

* Factory Method Pattern
* Abstract Factory Pattern
* Builder Pattern
* Prototype Pattern
* Singleton Pattern

### 🦈 Structural patterns

* Adapter Pattern
* Bridge Pattern
* Composite pattern
* Decorator Pattern
* Facade Pattern
* Flyweight pattern
* Proxy Pattern

### 🦈 Behavioral patterns

* Chain of Responsibility Pattern
* Command Pattern
* Interpreter pattern
* Iterator Pattern
* Mediator Pattern
* Memento Pattern
* Observer Pattern
* State Pattern
* Strategy Pattern
* Template Method Pattern
* Visitor Pattern

## 🤨 คอร์สนี้ต่างจากอันเดิม ?

เพื่อนๆที่ติดตามสลัดผักมาตั้งแต่ยุกต์เริ่มต้น ก็น่าจะเห็นคอร์สเรื่อง [🤴 Design Patterns](https://saladpuk.gitbook.io/learn/software-design/designpatterns) ที่อยู่เมนูด้านล่างสุดมานานแล้ว เลยอาจจะส่งสัยว่ามันต่างกันคอร์สนั้นยังไงชิมิ? ... ผมขอตอบเลยว่า ใจความสำคัญ มันไม่ได้ต่างกันหรอก ถ้าอ่านตัวนั้นแล้วเข้าใจ ก็ไม่ต้องอ่านคอร์สนี้ก็ได้ เพียงแค่คอร์สเก่าผมกลับไปอ่านแล้วรู้สึกว่ามันเมากาวมากไปหน่อย และมันถูกเขียนตั้งแต่ยังไม่มีสลัดผักเลย ดังนั้นในรอบนี้ผมจะอธิบายโดยเน้นไปที่หัวใจสำคัญจริงๆของมัน + ใช้เกมมาช่วยในการอธิบายจะได้เข้าใจมากยิ่งขึ้นกันครัช
