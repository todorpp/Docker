This lab goal is to show the use of named volumes which is to store files somewhere localy, so once when container is stoped the data is not lost. 

The code is simple web app which allow us to write some text and save it . We can see the file http:localhost:port_number/feedback/example.txt

In order for this file to be saved we must run the container with special flag and the command can lok like this:

docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback feedback-node:volume

To verify we can stop the container and run it again, we will be able succesfuly to revisit http:localhost:port_number/feedback/example.txt

--------------------------------------------------------------------------------------------------------------------------------------------------

Other option is the use of Bind mount and anonymous volumes which will allow us to manipulate the code which will reflect on the running application
in real time. For this use case named volume , bind mount with read only ability  and anonymous volume must be created with the following commands 

docker run -d -p 3000:80  --name feedback-app -v feedback:/app/feedback -v "C:\Users\tppar\Desktop\Docker\4th:/app:ro" -v /app/node_modules feedback-node:volume
