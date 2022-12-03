# learning cJSON

## 简介
1. 纯c的json工具，包括创建，解析并打印
2. test可执行程序包含调试信息
3. test1可执行程序不包含调试信息

## 学到的东西
1. 纯c靠指针能完成大部分事情
2. memset(node, 0, sizeof(cJSON)) // 其中node是由malloc申请到的cJSON指针
3. 不可以返回局部变量的引用或指针，但可在函数内申请堆上的内存
4. malloc申请内存有可能失败，所以失败时应该返回；传进来的东西不符合预期要加判断，由此保证程序的健壮性
5. const char* in ; in && *in 指针不为空且指针所指不为空 0 '\0'
6. strncmp(value, 'null', 4) // 比较前几个字符，相同为0
7. parse_string中计算应该分配的指针大小，后*ptr2++=*ptr++;
8. '9'-'0' 可以得出字符对应int
10. array中装了多个同类型的item，这些item形式上为双向链表
11. object中每一个item都有name，还有value; parse_value可以将value传到item上
12. 解析时指针往后移动，parse_value返回指针的位置
13. strcpy(out, 'null')
14. memcpy(copy, str, len) // 把str中len字节复制到copy所指向的地址里
15. sprintf
16. 打印就是将item的name和value写到输出字符串上，然后打印字符串
19. memset(entries, 0, sizeof(char*)*numentries)给二级指针初始化
20. entries=(char**)cJSON_malloc(numentries*sizeof(char*)); // 分配这么多内存给entries指针，这个指针里存放多个一级指针
17. 打印object或array时，由于形式上有多个child，所以会保存每个child，用二级指针保存
18. 之后再统一整合各个child的输出












## 没看懂的地方
1. pow2gt
1. printbuffer
1. ensure
1. update
1. parse_hex4
1. firstByteMark
1. cJSON_PrintUnformatted
1. cJSON_PrintBuffered
1. cJSON_Minify

## 看懂但却不理解的地方
1. 待补充
2. 待补充
3. 待补充

## 待完成
1. 下次自己写一个