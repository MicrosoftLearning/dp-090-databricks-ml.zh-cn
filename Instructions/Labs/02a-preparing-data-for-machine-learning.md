---
lab:
  title: 为机器学习准备数据
  module: Module 2 - Training and Evaluating Machine Learning Models
ms.openlocfilehash: c779c63d3b34c05606a93671ba800fd848bed439
ms.sourcegitcommit: e397eba14f6dd257b83e0584f42e459cfe84bfbd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "138100255"
---
# <a name="preparing-data-for-machine-learning"></a>为机器学习准备数据

机器学习主要是关于训练模型，你可以使用这些模型为应用程序提供预测服务。 在本练习中，你将了解如何使用 Azure Databricks 准备用于机器学习的训练数据。

## <a name="prerequisites"></a>先决条件

在开始本实验室之前，请完成“Azure Databricks 入门”实验室以设置 Azure Databricks 环境并导入所需的数据和笔记本。

## <a name="prepare-data-for-machine-learning"></a>为机器学习准备数据

在本练习中，你将了解如何在 Azure Databricks 环境中加载和操作数据。

1. 在 Web 浏览器中，打开 Azure Databricks 工作区。

1. 如果群集未运行，请在“计算”页上，选择群集，然后使用“&#9654; 开始”按钮启动它 

1. 在 Azure Databricks 工作区中，使用左侧的命令栏，选择“工作区”。 然后选择“用户”，和 **&#9751; *your_user_name***。 然后在名为“02 - 训练和评估机器学习模型”的文件夹中，打开“1.0 特征化”笔记本 。

1. 将笔记本附加到你的群集。 然后阅读笔记本中的笔记，依次运行每个代码单元。

## <a name="clean-up"></a>清理

如果现在已完成使用 Azure Databricks，请在 Azure Databricks 工作区的“计算”页上，选择你的群集，然后选择“&#9632; 终止”将其关闭 。 否则，让它继续运行以便在下一个练习中使用。
