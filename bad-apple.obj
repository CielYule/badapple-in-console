#include <stdio.h>

#include <stdint.h>

#include <io.h>     //for _setmode()

#include <fcntl.h>  //for _O_BINARY



#define PIC_WIDTH   128

#define PIC_HEIGHT  64

#define PIC_SIZE    (PIC_WIDTH * PIC_HEIGHT * 3) //每张图在内存中的大小，3表示每像素3字节



int main() {

    _setmode(_fileno(stdin), _O_BINARY);

    uint8_t buffer[PIC_SIZE]; //每次缓冲一张图片

    fread(buffer, PIC_SIZE, 1, stdin);

    //只要不读取完或出错，就重复读取。

    //注意必须先读取再判断，来确定此次读取是否有效

    while (!feof(stdin) && !ferror(stdin)) {

        //TODO: 处理buffer并输出...

        fread(buffer, PIC_SIZE, 1, stdin); //读下一次的数据

    }

    return 0;

}
