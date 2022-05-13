---
lab:
  title: 在 Azure 机器学习中运行试验
  module: Module 4 - Integrating Azure Databricks and Azure Machine Learning
ms.openlocfilehash: 164163c5477a4116e4f46d432f84058e6c420e52
ms.sourcegitcommit: e397eba14f6dd257b83e0584f42e459cfe84bfbd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "138100277"
---
# <a name="running-experiments-in-azure-machine-learning"></a>在 Azure 机器学习中运行试验

机器学习主要是关于训练模型，你可以使用这些模型为应用程序提供预测服务。 在本练习中，你将了解如何通过 Azure Databricks 在 Azure 机器学习中运行试验。

## <a name="prerequisites"></a>先决条件

在开始本实验室之前，请完成“Azure Databricks 入门”实验室以设置 Azure Databricks 环境并导入所需的数据和笔记本。

## <a name="install-libraries-on-the-azure-databricks-cluster"></a>在 Azure Databricks 群集上安装库

将运行的笔记本取决于需要在群集中安装的某些 Python 库。 以下步骤将引导你添加这些依赖项。

- 在 Azure Databricks 工作区中，从“群集”部分选择群集。 确保群集的状态为“正在运行”。
- 选择“库”链接，然后选择“新安装” 。
- 在库源中，选择 PyPi，然后在“包”文本框中键入 `azureml-sdk[databricks]`，然后选择“安装”  。
- 接下来将安装 `sklearn-pandas==2.1.0`
- 接下来将安装 `azureml-mlflow`

## <a name="deploy-an-azure-machine-learning-workspace"></a>部署 Azure 机器学习工作区

1. 如果已在订阅中创建了 Azure 机器学习工作区，则可以跳到[练习：在 Azure 机器学习中运行试验](#Exercise-Running-experiments-in-Azure-Machine-Learning)部分。

1. 在 [Azure 门户](https://portal.azure.com/#home)中创建新的资源：**机器学习**

1. 在显示的“创建机器学习工作区”对话框中，提供以下值：

   - **订阅**：选择自己的 Azure 订阅。
   - 资源组：选择在其中部署了 Azure Databricks 工作区的资源组。
   - 工作区名称：aml-ws
   - 区域：选择离你最近的区域（如果 Azure Databricks 工作区和 Azure 机器学习工作区位于不同位置，这是正常的）。

1. 查看并完成 Azure 机器学习工作区的创建。

## <a name="run-an-experiment-in-azure-machine-learning"></a>运行 Azure 机器学习中的试验

在本练习中，你将了解如何在 Azure Databricks 环境中加载和操作数据。

1. 在 Web 浏览器中，打开 Azure Databricks 工作区。

1. 如果群集未运行，请在“计算”页上，选择群集，然后使用“&#9654; 开始”按钮启动它 

1. 在 Azure Databricks 工作区中，使用左侧的命令栏，选择“工作区”。 然后选择“用户”，和 **&#9751; *your_user_name***。 然后，在名为“04 - 集成 Azure Databricks 和 Azure 机器学习”的文件夹中，打开“1.0 在 Azure 机器学习中运行试验”笔记本 。

1. 将笔记本附加到你的群集。 然后阅读笔记本中的笔记，依次运行每个代码单元。

## <a name="clean-up"></a>清理

如果现在已完成使用 Azure Databricks，请在 Azure Databricks 工作区的“计算”页上，选择你的群集，然后选择“&#9632; 终止”将其关闭 。 否则，让它继续运行以便在下一个练习中使用。
