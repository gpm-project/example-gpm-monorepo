# gpm-example

A repository with the reference layout for generating protos with [GPM](https://github.com/gpm-project/grpc-proto-manager).

## Structure

The basic structure expected by the grpc-proto-manager is a simple set of directories from the project root, each of them containing a set of `.proto` files. Optionally, you may specify a `.protolangs` file with the target languages for the generation.

```
├── | <high-level-entity>
│   ├── [.protolangs]
│   └── myprotofile.proto
```

## GPM YAML

To specify how the generation should be done, GPM expects a `.gpm.yaml` at the root project level. The contents of this file are as follows:

```
tempPath: /tmp/gpm
repositoryProvider: github
repositoryOrganization: dhiguero
defaultLanguage: go
```

Where:

* **tempPath**: Specifies the path of a temporal directory used to create intermediate code.
* **repositoryProvider**: Selects the type of repository interface.
* **repositoryOrganization**: Selects the the target organization in the repository provider. In the example, it translates into the generated code being pushed to `github.com/gpm-project/grpc-<high-level-entity>-<language>`.
* **defaultLanguage**: Defines the target language if the `.protolangs` file is not found. 

For further information check the YAML format on [GPM](https://github.com/gpm-project/grpc-proto-manager).

## License

Copyright 2020 GPM Project.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.