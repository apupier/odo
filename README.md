# ocdev
[![Build Status](https://travis-ci.org/redhat-developer/ocdev.svg?branch=master)](https://travis-ci.org/redhat-developer/ocdev) [![codecov](https://codecov.io/gh/redhat-developer/ocdev/branch/master/graph/badge.svg)](https://codecov.io/gh/redhat-developer/ocdev)

## What is ocdev?
OpenShift Command line for Developers

## Installation
You can [download](https://dl.bintray.com/ocdev/ocdev/latest/) latest binaries (build automatically from current master branch).

### How to use ocdev as an oc plugin?
- make sure that ocdev binary exists in your $PATH
- copy the [plugin.yaml](./plugin.yaml) file to ~/.kube/plugins/ocdev/
- use the plugin as `oc plugin dev`

### Concepts

- An **_application_** is, well, your application! It consists of multiple microservices or components, that work individually to build the entire application.
- A **_component_** can be thought of as a microservice. Mutliple components will make up an application. A component will have different attributes like storage, etc.
Multiple component types are currently supported, like nodejs, perl, php, python, ruby, etc.

### Getting Started

1. Create and start working on a new application:
`ocdev application create <application name>`

2. Deploy code in current directory:
`ocdev component create <component type> --dir=.`

3. Test your application and make changes to the code

4. Deploy changes to the application:
`ocdev component push`

5. Go back to 3.

### CLI Structure
```
ocdev --verbose : OpenShift CLI for Developers
    application : application
        create : create an application
        delete : delete the given application
        get --short : get the active application
        list : lists all the applications
    completion : Output shell completion code
    component : components of application
        create --binary --dir --git : component create <component_type> [component_name]
        delete : component delete <component_name>
        get --short : component get
        push --dir : component push
    storage --component : storage
        add --path --size : create storage and mount to component
        list : list storage attached to a component
        remove : remove storage from component
    version : Print the version of ocdev
```
*_autogenerated_