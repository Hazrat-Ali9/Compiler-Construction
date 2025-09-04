# 🍑 Hazrat Ali

# 🌽 Programmer || Software Engineering

# 🫣 Compiler Lab 

# Class 8 : Lab 8

# constant asm

.model small
.stack 100h
.code

a equ '2'

main proc
    mov ah,1
    int 21h
    mov bl,al
    mov a,bl
             
             
    mov ah,2
    mov dl,10
    int 21h
    
    mov ah,2
    mov dl,13
    int 21h
      
    mov dl,a
    int 21h
   
    exit:
    mov ah,4ch
    int 21h
    main endp
end main

# Hexa to Decimal.asm 

.model small
.stack 100h
.data
msg db 'Invaid Input $' 
.code
main proc
    
    mov ax,@data
    mov ds,ax
    
    mov ah,1
    int 21h
    mov bl,al
    
    
    mov ah,2
    mov dl,10
    int 21h
    mov dl,13
    int 21h
    
    cmp bl,'0'
    jge l1
   
    jmp l5
    
    
    l1:
    
    cmp bl,'9'
    jle l2
    
    
    cmp bl,'A'
    jge l3
    
    jmp l5
    
    l2:
    
    mov ah,2
    mov dl,bl
    int 21h
    jmp exit
    
    l3:
    
    cmp bl,'F'
    jle l4
    jmp l5
    
    l4:
    
    sub bl,17
    
    mov ah,2
    mov dl,49
    int 21h
    
    mov ah,2
    mov dl,bl
    int 21h
    
    jmp exit
    
    l5:
    
    mov ah,9
    lea dx,msg
    int 21h
    
    jmp exit
    
    exit:
    mov ah,4ch
    int 21h
    main endp
end main


# Class : 9 Lab : 9

# Reverse

.model small
.stack 100h
.code

main proc
    mov ah,1
    
    int 21h
    mov bl,al
    
    int 21h
    mov bh,al
    
    mov ah,2
    mov dl,10
    int 21h
    
    mov dl,13
    int 21h
    
    xchg bl,bh
    
    mov ah,2
    mov dl,bl
    int 21h
    
    mov dl,bh
    int 21h
    
    exit:
    mov ah,4ch
    int 21h
    main endp
end main


# Sqaure
;*****
;*****
;*****
;*****
;*****
;*****

.model small
.stack 100h
.data

var db 10,13,'***** $'
.code

main proc
    
    mov ax,@data
    mov ds,ax
    
    mov ah,9
    lea dx,var
    
    int 21h
    int 21h
    int 21h
    int 21h
    int 21h
    
    
    exit:
    
    mov ah,4ch
    int 21h
    main endp

end main

# Pyramid 

;*****
;****
;***
;**
;*


.model small
.stack 100h
.code

main proc
    
    mov cx,5
    
    level1:
    mov bx,cx
    
    level2:
    mov ah,2
    mov dl,'*'
    int 21h
    loop level2
    
    mov ah,2
    mov dl,10
    int 21h
    mov dl,13
    int 21h
    
    mov cx,bx
    loop level1
    
    exit:
    mov ah,4ch
    int 21h
    main endp 

end main 

# Try Pattern Input 

;*****
;*****
;*****
;*****
;*****
;*****

.model small
.stack 100h
.data

var db 10,13,'***** $'
.code

main proc
    
    mov ah,1
    int 21h
    mov bx,ax
    
    sub bx,48
    
    mov cx,bx
    
    level2:
    mov cx,
    
    mov ah,2
    mov dl,'*'
    int 21h
    
    
    
    
    exit:
    
    mov ah,4ch
    int 21h
    main endp

end main
    

Class : 10 Lab : 10 


# CheckPassword 


# AND,OR,XOR.asm

.model small
.stack 100h
.data
a db 10,13, 'for and $'
b db 10,13,  'for or $'
¢ db 10,13,  'for xor $'
.code
main proc
mov ax,@data
mov ds, ax

mov ah,9
lea dx,a
int 21h

mov bl,111b  ;op1
and bl,101b  ;op2
add b1,48

mov ah,2
mov dl, bl
int 21h

or1:
mov ah,9
lea ax,b
int 21h

mov b1,101b 
or bl,101b 
add b1,48 

mov ah,2 
mov dl,bl 
int 21h 


xor1:
mov ah,9
lea ax,c
int 21h

mov bl,111b 
xor bl,100b
add bl,48 

mov ah,2 
mov dl,bl 
int 21h 

exit:
mov ah,4ch
int 21h
main endp
end main


# ASCII_character.asm

.model small 
.stack 100h
.code 
main proc 
mov cx,0 

