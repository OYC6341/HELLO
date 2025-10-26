# 以下是MIPS编程中一些常用的宏

```MIPS
.macro end
	li $v0,10
	syscall
.end_macro

.macro getInt(%des)
	li $v0,5
	syscall
	move %des,$v0
.end_macro

.macro printInt(%des)
	move $a0,%des
	li $v0,1
	syscall
.end_macro

.macro index1(%ans,%des)
	sll %ans,%des,2
.end_macro

.macro index2(%ans,%n,%m,%l)
	mul %ans,%n,%l
	add %ans,%ans,%m
	sll %ans,%ans,2
.end_macro

.macro push(%des)
	addi $sp,$sp,-4
	sw %des,0($sp)
.end_macro

.macro pop(%des)
	lw %des,0($sp)
	addi $sp,$sp,4
.end_macro
```

