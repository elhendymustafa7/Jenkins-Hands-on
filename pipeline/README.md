# Pipeline In Jenkins
<pre>
- Scripted Pipeline     => node {}
- Declarative Pipeline  => pipeline {}
</pre>

```
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
```

## Agent in jenkins Declarative Pipeline
<pre>
- any     => run pipeline in any available system
- label   => run on specific agent 
- docker  => Jenkins agent that runs inside a Docker container
- run     => defer agent selection to stages
</pre>

