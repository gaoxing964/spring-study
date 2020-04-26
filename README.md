# spring-study

step 1
export http_proxy="http://CHINA%5C[Q-number]:[TSS-password]@proxy.apac.gdc:8080"
export https_proxy="http://CHINA%5C[Q-number]:[TSS-password]@proxy.apac.gdc:8080"

step 2

Edit /etc/apt/apt.conf.d/60bmw-location, create if it does not exist
Acquire::http::Proxy "http://CHINA%5Chttp://CHINA%5C[Q-number]:[TSS-password]@122.200.123.130:8080";
Acquire::http::Proxy::cc-artifactory.bmwgroup.net "DIRECT";



5.	Install curl: sudo apt-get install curl
6.	Install node/npm
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash –
sudo apt-get install nodejs
7.	Configure npm proxy
npm config set proxy http://CHINA%5C[Q-number]:[TSS-password] @proxy.apac.gdc:8080
npm config set https-proxy http://CHINA%5C[Q-number]:[TSS-password] @proxy.apac.gdc:8080
	Check the content of ~/.npmrc to make sure the proxy setting correct.
8.	Install OAP Generator
sudo npm i -g oap-generator --registry http://160.46.254.251:22122/oapdevnpm  --ignore-scripts --proxy http://[Q-number]:[TSS-password]@160.48.211.81:8080 –ddd
run oap-generator init and you will see the prompt:
	Fields with (*) are required
	---
	Please enter project name (hello-oap):
9.	Install Git
sudo apt install git
Note: If you found error shows: “Could not get lock /var/lib/dpkg/lock”, that means some program is updating Ubuntu or installing some software that locks the dkpg file.
ps aux | grep –i apt   // list process that is running   
                       // apt or apt-get
sudo kill <process-id> // kill the processes…

	Configure git(~/.gitconfig)
[url "ssh://asc.bmwgroup.net/"]
    insteadof = https://asc-repo.bmwgroup.net/gerrit/
    insteadof = https://asc-repoa.bmwgroup.net/gerrit/
[http "https://github.com"]
    proxy = https://proxy.cn.sub:8080/
[http "https://asc-repo.bmw.com"]
    proxy = http://proxy.apac.gdc:8080/
[http "https://asc-repoa.bmwgroup.net"]
    proxy = http://proxycn.bmwgroup.net:8080/
[http "https://cc-github.bmwgroup.net"]
    proxy = http://proxycn.bmwgroup.net:8080/
[http "https://atc.bmwgroup.net"]
    proxy = http://proxycn.bmwgroup.net:8080/
[http "https://git.yoctoproject.org"]
    proxy = http://proxy.cn.sub:8080/
[http "https://gerrit.googlesource.com"]
    proxy = http://proxy.apac.gdc:8080/
[http "https://atc.bmwgroup.net"]
    proxy = http://[Q-number]:[TSS-password]160.48.211.81:8080/
[remote "origin"]
    prune = true
[filter "lfs"]
    process = git-lfs filter-process
    required = true
    clean = git-lfs clean -- %f
    smudge = git-lfs smudge -- %f
[user]
     name = <Your Name>
        email = <Your BMW email address>
[http]
     proxy = http://CHINA%5C[Q-number]:[TSS-password]@proxy.apac.gdc:8080
[https]
     proxy = http://CHINA%5C[Q-number]:[TSS-password]@proxy.apac.gdc:8080

10.	Install JAVA
1)	Download  Java SE Development Kit 8u241: https://www.oracle.com/java/technologies/javase-jdk8-downloads.html
2)	Follow https://www.fosstechnix.com/install-oracle-java-8-on-ubuntu/ to configure JAVA on Ubuntu.
11.	Install SSH server
sudo apt update
sudo apt install openssh-server

