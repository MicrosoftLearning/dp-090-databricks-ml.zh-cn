---
lab:
  title: 使用 MLflow 跟踪试验
  module: Module 3 - Managing Experiments and Models
ms.openlocfilehash: 931fc6d405a591dab6f2539e590eb11ba0b8c7ba
ms.sourcegitcommit: e397eba14f6dd257b83e0584f42e459cfe84bfbd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "138100258"
---
# <a name="using-mlflow-to-track-experiments"></a>使用 MLflow 跟踪试验

MLflow 是一个功能齐全的模型跟踪和注册表系统。  在本练习中，你将使用 MLflow 收集模型训练项目、指标和参数。  然后，你将能够通过 Azure Databricks UI 或以编程方式查看这些输出。 首先，你需要使用交互式群集访问 Azure Databricks 工作区。 如果没有工作区和/或所需的群集，请按照下面的说明操作。 否则，可以跳到[上传 Databricks 笔记本存档](#Upload-the-Databricks-notebook-archive)部分。

## <a name="prerequisites"></a>先决条件

在开始本实验室之前，请完成 [Azure Databricks 入门](Instructions/Labs/01a-introduction-to-azure-databricks.md)实验室以设置 Azure Databricks 环境并导入所需的数据和笔记本。 若要使用 MLflow，需要按照安装实验室中的说明，将计算群集与 ML Databricks Runtime 版本结合使用。 此运行时已包括 MLflow 的安装。

## <a name="use-mlflow-to-track-experiments"></a>使用 MLflow 跟踪试验

在本练习中，你将了解如何在 Azure Databricks 环境中加载和操作数据。

1. 在 Web 浏览器中，打开 Azure Databricks 工作区。

1. 如果群集未运行，请在“计算”页上，选择群集，然后使用“&#9654; 开始”按钮启动它 

1. 在 Azure Databricks 工作区中，使用左侧的命令栏，选择“工作区”。 然后选择“用户”，和 **&#9751; *your_user_name***。 然后在名为“03 - 管理试验和模型”的文件夹中，打开“01 - 使用 MLflow 跟踪试验”笔记本 。

1. 将笔记本附加到你的群集。 然后阅读笔记本中的笔记，依次运行每个代码单元。

> **提示**：在标题为“使用 Databricks UI 查看试验、运行和运行详细信息”部分中，将有关于要执行哪些操作的说明，因为这些操作将在笔记本范围之外进行。  最简单的方法是在浏览器中打开第二个选项卡，边查看笔记本中的说明边在该选项卡中执行这些操作。

## <a name="clean-up"></a>清理

如果现在已完成使用 Azure Databricks，请在 Azure Databricks 工作区的“计算”页上，选择你的群集，然后选择“&#9632; 终止”将其关闭 。 否则，让它继续运行以便在下一个练习中使用。
