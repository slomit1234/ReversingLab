# ReversingLab
Subbmiter - Shlomit Ashkenazi

1. you can see that my last ID number is 4 
2. so, i took the "reverse.tgz" file, extrated it and nevigated to 4 directory:
3. 
![image](https://user-images.githubusercontent.com/42152443/235359309-32ac7b82-57ba-4304-9364-cf8e32f9da23.png)

than, i tried to see if we could hack the password in easier methods, like we saw in class:

  * strings ./prog (do not work)
  
![image](https://user-images.githubusercontent.com/42152443/235359522-f3b696c3-ff7f-40f3-9f30-37bcb3ad3d55.png)

  * ltrace prog (do not work)
  
![image](https://user-images.githubusercontent.com/42152443/235359566-212b1da5-df37-4f78-a68a-86ba372a272d.png)

so we need to solve it with an assembler:

we used the command " objdump -d prog | less"
there we saw 2 important things:

1. entering the real password to the stack rgb (register).

![image](https://user-images.githubusercontent.com/42152443/235359859-809e45e0-1802-49e6-81ba-99ffdce2df40.png)

2. checking if the password that the user enter is correct by taking the values above and comparing after negitiving it, bit by bit.

![image](https://user-images.githubusercontent.com/42152443/235359957-736c67bd-f799-48d2-a112-e83b3643614b.png)

so we took the password bit by bit negiting it (with not and than added 1), and checked it in front of an ASCII table
![image](https://user-images.githubusercontent.com/42152443/235360112-3b6c281b-66a6-497d-897d-9f22ab117017.png)
![image](https://user-images.githubusercontent.com/42152443/235733749-132b4387-c53d-4195-95f2-2b87cb646858.png)

ba bf bd bb be b1 b1 b5 --> 46 41 43 45 42 4f 4f 4b

![image](https://user-images.githubusercontent.com/42152443/235735446-c4cf5b7d-eb4c-4609-a2a4-b7cdf79895e0.png)

the parsed string was FACEBOOK

![image](https://user-images.githubusercontent.com/42152443/235360254-9bb7ce1c-ec36-4b7a-b7bd-f7ba8390754d.png)

THE END :)
