---
title: Flyweight pattern
---

- What is the flyweight pattern?
id:: c6a4101f-f2f3-4e0a-a3a3-8192de2806d9
	 - It is a structural pattern that focuses on how related objects share data. It helps prevent repetitive code and increases efficiency when it comes to data sharing as well as conserving memory.
id:: 394be1c1-07cd-4f47-ae42-117fb09ecac1

	 - This pattern takes the common data structures/objects that are used by a lot of objects and stores them in an external object (**flyweight**) for sharing. You could say that it is used for caching purposes. So, the same data does not need to have separate copies for each object, instead, it is shared amongst all.
id:: 3e4d60ef-abbc-439e-9a28-d27185ab59f3

	 - A __flyweight__ is an independent object that can be used in multiple contexts simultaneously. It cannot be distinguished from the instances of objects that are not sharable. A flyweight object can consist of two states:
id:: 789deeda-b504-4379-8f4f-fad0671fd01f
		 - **intrinsic:** this state is stored in the flyweight. It contains the information required by the internal methods of objects. It is independent of the context of the flyweight and is sharable with other objects.
id:: 5ac3d80a-3883-49eb-9e08-12ac55145896

		 - **extrinsic:** this state depends on the context of the flyweight and it cannot be shared. Normally, the client objects pass the extrinsic state to the flyweight object when needed.
id:: c5f8cbc0-f931-4eca-a822-49527f63c7d7

	 - In plain words
id:: 6d2b4b5f-02e3-4ccc-a3f6-ec711ecf590f
		 - It is used to minimize memory usage or computational expenses by sharing as much as possible with similar objects.
id:: 92c0bc9f-521e-4a94-b4e4-711e7bc17008

	 - Wikipedia says
id:: 93c92f49-0de1-4f80-9e15-42ed1cd2d28f
		 - In computer programming, flyweight is a software design pattern. A flyweight is an object that minimizes memory use by sharing as much data as possible with other similar objects; it is a way to use objects in large numbers when a simple repeated representation would use an unacceptable amount of memory.
id:: cf614bd6-6bad-4aed-a037-e925bf33a460

	 - 
```javascript
class CodeFile {
    constructor(codefileName){
        this.codefileName = codefileName
    }
}

 
class Formatter {
    format(codefile){}
}

 
class PythonFormatter extends Formatter {
 
    constructor(){
        super()
        console.log("Python Formatter instance created")
    }
     
   
    format(codefileName) {
        console.log(`"Formatting the Python ${codefileName} file you uploaded.`)
    }
 
}

class JavaFormatter extends Formatter {
 
    constructor(){
        super()
        console.log("Java Formatter instance created")
    }
     
   
    format(codefileName) {
        console.log(`"Formatting the Java ${codefileName} file you uploaded.`)
    }
 
}


class FormatterFactory {
  constructor() {
    this.myFormatterMap = new Map()
  }

  createFormatter(formatterType) {
    let formatter = this.myFormatterMap.get(formatterType)
    if (formatter == null) {
      if(formatterType == "Python"){
        formatter = new PythonFormatter()
      }
      else if(formatterType == "Java"){
        formatter = new JavaFormatter()
      }
      this.myFormatterMap.set(formatterType, formatter);
    }
    return formatter
  }
}

const codefile1 = new CodeFile("helloworld.py")
let formatter = new FormatterFactory()
const pythonFormatter = formatter.createFormatter("Python")
pythonFormatter.format(codefile1.codefileName)
//uploading new codefile Python file
const codefile2 = new CodeFile("test.py")
const anotherPythonFormatter = formatter.createFormatter("Python")
anotherPythonFormatter.format(codefile2.codefileName)
console.log("Both Python Formatter instances are the same? " + (anotherPythonFormatter === pythonFormatter))
//uploading a Java file
const codefile3 = new CodeFile("myfile.java")
const javaFormatter = formatter.createFormatter("Java")
javaFormatter.format(codefile3.codefileName)
```
id:: 0a1a2ee8-ba3c-4348-abb1-c569ecc16250

	 - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fsoftware-architecture%2FMYHAU-6GZc.png?alt=media&token=f6f29aa7-0592-4da8-a418-f84877dca5ba)
id:: a90a1fee-ab89-41cc-bbee-7238a54ccf7a

	 - When to use the flyweight pattern?
id:: 267f3225-a1db-454d-a06c-ac321105d49f
		 - This pattern should be used when your application has plenty of objects using similar data or when memory storage cost is high. JavaScript uses this pattern to share a list of immutable strings across the application.
id:: f7e6acbf-3e5f-462e-8337-fbccf7a7e645

		 - This pattern is mostly used in applications like network apps or word processors. It can also be used in web browsers to prevent loading the same images twice. The flyweight pattern allows caching of images. Therefore, when a web page loads, only the new images are loaded from the Internet, the already existing ones are fetched from the cache.
id:: 99aa7627-9659-411c-8ea1-43171b324e45
