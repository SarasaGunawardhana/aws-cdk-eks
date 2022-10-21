# aws-cdk-eks

Prerequisites 
- npm install -g typescript
- npm install -g aws-cdk
Bootstrapping
- cdk bootstrap aws://ACCOUNT-NUMBER/REGION

Create CDK application
    $ cdk init app --language typescript

Build 
- npm run build

List the stacks in the app (To verify that everything is working correctly, list the stacks in your app.)
- cdk ls

Synthesize an AWS CloudFormation template
- cdk synth
* The cdk synth command executes your app, which causes the resources defined in it to be translated into an AWS CloudFormation template. The displayed output of cdk synth is a YAML-format template. Following, you can see the beginning of our app's output. The template is also saved in the cdk.out directory in JSON format.


Deploy
- cdk deploy


Modify and verify
- cdk diff

Destroy
- cdk destroy

scope: Tells the bucket that the stack is its parent: it is defined within the scope of the stack. You can define constructs inside of constructs, creating a hierarchy (tree). Here, and in most cases, the scope is this (self in Python), meaning the construct that contains the bucket: the stack.

Id: The logical ID of the Bucket within your AWS CDK app. This (plus a hash based on the bucket's location within the stack) uniquely identifies the bucket across deployments. This way, the AWS CDK can update it if you change how it's defined in your app. Here, it's "MyFirstBucket." Buckets can also have a name, which is separate from this ID (it's the bucketName property).

props: A bundle of values that define properties of the bucket. Here we've defined only one property: versioned, which enables versioning for the files in the bucket.