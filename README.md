## Fix bug: 
*** when use groovy 2.4.15, android minSdkVersion must set 26+

error:
```
com.android.tools.r8.ApiLevelException: MethodHandle.invoke and MethodHandle.invokeExact are only supported starting with Android O (--min-api 26)
``` 


#### Step
* Download JarJar jar
* In the same folder download the grooid jar you want to use. This was tested with 2.4.12 jar
* Again, in the same folder create a file called rules.txt
* In rules.txt put "zap org.codehaus.groovy.vmplugin.v7.IndyInterface"
* Run java -jar jarjar-1.3.jar process rules.txt groovy-2.4.12-grooid.jar groovy-android.jar
* Now add newly created jar file to your android project.  


reference: 
https://gist.github.com/AndrewReitz/3e1145d66a8ef3f7b578d8604ecd671c