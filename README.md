# 2025_01_01_ServerIsTheClientsBroadcaster
When the server is on a secured computer, you can’t host directly. However, you can still connect to other servers. The idea is to broadcast game info to a trusted hub (such as a pub, school, or workshop) online. That hub then relays the information locally to others.

Two situation comme to my mind.

You want to make coding tournament between schools. You can broadcast 50 to 800 connections per N schools. |
But you can send the information to a server of the local organiser in ws or wss, then they broadcast it to the student.

The other situation is about sending information to a Esp32, PiPico when we detect that the ip is active.


Draft idea:
```
Buttler Integer Server
Use -> Server: Hey I am public RSA and I am here ws:98.56.54.223:8256 (by hand from the admin, HTTPS, UDP or else)
Server -> User: Connect to Websocket 98.56.54.223:8256 Can you sign this [GUID TEXT]
User -> Server: Return sign message with RSA or ECC
Server: Verify the user if false stop websocket connection and suspicion point.
Server -> User: Connection established return the auth index of the RSA key
```
