# sorting-of-numbers
## Aim
To write and execute an Assembly Language Program for sorting data in Ascending and  descending order using 8051 microcontroller on Keil software.
---

## Apparatus Required
- Personal Computer  
- Keil µVision software  
---

## Algorithm(ASCENDING ORDER)
1. Initialize the register **R7** with count (number of elements).  
2. Get the first two elements into two registers.  
3. Compare the two elements:  
   - If the value in register **R0** is lower, exchange **A** and **R0** data.  
   - Otherwise, increment pointer and decrement register **R7**.  
4. Check if **R7 = 0** → if yes, move the register **R0 & A**.  
5. Increment pointer and decrement **R7**.  
6. If **R7 ≠ 0**, repeat from Step 2.  
7. Otherwise, stop the program.  
---

## Program (Ascending order)
ORG 0000H

MOV R1,30H        ; Outer loop count = N
DEC R1

LOOP1: MOV R0,#40H
       MOV R6,30H
       DEC R6

LOOP:  MOV A,@R0
       INC R0
       MOV B,@R0

       CJNE A,B,NEXT

NEXT:  JC DOWN        ; If A < B, no swap

       MOV @R0,A      ; Swap if A > B
       DEC R0
       MOV @R0,B
       INC R0

DOWN:  DJNZ R6,LOOP
       DJNZ R1,LOOP1

END
```asm




```
## OUTPUT(Ascending order)


<img width="960" height="500" alt="WhatsApp Image 2026-05-21 at 10 39 58 AM" src="https://github.com/user-attachments/assets/8ce70fa1-fdd9-49e2-8ee6-9edf278f63f8" />

---

## Algorithm(Descending order)
1. Initialize the register **R7** with count.  
2. Get first two elements in two registers.  
3. Compare the two elements of data:  
   - If the value of **R0** register is high, then exchange **A** and **R0** data.  
   - Else, increment pointer and decrement register **R7**.  
4. Check if **R7 = 0**, then move the contents of **R0** and **A**.  
5. Again increment pointer and decrement **R7**.  
6. Check if **R7 = 0**:  
   - If **No**, repeat the process from Step 2.  
   - If **Yes**, stop the program.  
---
## Program (Descending order)




ORG 0000H
MOV R1,30H     ; Outer loop count = N
DEC R1

LOOP1: MOV R0,#40H
       MOV R6,30H
       DEC R6

LOOP:  MOV A,@R0
       INC R0
       MOV B,@R0
       CJNE A,B,NEXT
NEXT:  JNC DOWN

       MOV @R0,A
       DEC R0
       MOV @R0,B
       INC R0

DOWN:  DJNZ R6,LOOP
       DJNZ R1,LOOP1   ; Outer loop ends correctly

END


```asm




```
## OUTPUT(Descending order)

<img width="971" height="556" alt="WhatsApp Image 2026-05-21 at 10 41 31 AM" src="https://github.com/user-attachments/assets/fb9a1cd4-39a8-4ec5-944b-3b20890f3e23" />


---
## RESULT:
Thus the sorting of given data was done using 8051 keil software.

