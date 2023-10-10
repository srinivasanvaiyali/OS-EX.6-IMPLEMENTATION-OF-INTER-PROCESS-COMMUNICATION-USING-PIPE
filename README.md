# OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE

### Aim: 

write C programs to illustrate IPC using pipes mechanisms

## Algorithm:  IPC using pipes

1. Create a child process usingfork()

2. Create a simple pipe with C, we make use of the pipe() systemcall.

3. Create two file descriptor fd[0] is set up for reading, fd[1] isset up forwriting

4. Close the read end of parent process using close() and perform writeoperation


5. Close the write end of child process and performreading

6. Display thetext.

##  PROGRAM:
```
#include <stdio.h>
int main()
{

  int fd[2],child; char a[10];
  printf("\nEnter the string : ");
  scanf("%s",a);
  pipe(fd);
  child=fork();
  if(!child)
{
    close(fd[0]);
    write(fd[1],a,5); wait(0);
}

  else

{
   close(fd[1]);
    read(fd[0],a,5); printf("The string received from pipe is : %s",a);
}

return 0;
}



```
##  OUTPUT:

![ex 6 os srinivasan](https://github.com/srinivasanvaiyali/OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE/assets/145117665/09642613-ade8-43ae-ae69-5fe16a19dd8d)




##  Result: 

Thus, IPC using pipes mechanisms is illustrated using c program successfully
