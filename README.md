This is for MTN
<p align="right">
<img src="https://travis-ci.org/google/libphonenumber.svg?branch=master">
</p>

# What is it?

This is a fork of [Google's libphone library](https://github.com/google/libphonenumber). The original Readme can be viewed [here](https://github.com/google/libphonenumber/blob/master/README.md). This fork was created to allow MTN specific updates the library.

# How to make changes for MTN

*   Clone this repository
*   Make changes to the data in the ./resources folder, and commit the changes.
*   In the ./java folder run the command ant -f build.xml (see [making-metadata-changes.md](making-metadata-changes.md) for more infomation)
*   Create a pull request into the master branch. 
*   Once the PR is accepted and the changes merged into master the Azure pipelines will build run mvn clean install from the ./java folder, push the articfacts to our nexus repository


