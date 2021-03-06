# Rock, Paper, Scissors game
Solution for Rock, Paper, Scissors coding puzzle.

## Description
Refer to _Description.pdf_ for details on required functionalities.

### Pre-requirements
Pre-requirements to successfully compile and run coding puzzle are:
  - Linux/Windows
  - Oracle JDK 8

### Usage
For compiling, running unit tests and packaging Lightbend Activator can be used. Activator launcher and executable scripts are included in the project in _bin/_ and _libexec/_ locations.
If on Linux machine, make sure Activator script has sufficient permissions to be run:
```sh
$ chmod 777 bin/activator
```
Alternatively, if SBT is installed on machine, it can be directly used instead.
Following subsections explain solution usage using Lightbend Activator.
##### Compile
Linux:

```sh
$ bin/activator compile
```
Windows:
```bat
> bin\activator.bat compile
```

##### Run unit tests
Linux:
```sh
$ bin/activator test
```
Windows:
```bat
> bin\activator.bat test
```

##### Run using Lightbend Activator
Linux:
```sh
$ bin/activator run
```
Windows:
```bat
> bin\activator.bat run
```

##### Create installation _zip_ file
Linux:
```sh
$ bin/activator universal:packageBin
```
Windows:
```bat
> bin\activator.bat universal:packageBin
```
Upon completion installation zip file _roshambo_1.0.0.zip_ can be found in _target/universal_ folder. Also, API docs are generated during this process.

##### Install
Installation consists of extracting previously generated installation zip file _roshambo_1.0.0.zip_.

##### Run
Goto _roshambo-1.0.0_ installation folder and run commands bellow.

Linux:
```sh
$ cd roshambo-1.0.0/bin
$ ./roshambo
```
Windows:
```bat
> cd roshambo-1.0.0\bin
> roshambo.bat
```

#### API Docs
Roshambo API docs can be found in _target/scala-2.12/api_ folder. Open _index.html_ in your favourite browser.

##### Create Eclipse project files
Linux:
```sh
$ bin/activator eclipse
```
Windows:
```bat
> bin\activator.bat eclipse
```
Make sure Eclipse is using Scala 2.12.2 version and Eclipse project output folder is changed from _bin/_ to _classes/_!
If project output folder is not changed Eclipse could by accident delete Activator scripts located in _bin/_ folder. In that case re-download scripts from GitHub repository.

### Docker image
Requirement for creating and publishing Docker image is having the docker console client, version 1.3 or higher, installed. SBT Native Packager doesn’t use the REST API, but instead uses the CLI directly.

Linux:
```sh
$ bin/activator docker:publishLocal
```
Windows:
```bat
> bin\activator.bat docker:publishLocal
```
Run a command in a new container:
```sh
docker run -a stdin -a stdout -i -t roshambo:1.0.0
```
