LEX=flex
YACC=bison
CC=g++
OBJECT=main # 生成的目标文件
 
$(OBJECT): lex.yy.o  yacc.tab.o
	$(CC) lex.yy.o yacc.tab.o -o $(OBJECT)
	@./$(OBJECT) # 编译后立刻运行
 
lex.yy.o: lex.yy.c  yacc.tab.h  main.h
	$(CC) -c lex.yy.c
 
yacc.tab.o: yacc.tab.c  main.h
	$(CC) -c yacc.tab.c
 
yacc.tab.c  yacc.tab.h: yacc.y
# bison 使用 -d 参数编译 .y 文件
	$(YACC) -d yacc.y
 
lex.yy.c: lex.l
	$(LEX) lex.l
 
clean:
	@rm -f $(OBJECT)  *.o lex.yy.c yacc.tab.*

