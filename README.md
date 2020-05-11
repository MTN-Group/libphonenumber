# What is it?

This is a fork of [Google's libphone library](https://github.com/google/libphonenumber). The original Readme can be viewed [here](https://github.com/google/libphonenumber/blob/master/README.md). This fork was created to allow MTN specific updates the to the library.

### Making changes for MTN

*   Clone this repository, create and checkout your feature branch
*   Make changes to the data in the ./resources folder.
*   In the ./java folder run the command ant -f build.xml (see [making-metadata-changes.md](making-metadata-changes.md) for more infomation)
*   Commit and push.
*   Create a pull request into the master branch. 
*   Once the PR is accepted and the changes merged into master the Azure pipelines will build run mvn clean install from the ./java folder, push the articfacts to our nexus repository

### Keeping this fork in-sync with the upstream repo.

Run the following commands:
```
git remote add upstream git@github.com:google/libphonenumber.git
git fetch upstream
git checkout master
git merge upstream/master
```
Be prepared for alot of conflicts. Fix the conflicts by keeping the latest google versions pre-pended with mtn00x-.

### Using this library for maven based projects

Add the following dependencies to your project:
```     
<dependency>
    <groupId>com.googlecode.libphonenumber</groupId>
    <artifactId>mtn-libphonenumber</artifactId>
    <version>mtn-001-8.12.4-SNAPSHOT</version>
</dependency>
<dependency>
    <groupId>com.googlecode.libphonenumber</groupId>
    <artifactId>mtn-carrier</artifactId>
    <version>mtn001-1.130-SNAPSHOT</version>
</dependency>
<dependency>
    <groupId>com.googlecode.libphonenumber</groupId>
    <artifactId>mtn-geocoder</artifactId>
    <version>mtn001-2.140-SNAPSHOT</version>
</dependency>
```


