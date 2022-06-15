# 仿真文件test_bench编写

## 0 写在前面
编写 `test_bench` 的目的是为了对使用硬件描述语言设计的电路进行仿真验证，测试设计电路的功能、性能与设计的预期是否相符。通常，编写测试文件的过程如下：   
- 产生模拟激励（波形）； 
- 将产生的激励加入到被测试模块中并观察其响应； 
- 将输出响应与期望值相比较

## 1 Test bench 文件结构
通常，一个完整的测试文件其结构为  
```
module Test_bench();//通常无输入无输出 
信号或变量声明定义 
**逻辑设计中输入对应 reg 型** 
**逻辑设计中输出对应 wire 型** 
使用 initial 或 always 语句产生激励 
例化待测试模块 
监控和比较输出响应 
endmodule
```

## 2 信号设计
- 时钟激励
  <details>
  <summary>详情</summary>
    
  ```
  reg clk_i;
  initial begin
      clk_i=0; 
  end 
  always #(ClockPeriod/2) clk_i=~clk_i;
  ```
  </details>

- 复位信号
  <details>
  <summary>详情</summary>
    
  ```
  reg rst_n_i;
  initial begin
      rst_n_i=1; 
      #100; 
      rst_n_i=0; 
      #100; 
      rst_n_i=1; 
  end
  ```
  </details>

- 双向信号
  <details>
  <summary>详情</summary>
    
  遇到
  </details>

- 特殊信号
  <details>
  <summary>详情</summary>
    
  遇到
  </details>
