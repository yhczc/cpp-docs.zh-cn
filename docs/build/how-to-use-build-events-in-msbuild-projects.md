---
title: 如何：在 MSBuild 项目中使用生成事件
ms.date: 11/04/2016
f1_keywords:
- msbuild.cpp.howto.usebuildevents
helpviewer_keywords:
- 'msbuild (c++), howto: use build events in projects'
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
ms.openlocfilehash: 7678b975558b245fb730bff35fb156bf21d7f895
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814108"
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>如何：在 MSBuild 项目中使用生成事件

生成事件是在生成过程中的某个特定阶段执行 MSBuild 的命令。 *预生成*事件发生在生成开始之前;*预链接*事件发生之前链接步骤开始; 并*后期生成*发生在生成后事件已成功结束。 仅当关联的生成步骤发生时，生成事件才会发生。 例如，如果链接步骤不会运行，也不会发生预链接事件。

每个生成三个事件由命令元素表示在项定义组中 (`<Command>`)，它执行和消息元素 (`<Message>`)，它是显示时**MSBuild**执行生成事件。 每个元素是可选的并且如果多次指定同一个元素，最后一个匹配项优先。

一个可选*在生成中使用*元素 (`<`*生成事件*`UseInBuild>`) 可以指定属性组，以指示是否执行生成事件中。 内容的价值*在生成中使用*元素是**true**或**false**。 默认情况下，除非执行生成事件其对应*在生成中使用*元素设置为`false`。

下表列出了每个生成事件 XML 元素：

|XML 元素|描述|
|-----------------|-----------------|
|`PreBuildEvent`|在生成开始之前执行此事件。|
|`PreLinkEvent`|此事件链接步骤开始之前执行。|
|`PostBuildEvent`|在生成完成之后执行此事件。|

下表列出了每个*在生成中使用*元素：

|XML 元素|描述|
|-----------------|-----------------|
|`PreBuildEventUseInBuild`|指定是否执行*预生成*事件。|
|`PreLinkEventUseInBuild`|指定是否执行*链接前*事件。|
|`PostBuildEventUseInBuild`|指定是否执行*后期生成*事件。|

## <a name="example"></a>示例

下面的示例可以在中创建的 myproject.vcxproj 文件的项目元素内添加[演练：使用 MSBuild 创建 Visual c + + 项目](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)。 一个*预生成*事件使 main.cpp 的副本; 以*预链接*事件使一个 main.obj; 的副本和一个*后期生成*事件生成 myproject.exe 的副本。 如果使用发布配置生成项目，则执行生成事件。 如果使用调试配置生成项目，则不执行生成事件。

```
<ItemDefinitionGroup>
  <PreBuildEvent>
    <Command>copy $(ProjectDir)main.cpp $(ProjectDir)copyOfMain.cpp</Command>
    <Message>Making a copy of main.cpp </Message>
  </PreBuildEvent>
  <PreLinkEvent>
<Command>copy $(ProjectDir)$(Configuration)\main.obj $(ProjectDir)$(Configuration)\copyOfMain.obj</Command>
    <Message>Making a copy of main.obj</Message>
  </PreLinkEvent>
  <PostBuildEvent>
<Command>copy $(ProjectDir)$(Configuration)\$(TargetFileName) $(ProjectDir)$(Configuration)\copyOfMyproject.exe</Command>
    <Message>Making a copy of myproject.exe</Message>
  </PostBuildEvent>
</ItemDefinitionGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">
  <PreBuildEventUseInBuild>true</PreBuildEventUseInBuild>
  <PreLinkEventUseInBuild>true</PreLinkEventUseInBuild>
  <PostBuildEventUseInBuild>true</PostBuildEventUseInBuild>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
  <PreBuildEventUseInBuild>false</PreBuildEventUseInBuild>
  <PreLinkEventUseInBuild>false</PreLinkEventUseInBuild>
  <PostBuildEventUseInBuild>false</PostBuildEventUseInBuild>
</PropertyGroup>
```

## <a name="see-also"></a>请参阅

[在命令行-c + + 的 MSBuild](msbuild-visual-cpp.md)<br/>
[演练：使用 MSBuild 创建 Visual C++ 项目](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)
