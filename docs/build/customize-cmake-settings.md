---
title: 自定义 Visual Studio 中的 CMake 生成设置
ms.date: 03/05/2019
helpviewer_keywords:
- CMake build settings
ms.openlocfilehash: aa840dd41ee6843afae80343e42ba62741bbcd80
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824472"
---
# <a name="customize-cmake-build-settings"></a>自定义 CMake 生成设置

Visual Studio 提供了定义如何调用 CMake.exe 创建 CMake 缓存对于给定的项目的多个 CMake 配置。 若要添加新的配置，请单击工具栏中的下拉列表的配置，然后选择**管理配置**:

   ![CMake 管理配置](media/cmake-manage-configurations.png)

您可以从预定义的配置列表中选择：

   ![CMake 预定义的配置](media/cmake-configurations.png)

首次选择一个配置时，Visual Studio 将创建`CMakeSettings.json`项目的根文件夹中的文件。 此文件用于重新创建 CMake 缓存文件，例如，在“清除”操作后重新创建。 

若要添加其他配置，请右键单击`CMakeSettings.json`，然后选择**添加配置**。 

   ![CMake 添加配置](media/cmake-add-configuration.png "CMake 添加配置")

JSON IntelliSense 可帮助你编辑`CMakeSettings.json`文件：

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

此外可以编辑文件使用**CMake 设置编辑器**。 右键单击`CMakeSettings.json`中**解决方案资源管理器**，然后选择**编辑 CMake 设置**。 或者，选择**管理配置**从配置下拉列表顶部的编辑器窗口。 

您可以直接编辑`CMakeSettings.json`若要创建自定义配置下面的示例显示了可用作起始点的示例配置：

```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },

```

- **name**：显示在 C++ 配置下拉列表中的配置名称。 `${name}`宏可用于编写其他属性值，例如路径时使用此值。 有关示例，请参阅**buildRoot**中的定义`CMakeSettings.json`。

- **生成器**： 映射到 CMake **-G**切换并指定要使用的生成器。 此外可以为宏，使用此属性`${generator}`，当编写其他属性值。 Visual Studio 当前支持下列 CMake 生成器：

    - "Ninja"
    - "Visual Studio 14 2015"
    - "Visual Studio 14 2015 ARM"
    - "Visual Studio 14 2015 Win64"
    - "Visual Studio 15 2017"
    - "Visual Studio 15 2017 ARM"
    - "Visual Studio 15 2017 Win64"

    由于 Ninja 旨在加快生成速度，而不是为了提高灵活性和功能，因此它被设为默认生成器。 但是，某些 CMake 项目可能无法使用 Ninja 正确地进行生成。 如果发生这种情况，可以指示 CMake 改为生成 Visual Studio 项目。

    若要指定 Visual Studio 生成器，请打开`CMakeSettings.json`从主菜单中选择**CMake |更改 CMake 设置**。 删除“Ninja”并键入“V”。 这可激活 IntelliSense，从而可让用户选择所需生成器。

    当活动配置指定的 Visual Studio 生成器时，默认情况下 MSBuild.exe 调用使用了`-m -v:minimal`参数。 若要在自定义生成，`CMakeSettings.json`文件，可以指定其他[MSBuild 命令行参数](../build/msbuild-visual-cpp-overview.md)要传递给生成系统通过`buildCommandArgs`属性：
    
    ```json
    "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
    ```

- **buildRoot**：映射到 -DCMAKE_BINARY_DIR 开关，并指定要创建 CMake 的位置。 如果文件夹不存在，则会创建一个。

- **variables**：包含将作为 -D name=value 传递到 CMake 的 CMake 变量的名称/值对。 如果 CMake 项目生成指令指定将任何变量直接添加到 CMake 缓存文件，那么建议改为在这里添加它们。 下面的示例演示如何指定 14.14.26428 的名称-值对 MSVC 工具集：

```json
"variables": [
    {
      "name": "CMAKE_CXX_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe"
    },
    {
      "name": "CMAKE_C_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe"
    }
  ]
```

- **cmakeCommandArgs**：指定任何要传递到 CMake.exe 的其他开关。

- **configurationType**：定义所选生成器的生成配置类型。 当前支持的值为“Debug”、“MinSizeRel”、“Release”和“RelWithDebInfo”。

- ctestCommandArgs：指定运行测试时传递给 CTest 的其他开关。

- buildCommandArgs：指定传递给基础生成系统的其他开关。 例如，使用 Ninja 生成器强制输出命令行使用 Ninja 时，传递 -v。

有关 CMake Linux 项目提供了其他设置。 请参阅[配置 CMake Linux 项目](../linux/cmake-linux-project.md)。

## <a name="environment-variables"></a>环境变量

 `CMakeSettings.json` 此外支持任何上面提到的属性中使用环境变量。 所使用的语法为 `${env.FOO}`，用于展开环境变量 %FOO%。