lev1:
mov bx,cx
mov cx,10

lev2:
mov ah,2 
mov dl,bl 
int 21h 

inc bl 
cmp bl,255

je exit 
loop lev2

mov ah,2 
mov dl,10 
int 21h
mov dl,13 
int 21h

inc bl
mov cx, bx
loop lev1

exit:
mov ah,4ch
int 21h
main endp
end main


Class 11 Lab 11 

# 1
# AndOrXor.asm

.model small
.stack 100h
.data
a db 10,13, 'for and $'
b db 10,13,  'for or $'
c db 10,13,  'for xor $'
.code

main proc
mov ax,@data
mov ds, ax

mov ah,9
lea dx,a
int 21h

mov bl,111b  ;op1
and bl,101b  ;op2
add bl,48

mov ah,2
mov dl, bl
int 21h

or1:
mov ah,9
lea ax,b
int 21h

mov bl,101b 
or  bl,101b 
add bl,48 

mov ah,2 
mov dl,bl 
int 21h 


xor1:
mov ah,9
lea ax,c
int 21h

mov bl,111b 
xor bl,100b
add bl,48 

mov ah,2 
mov dl,bl 
int 21h 

exit:
mov ah,4ch
int 21h
main endp
end main

# 2
# Procedure.asm

.model
.stack 100h
.data
a db ‘Enter two numbers $'
b db 10,13, 'Result  : $'
.code
main proc
mov ax,@data
mov ds, ax

proc1 proc
mov ah,9
lea dx,a
int 21h

mov ah,1
int 21h
mov bl,al
int 21h
mov bh,al

call proc2
ret

proc2 proc
mov ah,9
lea dx,b
int 21h

add bl,bh
sub bl,48
mov ah,2
mov dl,bl
int 21h

cmp bl,13
Jmp exit
ret 

exit:
mov ah,4ch
int 21h
main endp
end main


# Class 12 Lab 12 


# 1. Division.asm

.model small
.stack 100h

.data

a dw ?       

b dw ?     

c db 'Input first digit ',10,13,'$'   

d db 10,13,'Input second digit ',10,13,'$'

e db 10,13,'Result ',10,13,'$'

.code

main proc
    
    mov ax,@data
    mov ds,ax
    
    mov ah,9
    lea dx,c
    int 21h       
    
    mov ah,1
    int 21h 
    sub al,48
    mov ah,0
    mov [a],ax
    
    mov ah,9
    lea dx,d
    int 21h
    
    mov ah,1
    int 21h
    sub al,48 
    mov ah,0
    mov [b],ax
    
  
    
    mov ah,9
    lea dx,e
    int 21h  
    
    mov ax,a
    mov dx,0
    div b  
    
    add ax,48
     
    
   
    mov dx,ax 
    mov ah,2 
    int 21h 
    
    
    
    exit:
    mov ah,4ch
    int 21h
    
    main endp

end main


# 2. Multiplication.asm

.model small
.stack 100h

.data

a dw ?       

b dw ?     

c db 'Input first digit ',10,13,'$'   

d db 10,13,'Input second digit ',10,13,'$'

e db 10,13,'Result ',10,13,'$'

.code

main proc
    
    mov ax,@data
    mov ds,ax
    
    mov ah,9
    lea dx,c
    int 21h       
    
    mov ah,1
    int 21h 
    sub al,48
    mov ah,0
    mov [a],ax
    
    mov ah,9
    lea dx,d
    int 21h
    
    mov ah,1
    int 21h
    sub al,48 
    mov ah,0
    mov [b],ax
    
  
    
    mov ah,9
    lea dx,e
    int 21h  
    
    mov ax,a
    mul b  
    
    add ax,48
     
    
   
    mov dx,ax 
    mov ah,2 
    int 21h 
    
    
    
    exit:
    mov ah,4ch
    int 21h
    
    main endp

end main



# 3. PasswordCheck.asm

.model small
.stack 100h
.data

a db 'Enter Your Password: $'
correct db 10,13,'Correct Passaword$'
wrong db 10,13,'Wrong Password$'
pass db 'assembly$'
pass1 dw 8
.code

main proc
    mov ax,@data
    mov ds,ax
    
    mov cx, pass1
    mov bx, offset pass
    
    mov ah,9
    lea dx,a
    int 21h
    
    l1:
    mov ah,8
    int 21h
    
    cmp al,[bx]
    jne l2
    inc bx
    loop l1
    
    mov ah,9
    lea dx, correct
    int 21h
    jmp exit
    
    l2:
    mov ah,9
    lea dx, wrong
    int 21h
    
    exit:
    mov ah,4ch
    int 21h
    main endp
end main





