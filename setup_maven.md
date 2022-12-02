Prerequisites:
- AWS Acccount.
- Create Redhat EC2 T2.medium Instance with 4GB of RAM.
- Install java openJDK 1.8+

# install Java JDK 1.8+ as a pre-requisit for maven to run.

- sudo hostname maven
- cd /opt
- sudo yum install wget nano tree unzip git-all -y
- sudo yum install java-11-openjdk-devel java-1.8* -y
- java -version
- git --version
#### Install Maven on your server
Download maven packages https://maven.apache.org/download.cgi onto Jenkins server. In this case I am using /opt/maven as my installation directory
	- Link : https://maven.apache.org/download.cgi
  # Creating maven directory under /opt
  - sudo mkdir maven
  - cd /opt/maven
  # downloading & installing maven version 3.8.6
  - sudo wget https://dlcdn.apache.org/maven/maven-3/3.8.6/binaries/apache-maven-3.8.6-bin.zip
  - sudo unzip /opt/maven/apache-maven-3.8.6-bin.zip
  - sudo rm -rf apache-maven-3.8.6-bin.zip
  - sudo mv apache-maven-3.8.6/ maven
 ```
	
Setup M2_HOME and M2 paths in .bash_profile of user and add these to path variable
```sh
  - vi ~/.bash_profile
  - M2_HOME=/opt/maven/
  - M2=$M2_HOME/bin
  - PATH=$PATH:$M2_HOME:$M2
```
#### Check point 
Refresh the bash profile, logoff & login and check maven version
Check maven version 
```sh
  - source ~/.bashrc
  - 
  - mvn –version
```
