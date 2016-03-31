
# my maven archetype

A simple Java8 archetype.

## Builtins

#### Plugins

- maven-compiler-plugin
- maven-source-plugin
- maven-javadoc-plugin
- maven-release-plugin
- maven-deploy-plugin
- site-maven-plugin

#### Dependencies

- junit.junit
- org.slf4j.slf4j-api
- org.slf4j.slf4j-asimple
- org.apache.commons.commons-lang3
- joda-time.joda-time
- org.projectlombok.lombok


## How to use

### Install archetype

```
# git clone https://github.com/asufana/my-maven-archetype
# cd my-maven-archetype
# mvn install
```

### Create project

```
# mvn archetype:generate \
	-DinteractiveMode=false \
	-DarchetypeGroupId=com.github.asufana \
	-DarchetypeArtifactId=my-maven-archetype \
	-DgroupId={YOUR_GROUP_ID} \
	-DartifactId={YOUR_ARTIFACT_ID}
# cd {YOUR_ARTIFACT_ID}
# mvn eclipse:eclipse
```

### Release project

Modify scm parameters at pom.xml.

```
# mvn release:prepare
# mvn release:perform
```

### Fetch from github

```pom.xml
<dependencies>
    <dependency>
        <groupId>{YOUR_GROUP_ID}</groupId>
        <artifactId>{YOUR_ARTIFACT_ID}</artifactId>
        <version>1.0</version>
    </dependency>
</dependencies>

<repositories>
    <repository>
        <id>github</id>
        <url>https://raw.github.com/{YOUR_ACCOUNT_NAME}/{YOUR_ARTIFACT_ID}/mvn-repo/</url>
        <snapshots>
            <enabled>true</enabled>
            <updatePolicy>always</updatePolicy>
        </snapshots>
    </repository>
</repositories>
```

### Fetch from github for PlayFramework1

```dependencies.yml
require:
    - play
    - {YOUR_GROUP_ID} -> {YOUR_ARTIFACT_ID} [1.0,)

repositories:
    - github:
        type:   iBiblio
        root:   https://raw.github.com/{YOUR_ACCOUNT_NAME}/{YOUR_ARTIFACT_ID}/mvn-repo/
        contains:
            - {YOUR_GROUP_ID} -> *
```
