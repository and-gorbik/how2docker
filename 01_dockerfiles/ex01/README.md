How to run:
1. docker build -t ts3server .
2. docker run -it --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ts3server
3. launch up-to-date version of ts client
4. cmd + S to connect to server
5. host: $(docker-machine ip Char):9987
6. enter 40 character token

How to setup ts3: [source](https://www.hostinger.com/tutorials/how-to-make-a-teamspeak-3-server/)
