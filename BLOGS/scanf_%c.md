### scanf("%c",&c) 与 scanf(" %c",&c)的区别

scanf("%c",&c) 与 scanf(" %c",&c)，后者只是在%前多了个空格，似乎没有什么区别，但使用起来区别是很大的。

scanf()作单字符输入时规定只接收一个字符，但它却把回车符也作为字符对待的。这个回车符是放在缓冲区的，但是空格却是直接忽略掉。

这就造成程序中第二次调用scanf("%c",&c)是从缓冲区中取一个字符，把第一次调用scanf("%c",&c)后输入的回车当作输入字符了。

这就在输入逻辑上造成了混乱。

有了scanf(" %c",&c)这个空格（换成\n或者\t也可以），这样就把缓冲区中的回车当成第一个字符，读取后丢掉。

