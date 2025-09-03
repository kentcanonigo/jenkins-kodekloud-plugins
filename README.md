## For KodeKloud Jenkins Level 4

### Run this on the jumphost:

```bash
ssh admin@jenkins "
rm -rf /tmp/jenkins-plugins && \
git clone https://github.com/kentcanonigo/jenkins-kodekloud-plugins.git /tmp/jenkins-plugins && \
sudo tar -xzvf /tmp/jenkins-plugins/jenkins-plugins-backup.tar.gz -C /var/lib/jenkins/plugins/ && \
sudo chown jenkins:jenkins /var/lib/jenkins/plugins/* && \
sudo chmod 644 /var/lib/jenkins/plugins/* && \
curl -s -o /tmp/jenkins-cli.jar http://localhost:8080/jnlpJars/jenkins-cli.jar && \
java -jar /tmp/jenkins-cli.jar -s http://localhost:8080/ -auth admin:'Adm!n321' safe-restart
"
```

This should install the needed plugins for you to complete the tasks
