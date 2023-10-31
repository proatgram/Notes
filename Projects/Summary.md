# Summary
This merge request is focused on adding CMake support to further expand the capabilities and usability of this project. Using CMake will allow other projects that do not rely on Bazel to much easily include Nearby and use it. 

## Bazel vs CMake integration challanges
Bazel is not easy to integrate into other build systems, often requiring workarounds to include a single library (From personal experience). Bazel, is also not the most friendly when it comes to LSP integration, as it doesn't at this current moment offer a way to export any kind of compilation database to use with LSP's and Intellisense, making developers' work harder when they don't have access to internal build resources and tools. However, using CMakes `CMAKE_EXPORT_COMPILE_COMMANDS` flag, this is made easy, with no need to use a workaround like `bazel-compdb`. Not having LSP hints or technology like Intellisense makes developers work more difficult to spot issues at the time of writing code. Having a half baked support for it is possibly worse, giving developers false errors and warnings when none are actually being thrown.

## Compatability Considerations
All of this being said, this implementation is made with much thought put into it in order to maintain compatibility with both Bazel and CMake, while having as many features in both. Both do, and will compile the same (with one exception), so the end user depending on their needs can choose whichever one they need to better integrate it into their project without needing to worry about features they will get in one build system over the other.

The Protobuf version specified in the `WORKSPACE` file for Bazel does not have the required CMake implementation for including Protobuf generation functions into the project at configure time. For this reason the version has been bumped up to the first version that changes this, allowing us to include the CMake file relavent to the genration of Protobuf files in at configure time, which is needed when pulling a specific version similar to Bazel.

## External Dependency Management
Dependency management heavily relies on CMakes `FetchContent` module to fetch dependencies similar to Bazels `http_archive`. Using this, we are able to have a centralized area where dependencies are downloaded (or cloned) and have predictable outputs for each dependency. Because we are including our dependencies with the build, it is usually harder to maintain and install when install rules are added in CMake due to us needing to include those in the install9/9/23. This is an issue that needs further talk if this route is taken.

## Testing
Testing will use CTest with GTest compiled testing binaries. This is currently in the works (see [this](https://github.com/google/nearby/issues/408#issuecomment-1704557872) comment). Testing will have the same coverage as testing done with Bazel, using the same targets and binaries, with GTest. Running unit tests would be as simple as running `ctest`, or even running the testing binaries directly. The goal is to have the same functionality with the Bazel testing targets.

## Notes
This PR uses sources from #2098, which adds Linux platform support.

## TODOS
### CMake specific
 - [ ] Formatting
 - [ ] Install targets for Linux
 - [ ] Testing targets
 - [ ] Export targets

### Implementation specific
 - [ ] Implement g3 building, which is used by tests
 - [ ] Implement other Nearby libraries, such as fast pair and presence