此外，还可以使用此文件中内置的宏：

- `${workspaceRoot}`：提供工作区文件夹的完整路径
- `${workspaceHash}`：工作区位置的哈希；可用于创建当前工作区的唯一标识符（例如用于文件路径）
- `${projectFile}`：根 CMakeLists.txt 文件的完整路径
- `${projectDir}`：根 CMakeLists.txt 文件的文件夹完整路径
- `${thisFile}` – 的完整路径`CMakeSettings.json`文件
- `${name}`：配置的名称
- `${generator}`：配置中使用的 CMake 生成器的名称

## <a name="ninja-command-line-arguments"></a>Ninja 命令行参数

如果未指定目标，则生成“默认”目标（请参阅手册）。

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|选项|描述|
|--------------|------------|
| --version  | 打印 ninja 版本（“1.7.1”）|
|   -C DIR   | 在执行任何其他操作前更改为 DIR|
|   -f FILE  | 指定输入生成文件（默认值为 build.ninja）|
|   -j N     | 以并行方式运行 N 个作业（默认值为 14，派生自可用 CPU）|
|   -k N     | 持续操作，直到 N 个作业失败（默认值为 1）|
|   -l N     | 如果加载平均值大于 N，则不要启动新的作业|
|   -n       | 试运行（不运行命令但像命令行运行成功了一样操作）|
|   -v       | 在生成过程中显示所有命令行|
|   -d MODE  | 启用调试（使用 -d 列表列出模式）|
|   -t TOOL  | 运行次级工具（使用 -t 列表列出次级工具）。 终止顶级选项；有更多标志传递给工具|
|   -w FLAG  | 调整警告（使用-w 列表列出警告）|

## <a name="inherited-environments"></a>继承的环境

 `CMakeSettings.json` 支持继承环境。 此功能支持：(1) 继承默认环境，以及 (2) 创建在运行时传递给 CMake.exe 的自定义环境变量。

```json
  "inheritEnvironments": [ "msvc_x64_x64" ]
```

上面的示例与运行带有“-arch=amd64 -host_arch=amd64”参数的“适用于 VS 2017 的开发人员命令提示”一样。

下表显示默认值：

|上下文名称|描述|
|-----------|-----------------|
|vsdev|默认的 Visual Studio 环境|
|msvc_x86|使用 x86 工具为 x86 编译|
|msvc_arm| 使用 x86 工具为 ARM 编译|
|msvc_arm64|使用 x86 工具为 ARM64 编译|
|msvc_x86_x64|使用 x86 工具为 AMD64 编译|
|msvc_x64_x64|使用 64 位工具为 AMD64 编译|
|msvc_arm_x64|使用 64 位工具为 ARM 编译|
|msvc_arm64_x64|使用 64 位工具为 ARM64 编译|

### <a name="custom-environment-variables"></a>自定义环境变量

在中`CMakeSettings.json`，可以全局定义自定义环境变量或在配置每个**环境**属性。 下面的示例定义一个全局变量“BuildDir”，该变量在 x86-Debug 和 x64-Debug 配置中继承。 每个配置都使用该变量来指定配置的“buildRoot”属性值。 也请注意每个配置如何使用“inheritEnvironments”属性来指定仅应用于该配置的值。

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x86 compiler.
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.BuildDir}\\${name}"    },
    {
      "name": "x64-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x64 compiler.
      "inheritEnvironments": [ "msvc_x64" ],
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

在下一步的示例中，x86 调试配置定义自己的值为**BuildDir**属性。 此值将覆盖全局设置的值**BuildDir**属性，以便**BuildRoot**计算结果为`D:\custom-builddir\x86-Debug`。

```json
{
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",

      // The syntax for this property is the same as the global one above.
      "environments": [
        {
          // Replace the global property entirely.
          "BuildDir": "D:\\custom-builddir",
        }
      ],

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      // Evaluates to "D:\custom-builddir\x86-Debug"
      "buildRoot": "${env.BuildDir}\\${name}"
    },
    {
      "name": "x64-Debug",

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x64" ],
      // Since this configuration doesn’t modify BuildDir, it inherits
      // from the one defined globally.
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

## <a name="see-also"></a>请参阅

[在 Visual Studio 中的 CMake 项目](cmake-projects-in-visual-studio.md)<br/>
[配置 Linux CMake 项目](../linux/cmake-linux-project.md)<br/>
[连接到远程 Linux 计算机](../linux/connect-to-your-remote-linux-computer.md)<br/>
[配置 CMake 调试会话](configure-cmake-debugging-sessions.md)<br/>
[部署、运行和调试 Linux 项目](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake 预定义的配置参考](cmake-predefined-configuration-reference.md)<br/>
