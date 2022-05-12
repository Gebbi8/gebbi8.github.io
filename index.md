# Keeping track of tasks and how to do them
I usually use different tools and processes to get my scientific and teaching work done. Ranging from JAVA development for the backand and diverse frontend framework libraries. I'll try to keep track of things that I tend to forget in this blog.


### Publishing Java modules in Maven Central
Starting Point:
* changed existing modules of a Java tool
* some time ago I added another module and managed to publish everything on maven central (with support). Sadly, forgot how to do it.

Steps:
1. update pom.xml of all modules from bottom to top
2. git commit + push --- as always when changing something
3. sign artefacts
  * is it a one time requirement or do I have to sign before every update?
5. check JAVA path --- for some reason linux kepts forgetting about it
  * `echo $JAVA_HOME`
  * `source /etc/profile` --- if java is already set otherwise see: https://stackoverflow.com/questions/24641536/how-to-set-java-home-in-linux-for-all-users
6. check if the gpg signing works:
  * `echo "test" | gpg --clearsign`
  * if fails -> `export GPG_TTY=$(tty)`
7. 'mvn clean install` --- test if every test works
8. `mvn clean deploy` --- deploys to maven central
9. `mvn clean deploy -Ddocker.user=USERNAME -Ddocker.password='PASSWORD'`  --- deploys to dockerhub
10. check nexus repistory manager
11. wait for visability on maven central 
12. ask system admin to update server
###

* remark: Since I need the gpg key I'll do it remotly from my former machine

### Setting CSP
Content Security Policy secures the page from unwanted interaction with remote scripts and ressources
Use-Case: Fetching files from BioModels database.
*
