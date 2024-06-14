# 1_Jenkins File & Pipeline

### Jenkins File

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/v1h3iUgAnpGkKSmi-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/v1h3iUgAnpGkKSmi-image.png)

As discussed in the [Defining a Pipeline in SCM](https://www.jenkins.io/doc/book/pipeline/getting-started#defining-a-pipeline-in-scm), a `Jenkinsfile` is a text file that contains the definition of a Jenkins Pipeline and is checked into source control. Consider the following Pipeline which implements a basic three-stage continuous delivery pipeline

### Jenkins File Code

For more: [Using a Jenkinsfile](https://www.jenkins.io/doc/book/pipeline/jenkinsfile/)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/fBDgVuNkOiQOgo21-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/fBDgVuNkOiQOgo21-image.png)

- **Pipeline**: The task you are trying to accomplish. Like building or deploying some code.
- **Build Agent**: the place that runs your pipeline.
- **Stages**: structures your script into a high-level sequence. Stages show up as columns in the Pipeline Stage view with average stage times and colors for the stage result.
- **Steps**: is one way to specify what shall happen. sh is of a similar quality, it is a different kind of action. (You can also use build for things that are already specified as projects.)

### Multi-Stage Pipelines

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/FdFGFIP9j1NLGyvc-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/FdFGFIP9j1NLGyvc-image.png)

one Jenkins file with multiple stages. With multiple stage pipelines, if the Dev fails, it won't move to staging until it is fixed.