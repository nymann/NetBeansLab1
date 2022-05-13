# NetBeansLab1

### Introduction

In this assignment, we apply the NetBeans Platform in the Asteroid game setting.

### Objectives

The objective of this assignment is to get familiar with the NetBeans module system,
provide sufficient information to get started with CODA practice using NetBeans platform, and
appreciate the component-oriented features of the NetBeans platform.

### Homework

- At minimal get acquainted with the Run-time Container and Lookup API by watching video
  part 1 and 2 at
  [Top 10 NetBeans APIs tutorials](https://drive.google.com/drive/folders/1BJF9l_Wd9dTQEdHfywj_kw6F9wuPlMPd).
  Note, some of the tutorials are a bit outdated but most of them are still valid.

### Classwork

I expect you to focus on the NetBeans module system. For those of you who are
interested in Rich Client Development using the NetBeans platform I can recommend the full book [Boc11](#boc11).

- Always remember to pull in changes from the shared GitHub repository.
- Try the get the minimal Run-time Container running. That is, the following modules:
  - org-netbeans-bootstrap
  - org-openide-filesystems
  - org-netbeans-core-startup
  - org-openide-modules
  - org-openide-util and org-openide-util-lookup.

See [NBRun-timeExample](https://github.com/sweat-tek/SB4-KOM-F20/tree/master/NBRuntimeExample12).

- Port the components from previous [JavaLab](https://drive.google.com/file/d/1230YX4-bS_8-lXXFp4qqAC1f_mLAmDl9/view)
  and use the NetBeans `@Serviceprovider` annotation to register the services and the Lookup to find the service
  providers.
- Use following maven archetype for setup of Netbeans platform in the IDE:
  org.apache.netbeans.archetypes:netbeans-platform-app-archetype:1.22
- It can be run by the maven commandline as:

```sh
mvn -DarchetypeGroupId=org.apache.netbeans.archetypes
-DarchetypeArtifactId=netbeans-platform-app-archetype
-DarchetypeVersion=1.22
-DgroupId=<GROUP_ID> -DartifactId=<PROJECT_NAME>
-Dversion=1.0-SNAPSHOT
-DnetbeansVersion=RELEASE126
org.apache.maven.plugins:maven-archetype-plugin:3.1.2:generate
```

see [MvnCLI](https://drive.google.com/file/d/1HK-eaEbSoFBmE36VU9vlcCgcGzAQHTJY/view)

- Use following maven archetype from IDE for creating new Netbeans modules:
  org.apache.netbeans.archetypes:nbm-archetype:1.17
- To register the Core module main, create a Class that extends “ModuleInstall” and overrides
  the “restored()” method, see
  [AsteroidsNetbeansInstall](https://github.com/sweat-tek/SB4-KOM-F20/blob/master/AsteroidsNetbeansModules/Core/src/main/java/dk/sdu/mmmi/cbse/core/main/Installer.java).
- Register the class in the “manifest.mf” file using the “OpenIDE-Module-Install” tag, see
  [AsteroidsNetbeansManifest](https://github.com/sweat-tek/SB4-KOM-F20/tree/master/AsteroidsNetbeansModules/Core/src/main/nbm).

### Literature

##### [Boc11](https://drive.google.com/file/d/1bvQFztq1x3iEd2zJj6N6YPil48K56J00/view)

> Heiko Bock. The Definitive Guide to NetBeansTM Platform 7. Apress, 2011.
