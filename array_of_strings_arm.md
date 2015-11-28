## Source Code
```
#import <Foundation/Foundation.h>

void myFunction() {
    
    char *first_name = "chuck";
    char *second_name = "sly";
    char *third_name = "burt";
    char *fourth_name = "dolf";
    
    char *myArray[5];
    
    myArray[0] = first_name;
    myArray[1] = second_name;
    myArray[2] = third_name;
    myArray[3] = fourth_name;
    
    for(int i = 0; myArray[i] != '\0'; i++) {
        printf("[*] %s\n", myArray[i]);
    }

}

int main(int argc, const char * argv[]) {
    
    printf("[*] Calling myfunction()\n");
    myFunction();
    return 0;
}
```
## Compiler
```
clang -framework Foundation -arch armv7 -isysroot /Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS.sdk/ main.m -o main -miphoneos-version-min=7.0
```

## Walkthrough
```
             _myFunction:
0000bea8         push       {r7, lr}                                            ; XREF=0x40ac, _main+32
0000beaa         mov        r7, sp
0000beac         sub        sp, #0x30
0000beae         movs       r0, #0x0
0000beb0         movw       r1, #0x113                                          ; "dolf", :lower16:(0xbfcf - 0xbebc)
0000beb4         movt       r1, #0x0                                            ; "dolf", :upper16:(0xbfcf - 0xbebc)
0000beb8         add        r1, pc                                              ; "dolf"
0000beba         movw       r2, #0x104                                          ; "burt", :lower16:(0xbfca - 0xbec6)
0000bebe         movt       r2, #0x0                                            ; "burt", :upper16:(0xbfca - 0xbec6)
0000bec2         add        r2, pc                                              ; "burt"
0000bec4         movw       r3, #0xf6                                           ; "sly", :lower16:(0xbfc6 - 0xbed0)
0000bec8         movt       r3, #0x0                                            ; "sly", :upper16:(0xbfc6 - 0xbed0)
0000becc         add        r3, pc                                              ; "sly"
0000bece         movw       sb, #0xe6                                           ; "chuck", :lower16:(0xbfc0 - 0xbeda)
0000bed2         movt       sb, #0x0                                            ; "chuck", :upper16:(0xbfc0 - 0xbeda)
0000bed6         add        sb, pc                                              ; "chuck"
0000bed8         movw       ip, #0x12c                                          ; :lower16:(imp___nl_symbol_ptr____stack_chk_guard - 0xbee4)
0000bedc         movt       ip, #0x0                                            ; :upper16:(imp___nl_symbol_ptr____stack_chk_guard - 0xbee4)
0000bee0         add        ip, pc                                              ; imp___nl_symbol_ptr____stack_chk_guard
0000bee2         ldr.w      ip, [ip]                                            ; 
0000bee6         ldr.w      ip, [ip]                                            ; ___stack_chk_guard
0000beea         str.w      ip, [sp, #0x30 + var_4]
0000beee         str.w      sb, [sp, #0x30 + var_1C]
0000bef2         str        r3, [sp, #0x30 + var_20]
0000bef4         str        r2, [sp, #0x30 + var_24]
0000bef6         str        r1, [sp, #0x30 + var_28]
0000bef8         ldr        r1, [sp, #0x30 + var_1C]
0000befa         str        r1, [sp, #0x30 + var_18]
0000befc         ldr        r1, [sp, #0x30 + var_20]
0000befe         str        r1, [sp, #0x30 + var_14]
0000bf00         ldr        r1, [sp, #0x30 + var_24]
0000bf02         str        r1, [sp, #0x30 + var_10]
0000bf04         ldr        r1, [sp, #0x30 + var_28]
0000bf06         str        r1, [sp, #0x30 + var_C]
0000bf08         str        r0, [sp, #0x30 + var_2C]
```