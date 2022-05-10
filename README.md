# Proxy for Jcenter

In your build.gradle you can replace:
```gradle
    repositories {
        google()
        jcenter()
    }
```

with:
```gradle
    repositories {
        google()
        mavenCentral()
        jcenter {            
            url "http://localhost:6001/" 
            allowInsecureProtocol = true 
        }
    }
```

You can run:
`node index.mjs`

When you run it Android Studio will call `http://localhost:6001` to obtain java packages which are pulled from Jcenter but captured in the `cache` folder.

