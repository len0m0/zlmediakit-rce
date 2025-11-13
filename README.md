# zlmediakit-rce
zlmediakit descrip
zlmediakit is a high-performance, enterprise-grade streaming media service framework. This framework contains a remote command execution vulnerability in ZLMediaKit versions 1.0 through 8.0, 


1.Steps to reproduce (复现步骤)

Locate the command execution point
<img width="1145" height="897" alt="image" src="https://github.com/user-attachments/assets/5dbbc71c-372c-4fb8-85e8-6683290f97b8" />


Access requires a secret, so we locate the default secret. A default secret exists here.

<img width="1277" height="807" alt="image" src="https://github.com/user-attachments/assets/33f69ffc-25f0-4d16-9410-d1798dfaba51" />

Retrieve all configuration information via getServerConfig

<img width="777" height="321" alt="image" src="https://github.com/user-attachments/assets/59a064c3-aaee-4eed-8599-ae45da895598" />



Modify the command when calling ffmpeg to the host command you wish to execute.

<img width="551" height="499" alt="image" src="https://github.com/user-attachments/assets/cdad9c0e-3324-4e24-88e0-c2c1b09bb162" />

Of course, we can also modify ffmpegsnap to execute system commands.

Execute system commands to access DNS logs.

<img width="697" height="423" alt="image" src="https://github.com/user-attachments/assets/1ebbb69f-5e0a-44c4-b2db-438be72dbe25" />


2.some code(相关代码)

<img width="1339" height="885" alt="image" src="https://github.com/user-attachments/assets/0598c56f-0b11-4e3f-b970-990680deac52" />


3.Affected Version (受影响的版本)

ZLMediaKit versions 1.0 through 8.0, 

4.fixes Recommendations (修复建议)

Modify the default secret.
Add a whitelist when executing the ffmpeg command
