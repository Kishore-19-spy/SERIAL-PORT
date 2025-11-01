
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```asm
ORG 00H 
MOV TMOD, #20H 
MOV TH1, #0FCH 
MOV SCON, #40H 
SETB TR1 
MOV SBUF, #'K' 
WAIT:JNB TI, WAIT
CLR TI 
END



```
### (ii) Serial Port to Transfer a Message

```c
#include<reg51.h>
void main(void)
{
unsigned char msg[]="KISHORE A";
unsigned char i;
TMOD=0X20;
TH1=0XFC;
SCON=0X40;
TR1=1;
for (i=0; i<23;i++)
{
SBUF= msg[i];
while(TI==0);
TI=0;
}
while(1);
}






```

### OUTPUT:
<img width="1389" height="741" alt="image" src="https://github.com/user-attachments/assets/9fbc1818-4e2a-4ffe-8d9c-b65dec9414ff" />
<img width="1545" height="859" alt="image" src="https://github.com/user-attachments/assets/b5acc7c0-072d-4aee-8238-4b2f53b2bafc" />


### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
