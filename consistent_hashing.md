Consistent Hashing Technique:

Need: Data is distributed, scaled across different VM's (horizontal scaling). Its very important to hash the data objects into different servers
as evenly as possible.

Hashing function: Object -> Hashing function -> Range of values 

Deterministic hashing (Simple Hash)
1) Determining which server the object belongs to -> Hash(object) % No of server pool => which server object can get mapped to.
2) Cons: Not adaptable to server pool dynamically added or removed. There is a lot of chaos under all objects getting mapped 
   when a server goes offline or new server is added. 
   
Idea behind consistent hashing: The number of objects assigned to server remains consistent though the dynamic allocation of servers 
happen. 

Objects + Servers => Hashing function => range of values (X0 to Xn) - This is connected to form a hash ring. 

Servers + Objects are hashed and placed into the hash ring clockwise. When a server is added, the key object is just 
referenced to the new server in a clockwise turn and rest other objects are unaffected. Consistent hashing only requires 
distributing fraction of keys. 

To locate a server, we need to go clockwise to see what's the closest server an object can be mapped to. 

![Screenshot 2023-05-17 at 2 30 03 PM](https://github.com/SangeethaVenkatesan/SystemDesignGist/assets/68361331/f0da66f2-bfd9-4e11-9f16-8c9b6e17f917)

Potential issues with consistent hashing design:
1) To determine the ideal partition is very ambigous. It might not be evenly distributed in the ring.
![Screenshot 2023-05-17 at 2 37 35 PM](https://github.com/SangeethaVenkatesan/SystemDesignGist/assets/68361331/62debd0c-0d03-4b0c-8a20-19808808bd09)
2) To make the gap between the servers in the right come closer, virtual nodes are used to represent the server to have the objects 
   evenly distributed. 
![Screenshot 2023-05-17 at 2 39 17 PM](https://github.com/SangeethaVenkatesan/SystemDesignGist/assets/68361331/30823e9b-5fa7-4052-9931-8d0e15ef6b9f)
3) As the number of objects and servers increases, the distribution might get balanced. Keep in mind that virtual nodes require storing of
   their metadata too. 
   
 CONSISTENT HASHING IN REAL WORLD: Ultimate goal is to retreive and locate information efficiently. 
 1) Mainly to address scalability and load balancing challenges. Hence distributed cache systems, load balancing, content delivery 
    systems have a major area of application. 
    
  Interesting one: https://www.uni-weimar.de/fileadmin/user/fak/medien/professuren/Webis/teaching/ss14/big-data-seminar/sabri14-voldemort-talk.pdf 
  Linkedin application - Voldemort 
