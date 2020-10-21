# while循环
```
#定义结束标志符
delimiter ;;
 #创建存储过程
CREATE PROCEDURE test_insert3 () 
    #开始
    BEGIN
        #定义变量 
        DECLARE i INT DEFAULT 1;
            #条件判断
            WHILE i<200000
            #执行
            DO 
                #SQL
                INSERT INTO table_name values();
                #变量增加
                SET i=i+1;
            #结束循环 
            END WHILE ;
        #提交 
        commit; 
    #结束
    END;;

#执行
CALL test_insert3(); 
```
