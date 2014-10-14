aws-sdk-java-archetype
======================

The AWS SDK for Java Maven archetype allows you to easily create new Java projects configured with the [AWS SDK for Java](http://aws.amazon.com/sdkforjava/) and some sample code to help you find your way around the SDK.

Starting a project from the archetype is easy:
<pre>
mvn archetype:generate \
     -DarchetypeGroupId=com.amazonaws \
     -DarchetypeArtifactId=aws-java-sdk-archetype
</pre>

When you run the Maven <code>archetype:generate</code> goal, you'll be prompted for some basic Maven values for your new project <i>(<a href="http://maven.apache.org/guides/mini/guide-naming-conventions.html">groupId, artifactId, version</a>)</i>.

<pre>
[INFO] Generating project in Interactive mode
[INFO] Archetype [com.amazonaws:aws-java-sdk-archetype:1.0.0] found in catalog local
Define value for property 'groupId': : com.foo   
Define value for property 'artifactId': : my-aws-java-project
Define value for property 'version':  1.0-SNAPSHOT: : 
Define value for property 'package':  com.foo: : 
</pre>

When the <code>archetype:generate</code> goal completes, you'll have a new Maven Java project, already configured with a dependency on the AWS SDK for Java and some sample code in the project to help you get started with the SDK.

Before you run the sample code, you'll need to fill in your AWS security credentials.  This sample loads your credentials from the default credentials profiles file <i>(~/.aws/credentials)</i>.  If you've already set up your profile credentials file, then you're ready to run the sample.  If you haven't set up your <code>~/.aws/credentials</code> file yet, here's what you should start with:
<pre>
[default]
aws_access_key_id     = <your AWS access key>
aws_secret_access_key = <your AWS secret access key>
</pre>

When your AWS security credentials are configured, you're ready to compile and run the new project.  The sample project's POM file is configured so that you can easily compile, jar, and run the project by executing <code>mvn package exec:java</code>.  
