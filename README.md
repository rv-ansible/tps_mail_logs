
# TPS Mail Logs

This will create {{pre_check_logs}} file on each server, you should build all your logs on it and it will compile and send to your email if configured.

### requirements.yml
\- name: tps_mail_logs <br>
  &nbsp;&nbsp;src: https://github.domaingc.net/scm/tpsdev/tps_mail_logs.git <br>
  &nbsp;&nbsp;scm: git <br>
  
### Call from remote yml with tag:  

#### Create log, generate logs and send to mail:
\- name: call tps_mail_logs role (create_log) <br>
   &nbsp;&nbsp;hosts: all <br>
   &nbsp;&nbsp;become: true <br>
   &nbsp;&nbsp;roles: <br>
   &nbsp;&nbsp;&nbsp;&nbsp;\- { role: tps_mail_logs, create_log: true }  <br>
   
   &nbsp;&nbsp;&nbsp;&nbsp;\- { role: (call other roles) }  <br>
   &nbsp;&nbsp;&nbsp;&nbsp;\- { role: (call other roles) }  <br>
   
   &nbsp;&nbsp;&nbsp;&nbsp;\- { role: tps_mail_logs, mail: true }  <br>
   &nbsp;&nbsp;tags: create_log <br>
