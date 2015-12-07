README

备注：由于老师给的数据集不是顺序数据集，所以1、2实验中的第一步都没办法用代码完成，所以没有截图，其他均有结果的截图。

第三题回答问题的答案：

（1）不是
（2）有1层
（3）根据sdsf中的结果：

            VI   DSCBS   PER TRK  BLK PER TRK  ALT TRK   TRK(C-H)   (C-H-R)   DSCB(C-H-R)/LOW(C-H) HIGH(C-H)    (C-H-R)  
            89     742       50         45         0        0   0              1  14  50    1   0     1  14     1   0   1
0---------------DATA SET NAME----------------  SER NO  SEQNO  DATE.CRE  DATE.EXP  DATE.REF  EXT DSORG RECFM OPTCD BLKSIZE
 DSNA10.DBAG.ARCLOG1.D15032.T0404458.A0000085  VPMVSC      1  2015.032  2042.169  2015.032    1  PS   FB     02    24576 
0SMS.IND   LRECL  KEYLEN  INITIAL ALLOC  2ND ALLOC    EXTEND       LAST BLK(T-R-L)  DIR.REM  F2 OR F3(C-H-R)  DSCB(C-H-R)
            4096            RECS             180        24576AV        719   2  7038                            1   0  29
 EATTR                                                                                                                   
 NS                                                                                                                      
0            EXTENTS  NO  LOW(C-H)   HIGH(C-H)                                                                           
                        0   424 10      472  9                                                                           
                                 ----ON THE ABOVE DATA SET,THERE ARE              0 EMPTY BLOCK(S).                      
0 
--------------------------------------------------------------------------------------------------------------------------

可得到的信息如下：

------------------------------------------------------------------------------
           field                |                  information
--------------------------------+---------------------------------------------
VI                              | 89，表示该盘卷为索引VTOC
NO AVAIL DSCBS                  | 742，可用的DSCB数量
MAX DSCB PER TRK                | 50，每个磁道最多存放的DSCB数
MAX DIRECT BLK PER TRK          | 45，每个磁道最多存在的PDS的目录块的数量
NO AVAIL ALT TRK                | 0，需要替换的磁道号
NEXT ALT TRK(C-H)               | 0，需要替换的磁道的位置
FORMAT 6(C-H-R)                 | 0，FORMAT-6格式的DSCB的位置
LAST FMT 1 DSCB(C-H-R)          | 1，最后一个FORMAT-1格式的DSCB的位置
VTOC EXTENT LOW(C-H) HIGH (C-H) | 14，VTOC的范围,从哪里开始以及到哪里结束
THIS DSCB(C-H-R)                | 1，FORMAT-4格式的DSCB的位置，一般在VTOC的第一个记录
DATA SET NAME                   | DSNA10.DBAG.ARCLOG1.D15032.T0404458.A0000085，数据集名
SER NO                          | VPMVSC，所在盘卷的序列号
SEQNO                           | 1，相对第一个包含该数据集的盘卷的顺序。一般为一，除非该数据集在多个盘卷出现
DATE.CRE                        | 2015.032，该数据集被创建的日期
DATE.EXP                        | 2042.169，该数据集到期的日期，00.000表示不会过期
DATE.REF                        | 2015.032，该数据集最后次被使用的日期
EXT                             | 1，该数据集已分配的空间次数
DSORG                           | PS，数据的结构
RECFM                           | FB，记录格式
OPTCD                           | 02，可选码，在创建数据集的时候，在DCB中指定
BLKSIZE                         | 24576，块大小，以字节为单位。最多32760个字节或设备允许最大值
SMS.IND                         | 4096，SMS属性
LRECL                           | RECS，逻辑记录长度，以字节为单位，一般最多32760个字节大小
KELEN                           | 180，键值的长度,为1-255位或不存在键值
INITIAL ALLOC                   | 24576AV，描述了初试分配数据集空间时按什么单位进行分配
2ND ALLOC                       | 719，再次追加的数量。如果为0的话,说明该数据集在第一次分配后,不允许追加空间
EXTEND                          | 2，再次分配的单位
LAST BLK(T-R-L)                 | 7038，第一个数字表示磁道，第二个数字为块，最后表示还剩余多少个字节
DIR.REM                         | 1，表示在最后的256字节的块中已被使用掉 的字节
F2 OR F3(C-H-R)                 | 0，由一个FORMAT2格式的DSCB在该处描述述ISMF数据集的索引