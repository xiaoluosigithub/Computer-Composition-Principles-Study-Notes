CPU一次访存操作可能涉及TLB、页表、Cache、主存和磁盘的访问，CPU访存过程中存在三种缺失情况：
1. TLB缺失：要访问的虚页号不在TLB中
2. Cache缺失：要访问的主存块不在Cache中
3. Page缺失：要访问的页面不在主存中
![[Pasted image 20260515105638.png]]