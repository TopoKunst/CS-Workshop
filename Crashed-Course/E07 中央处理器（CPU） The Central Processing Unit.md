# 计算机科学速成课 Crash Course Computer Science

### 第七集 中央处理器（CPU） The Central Processing Unit

计算机的心脏是“中央处理器”（Central Processing Unit），简称“CPU”。

#### 指令

CPU负责执行程序，程序由一个个操作组成，这些操作叫做“指令”（Instruction），因为它们“指示”（instruct）计算机要做什么事。如果是数学指令例如加减，CPU会让ALU进行数学运算，也可能是内存指令，CPU会和内存通信然后进行读写数据。

在“微体系架构”的高层次视角进行CPU构建，首先需要一些内存：RAM，假设它只有16个位置并且每个位置存8位；然后还需要四个8位寄存器，分别为A，B，C，D；寄存器用来临时存数据和操作数据。

数据是以二进制值存在内存里的，同样程序也可以存在内存中。可以给CPU支持的所有指令分配一个ID，在这个例子中（详见下图），用前四位存“操作代码”（operation code），简称“操作码”（opcode），后四位代表数据来自哪里，可以是寄存器或内存地址。

<img src=".\image\image-20200212151144083.png" alt="image-20200212151144083" style="zoom:70%" />

#### 指令地址寄存器 & 指令寄存器

还需要两个寄存器：一个寄存器追踪程序运行到哪里了，称为“指令地址寄存器”（instruction address register），它存储当前指令的内存地址；另一个寄存器存当前指令，叫“指令寄存器”（instruction register）。

当启动计算机时，所有寄存器从0开始，为了举例在RAM中放了一个程序。

<img src=".\image\image-20200212153314570.png" alt="image-20200212153314570" style="zoom:100%" />

<img src=".\image\image-20200212185300128.png" alt="image-20200212185300128" style="zoom:100%" />

#### 取指令阶段

CPU的第一个阶段叫“取指令阶段”（fetch phase），负责拿到指令。首先，将“指令地址寄存器”连接到RAM，寄存器的值为0，所有RAM返回地址0的值，00101110会复制到“指令寄存器”里，取指令完成。

#### 解码阶段

接下来是“解码阶段”（decode phase），弄清楚是什么指令。在“指令寄存器”中的00101110的前4位0010是 LOAD A 指令，意思是把RAM的值放入寄存器A中，后4位1110是RAM的地址，转成十进制是14。接下来，指令由“控制单元”进行解码，“控制单元”也是逻辑门组成的，例如为了识别“LOAD A”指令，需要一个电路检查操作码是不是0010。

#### 执行阶段

知道是什么指令后可以开始执行，进入“执行阶段”（execute phase），用“检查是否 LOAD A 指令“的电路可以打开RAM的”允许读取线“，把地址14传过去，RAM拿到的值为00000011，十进制是3，因为是 LOAD A 指令，只需要把这个值放到寄存器A，其他寄存器不受影响，所以需要一根线把RAM连接到4个寄存器，用”检查是否 LOAD A 指令“的电路启用寄存器A的”允许写入线“，这就成功把RAM的地址14的值放到寄存器A。指令完成后可以关闭所有线路，去拿下一条指令，我们把”指令地址寄存器“+1，”执行阶段“结束。

<img src=".\image\image-20200212190926713.png" alt="image-20200212190926713" style="zoom:70%" />

可以把上述提到的”控制单元“视为一个整体，它”指挥“CPU的所有组件。”取指令----解码----执行“完成后，再来一次从”取指令“开始，”指令地址寄存器“现在的值是1，所以RAM返回地址1里的值：00011111，解码阶段分析前4位0001是 LOAD B 指令，从RAM里把一个值复制到寄存器B，后4位代表内存地址1111，十进制的15，到执行阶段，”控制单元“叫RAM读地址15，并配置寄存器B接收数据，成功把值00001110（十进制的14）存到了寄存器B，最后一件事是将”指令地址寄存器“+1。

下一条指令是10000100，1000是ADD指令，这次的后4位不是RAM的地址，而是2位2位分别代表2个寄存器，2位可以表示4个值，所以足够表示4个寄存器，第一个地址是01，代表寄存器B，第二个地址是00，代表寄存器A，所以10000100代表把寄存器B的值加到寄存器A里。为了执行这个指令，需要结合ALU，“控制单元”负责选择正确的寄存器作为输入，并且配置ALU执行正确的操作，对于“ADD”指令，“控制单元”会启用寄存器B，作为ALU的第一个输入，还要启用寄存器A，作为ALU的第二个输入，ALU可以执行不同操作，所以控制单元必须传递ADD操作码告诉ALU需要做什么操作，最后得到的结果应该存到寄存器A，但是不能直接写入寄存器A，若这样新值会进入ALU，不断和自己相加，因此，控制单元用一个自己的寄存器暂时保存结果，然后关闭ALU，然后把值写入正确的寄存器。例子中是 3+14=17，二进制为00010001。存进寄存器A之后的最后一件事就是把指令地址+1。

<img src=".\image\image-20200213175928614.png" alt="image-20200213175928614" style="zoom:70%" />

最后一条指令是01001101，解码得知是 STORE A 指令，即把寄存器A的值放入内存，RAM地址是13，接下来把地址传给RAM，启用允许写入线，同时打开寄存器A的“允许读取”，这样可以把寄存器A里的值传给RAM。这样就运行了一个完整的电脑程序，它从内存中加载两个值，相加，然后把结果放回内存中。

时钟以精确的间隔触发电信号，控制单元会用这个电信号推进CPU的内部操作，以确保一切按步骤进行。CPU“取指令--解码--执行”的速度叫“时钟速度”（clock speed），单位是赫兹（hertz），赫兹是用来表示频率的单位，1赫兹代表一秒1个周期。

第一个单芯片CPU是“英特尔4004”，1971年发布的4位CPU，它的时钟速度达到了740千赫兹——每秒74万次，1兆赫兹是1秒1百万个时钟周期，现在使用的电脑和手机可以达到几千兆赫兹——1秒10亿次时钟周期。为了尽可能省电，很多现代处理器可以按需求加快或减慢时钟速度，这叫“动态调整频率”（dynamic frequency scaling）。

加上时钟后，CPU才是完整的，可以将CPU抽象化为一个独立组件，RAM是在CPU外面的独立组件，CPU和RAM之间用“地址线” “数据线”和“允许读/写线”进行通信。

<img src=".\image\image-20200213182055244.png" alt="image-20200213182055244" style="zoom:70%" />
