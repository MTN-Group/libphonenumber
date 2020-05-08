# What is it?

This is a fork of [Google's libphone library](https://github.com/google/libphonenumber). The original Readme can be viewed [here](https://github.com/google/libphonenumber/blob/master/README.md). This fork was created to allow MTN specific updates the to the library.

### Making changes for MTN

*   Clone this repository
*   Make changes to the data in the ./resources folder, and commit the changes.
*   In the ./java folder run the command ant -f build.xml (see [making-metadata-changes.md](making-metadata-changes.md) for more infomation)
*   Create a pull request into the master branch. 
*   Once the PR is accepted and the changes merged into master the Azure pipelines will build run mvn clean install from the ./java folder, push the articfacts to our nexus repository

### Keeping this fork in-sync with the upstream repo.

After cloning, run the following commands:
```git remote add upstream git@github.com:google/libphonenumber.git
git fetch upstream
git checkout master
git merge upstream/master
```

### Using this library for maven based projects

Add the following dependencies to your project:
```     
        <dependency>
            <groupId>com.googlecode.libphonenumber</groupId>
            <artifactId>mtn-libphonenumber</artifactId>
            <version>8.12.3-SNAPSHOT</version>
        </dependency>
        <dependency>
            <groupId>com.googlecode.libphonenumber</groupId>
            <artifactId>mtn-carrier</artifactId>
            <version>1.129-SNAPSHOT</version>
        </dependency>
        <dependency>
            <groupId>com.googlecode.libphonenumber</groupId>
            <artifactId>mtn-geocoder</artifactId>
            <version>2.139-SNAPSHOT</version>
        </dependency>
```


