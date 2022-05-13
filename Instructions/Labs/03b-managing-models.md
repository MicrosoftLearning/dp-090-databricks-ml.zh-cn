---
lab:
  title: 管理模型
  module: Module 3 - Managing Experiments and Models
ms.openlocfilehash: 8989b8319c3fd55cda9c776b566b8a4a1c2b6d16
ms.sourcegitcommit: dd49d0d418bf18117549cc0ea1542b754ace865c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/25/2022
ms.locfileid: "139217560"
---
# <a name="managing-models"></a>管理模型

Azure Databricks 模型注册表是用于模型注册、模型版本控制以及标记模型以供部署的强大工具。  在本练习中，你将了解如何通过用户界面和 MLflow API 使用模型注册表。 首先，你需要使用交互式群集访问 Azure Databricks 工作区。 如果没有工作区和/或所需的群集，请按照下面的说明操作。 否则，可以跳到[上传 Databricks 笔记本存档](#Upload-the-Databricks-notebook-archive)部分。

## <a name="prerequisites"></a>先决条件

在开始本实验室之前，请完成“Azure Databricks 入门”实验室以设置 Azure Databricks 环境并导入所需的数据和笔记本。

## <a name="manage-models"></a>管理模型

在本练习中，你将学习如何管理模型。

1. 在 Web 浏览器中，打开 Azure Databricks 工作区。

1. 如果群集未运行，请在“计算”页上选择群集，然后使用“&#9654; 开始”按钮启动它 

1. 在 Azure Databricks 工作区中，使用左侧的命令栏，选择“工作区”。 然后选择“用户”和 &#9751; your_user_name******。 然后在名为“03 - 管理试验和模型”的文件夹中，打开“02 - 管理模型”笔记本 。

1. 将笔记本附加到你的群集。 然后阅读笔记本中的笔记，依次运行每个代码单元。

> **提示**：对于第一部分“通过用户界面管理模型”，将有关于要执行的操作的说明，因为大多数这些操作将在笔记本的限制之外进行。  最简单的方法可能是在浏览器中打开第二个选项卡，并在该选项卡中执行这些操作，同时查看笔记本中的说明。

## <a name="clean-up"></a>清理

如果现在已完成使用 Azure Databricks，请在 Azure Databricks 工作区的“计算”页上选择你的群集，然后选择“&#9632; 终止”将其关闭 。 否则，让它继续运行以便你在下一个练习中使用。
