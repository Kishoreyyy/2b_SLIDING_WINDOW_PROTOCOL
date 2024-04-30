# NAME : S.KAVIYA
# DEPARTMENT : CSE
# REGISTER NO : 212223040090
# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

CLIENT:

    import socket

    s=socket.socket()

    s.bind(('localhost', 8000))

    s.listen(5)

    c,addr=s.accept()

    size=int(input("Enter number of frames to send : "))

    l=list(range(size))

    s=int(input("Enter Window Size : "))

    st=0

    i=0

    while True:

        while(i<len(l)):
   
             st+=s
       
             c.send(str(l[i:st]).encode())
       
             ack=c.recv(1024).decode()
       
             if ack:
       
                print(ack)
          
                i+=s
          
SERVER:

       import socket

       s = socket.socket()

       s.connect(('localhost', 8000))

       while True:

           print(s.recv(1024).decode())
     
           s.send("Acknowledgement received from the client".encode())

## OUPUT

CLIENT: 

![Screenshot 2024-03-04 140722](https://github.com/KAVIYASHANMUGAM19/2b_SLIDING_WINDOW_PROTOCOL/assets/155141139/fd55e112-cd82-4c89-840b-2dee8af21640)

SERVER :

![Screenshot 2024-03-04 140747](https://github.com/KAVIYASHANMUGAM19/2b_SLIDING_WINDOW_PROTOCOL/assets/155141139/64a50b48-d652-437d-8303-5e7b7d614813)



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
