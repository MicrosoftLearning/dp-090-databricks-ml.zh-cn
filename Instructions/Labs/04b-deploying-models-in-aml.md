---
lab:
  title: 在 Azure 机器学习中部署模型
  module: Module 4 - Integrating Azure Databricks and Azure Machine Learning
ms.openlocfilehash: 3d1af4dc5af8a66548c81e00f5d6012db1cb8f00
ms.sourcegitcommit: dd49d0d418bf18117549cc0ea1542b754ace865c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/25/2022
ms.locfileid: "139217554"
---
# <a name="deploying-models-in-azure-machine-learning"></a>在 Azure 机器学习中部署模型

机器学习主要是关于训练模型，你可以使用这些模型为应用程序提供预测服务。 在本练习中，你将了解如何在 Azure Databricks 中训练模型，然后在 Azure 机器学习中部署模型。

## <a name="prerequisites"></a>先决条件

在开始本实验室之前，请完成“Azure Databricks 入门”和“在 Azure 机器学习中运行试验”实验室，以设置 Azure Databricks 和 Azure 机器学习环境 。

## <a name="install-libraries-on-the-azure-databricks-cluster"></a>在 Azure Databricks 群集上安装库

将运行的笔记本取决于需要在群集中安装的某些 Python 库。 以下步骤将引导你添加这些依赖项。

- 在 Azure Databricks 工作区中，从“群集”部分选择群集。 确保群集的状态为“正在运行”。
- 选择“库”链接，然后选择“新安装” 。
- 在库源中，选择 PyPi，然后在“包”文本框中键入 `azureml-sdk[databricks]`，然后选择“安装”  。
- 接下来将安装 `sklearn-pandas==2.1.0`
- 接下来将安装 `azureml-mlflow`

## <a name="deploy-a-model-in-azure-machine-learning"></a>在 Azure 机器学习中部署模型

在本练习中，你将了解如何在 Azure Databricks 环境中加载和操作数据。

1. 在 Web 浏览器中，打开 Azure Databricks 工作区。

1. 如果群集未运行，请在“计算”页上，选择群集，然后使用“&#9654; 开始”按钮启动它 

1. 在 Azure Databricks 工作区中，使用左侧的命令栏，选择“工作区”。 然后选择“用户”，和 **&#9751; *your_user_name***。 然后，在名为“04 - 集成 Azure Databricks 和 Azure 机器学习”的文件夹中，打开“2.0 在 Azure 机器学习中部署模型”笔记本 。

1. 将笔记本附加到你的群集。 然后阅读笔记本中的笔记，依次运行每个代码单元。

## <a name="clean-up"></a>清理

如果现在已完成使用 Azure Databricks，请在 Azure Databricks 工作区的“计算”页上，选择你的群集，然后选择“&#9632; 终止”将其关闭 。

如果已完成 Azure Databricks 探索，则可以删除 Azure 订阅中包含 Azure Databricks 和 Azure 机器学习资源的资源组。
