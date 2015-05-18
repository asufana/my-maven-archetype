
# my maven archetype

### Install

```shell
# git clone https://github.com/asufana/my-maven-archetype
# cd my-maven-archetype
# mvn install
```

### Create project

```shell 
# mvn archetype:generate \
	-DinteractiveMode=false \
	-DarchetypeGroupId=com.github.asufana \
	-DarchetypeArtifactId=my-maven-archetype \
	-DgroupId={YOUR_GROUP_ID} \
	-DartifactId={YOUR_ARTIFACT_ID}
# cd {YOUR_ARTIFACT_ID}
# mvn eclipse:eclpse
```
