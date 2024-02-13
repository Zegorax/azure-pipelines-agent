# Contribute (Dev)

## Dev Dependencies

![Win](res/win_sm.png) Git for Windows [Install Here](https://git-scm.com/downloads) (needed for dev sh script)

## Build, Test, Layout 

From src:

![Win](res/win_sm.png) `dev {command}`  

![*nix](res/linux_sm.png) `./dev.sh {command}`
  
**Commands:**  

`layout` (`l`):  Run first time to create a full agent layout in {root}/{runtime_id}/_layout  

`build` (`b`):   build everything and update agent layout folder  

`test` (`t`):    build agent binaries, run unit tests applicable to the current platform

Normal dev flow:
```bash
git clone https://github.com/microsoft/azure-pipelines-agent
cd ./src
./dev.(sh/cmd) layout # the agent that build from source is in {root}/{runtime_id}/_layout
<make code changes>
./dev.(sh/cmd) build # {root}/{runtime_id}/_layout will get updated
./dev.(sh/cmd) test # run unit tests before git commit/push
```

## Editors

[Using Visual Studio 2017](https://www.visualstudio.com/vs/)  
[Using Visual Studio Code](https://code.visualstudio.com/)

## Debugging in Visual Studio Code
Debugging in Visual Studio Code is supported out of the box.
To correctly use it, perform the following steps:
1) Clone the project
2) Open the project folder in VS Code
3) Pres F5 or click the "Run and Debug" tab on the left, and start the debugging process by clicking the green triangle
4) The project will compile once
5) Debugging will start and fail (agent is not configured)
6) Run the following commands:
    1) `cd _layout/linux-x64 && ./config.sh`
    2) Follow the instructions to register your agent in your DevOps tenant
7) Debug your project again

## Styling

We use the dotnet foundation and CoreCLR style guidelines [located here](
https://github.com/dotnet/corefx/blob/master/Documentation/coding-guidelines/coding-style.md)

## Troubleshooting build or test problems

'unzip' not found
- if you see this while building or testing on Windows, you need to install unzip for the Windows bash shell
- open a command window, run bash, and run `sudo apt install unzip` to get that tool installed


