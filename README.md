# 32 bit segmentation

Segmentation provides a mechanism for dividing the processor's addressable memory into smaller prodected spaces(**segments**).

To find the segments in memory the processor needs to know the base address of the segments. The base addresses of the segments are stored in their respective **segment descriptors**.  
Segment descriptor has a base adress, limit and access rights which together with the **offset** is used to get the **linear adress**.  
To find the segment descriptor implicit **segment selectors** are be used (CS - Code segment selector, DS - Data segment selector, ES, SS, FS, GS).  
The selector is used as an index to the **Global Descriptor Table (GDT)** or **Local Descriptor Table(LDT)** and the address of GDT is stored in a special CPU register called GDTR (Global Descriptor Table Register).  
  
A segment selector has the following format:
* Index to GDT/LDT (13 bits)
* TI: Table Indicator (LDT/GDT) (1 bit)
* RPL: Requester Privilege Level (2 bits)

The x86-64 architecture has largely dropped support for segmentation in 64-bit mode.


Mostly copied from **https://cyrussh.com/?p=161**
