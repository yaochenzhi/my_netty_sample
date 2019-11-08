javac -encoding utf8 -cp lib\netty-all-5.0.0.Alpha2.jar _02discard\*.java
java -cp lib\netty-all-5.0.0.Alpha2.jar;. _02discard.DiscardServer

jar -cvf server.jar _02discard\*.class -cp lib\netty-all-5.0.0.Alpha2.jar 

# with MANIFEST file
jar -cvmf MANIFEST.MF  server.jar  _02discard\*.class
jar -cvfm server.jar  MANIFEST.MF  _02discard\*.class

# without MANIFEST file
jar -cvf server.jar _02discard\*.class

# update MANIFEST file
jar umf main server.jar

# update MANIFEST file
jar uef main server.jar

# run jar 
java -jar server.jar