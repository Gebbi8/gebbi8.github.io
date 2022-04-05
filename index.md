# Keeping track of tasks and how to do them
I usually use different tools and processes to get my scientific and teaching work done. Ranging from JAVA development for the backand and diverse frontend framework libraries. I'll try to keep track of things that I tend to forget in this blog.


### Publishing Java modules in Maven Central
Starting Point:
* changed existing modules of a Java tool
* some time ago I added another module and managed to publish everything on maven central (with support). Sadly, forgot how to do it.

Steps:
1. update pom.xml of all modules - bottom to top
2. git commit + push - as always when changing something
3. sign artefacts
  * is it a one time requirement or do I have to sign before every update?
5. check JAVA path --- for some reason linux kepts forgetting about it
  * echo $JAVA_HOME
  * source /etc/profile --- if java is already set otherwise see: https://stackoverflow.com/questions/24641536/how-to-set-java-home-in-linux-for-all-users
6. check if the gpg signing works:
  * echo "test" | gpg --clearsign
  * if fails -> export GPG_TTY=$(tty)

* docker login??
* export GPG_TTY=$(tty)
* mvn clean build
* mvn clean install
* mvn clean deploy -P docker
* mvn clean deploy -Ddocker.user=USERNAME -Ddocker.password='PASSWORD'
###

* remark: Since I need the gpg key I'll do it remotly from my former machine



* do "mvn clean deploy" deploys artifact to maven central
* check nexus repository manager to see the effect
