# rmmod
rmmod bad module force

# Usage
1. make
2. insmod kill.ko modname=$(DEL_MOD_NAME)
3. rmmod $(DEL_MOD_NAME)
4. rmmod kill.ko

# Ref
https://blog.csdn.net/gatieme/article/details/75108154?biz_id=102&utm_term=linux%E5%BC%BA%E5%88%B6%E5%8D%B8%E8%BD%BD%E5%86%85%E6%A0%B8%E6%A8%A1%E5%9D%97&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduweb~default-1-75108154&spm=1018.2118.3001.4187

# Tips
- Replace DEL_MOD's exit function by change kill.c
```angular2html
line 28: 
	#define CONFIG_REPLACE_EXIT_FUNCTION 1(original is 0)
line 33~38:
	/* static */ void force_replace_exit_module_function(void)						
	...
```
