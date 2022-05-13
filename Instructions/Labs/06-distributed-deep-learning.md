---
lab:
  title: Azure Databricks 分布式深度学习
  module: Optional exercise
ms.openlocfilehash: aa5c957a37af811c4ae34da317ace00b6ed235ce
ms.sourcegitcommit: e397eba14f6dd257b83e0584f42e459cfe84bfbd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "138100279"
---
# <a name="set-up-for-distributed-deep-learning"></a>分布式深度学习的设置

首先，你需要使用交互式标准群集访问 Azure Databricks 工作区。 如果没有工作区和/或所需的群集，请按照下面的说明操作。

## <a name="create-azure-databricks-resources"></a>创建 Azure Databricks 资源

若要使用 Azure Databricks，首先需要在 Azure 订阅中部署 Azure Databricks 工作区，并创建运行笔记本和代码的群集。 然后，可以上传数据和笔记本以在工作区中进行试验。

### <a name="deploy-an-azure-databricks-workspace"></a>部署 Azure Databricks 工作区

1. 在 [Azure 门户](https://portal.azure.com)中，创建新的 Azure Databricks 资源，并指定以下设置：
   - 订阅：选择要在其中部署工作区的 Azure 订阅。
   - **资源组**：创建新的资源组。
   - 工作区名称：提供工作区的名称。
   - 区域：选择你附近的位置进行部署。 *[有关 Azure Databricks 支持的区域列表，请参阅](https://azure.microsoft.com/regions/services/)各区域的 Azure 服务可用性*。
   - **定价层**：标准

1. 等待工作区创建完毕。 创建工作区需要几分钟时间。 在创建工作区过程中，门户会在右侧显示“正在提交 Azure Databricks 的部署”  磁贴。 可能需要在仪表板上向右滚动才能看到此磁贴。 另外，还会在屏幕顶部附近显示进度条。 你可以查看任一区域来了解进度。

### <a name="create-a-cluster"></a>创建群集

1. 创建 Azure Databricks 工作区资源后，请在门户中转到该资源，然后选择“启动工作区”以在新选项卡中打开 Databricks 工作区，并在出现提示时登录。

1. 在 Databricks 工作区的左侧菜单中，选择“计算”，然后选择“+ 创建群集”以使用以下配置添加新群集 ：
   - **名称**：输入唯一名称。
   - **群集模式**：标准
   - 池：无
   - **Databricks Runtime 版本**：选择运行时最新可用版本的 ML 版本。确保已选择版本：
      - CPU 和 GPU 群集都可用于本练习。CPU 的测试成本将低于 GPU。
      - 包括 Scala > 2.11
      - 包括 Spark > 3.0
   - 终止时间：120 分钟不活动
   - 节点类型：Standard_DS3_v2

1. 等待创建群集，可能需要几分钟时间。 群集将自动启动，最终群集名称旁边的旋转“挂起”指示器将更改为绿色实心圆圈，以指示“正在运行”状态 。

### <a name="import-databricks-notebooks"></a>导入 Databricks 笔记本

1. 在 Azure Databricks 工作区中，使用左侧的命令栏，选择“工作区”。 然后选择“用户”，和 **&#9751; *your_user_name***。

1. 在显示的边栏选项卡中，选择名称旁边的向下指向 V 形符号 (v)，然后选择“导入” 。

1. 在“导入笔记本”对话框中，从以下 URL 导入笔记本存档，注意已创建一个具有存档名称的文件夹，其中包含两个笔记本：
   - `https://github.com/MicrosoftLearning/dp-090-databricks-ml/blob/master/06%20-%20Distributed%20Deep%20Learning.dbc`

## <a name="explore-distributed-deep-learning"></a>了解分布式深度学习

在本练习中，你将了解如何使用自动化 MLflow 进行超参数优化。

1. 在工作区的“06 - 分布式深度学习”文件夹中，打开“1.0 分布式深度学习”笔记本 。

1. 在左上角下拉菜单中，选择群集以将笔记本附加到该群集。 （或者，在未附加的笔记本中运行第一个单元时，系统将提示你附加群集）。

1. 阅读笔记本中的笔记，依次运行每个代码单元。

## <a name="clean-up"></a>清理

如果现在已完成使用 Azure Databricks，请在 Azure Databricks 工作区的“计算”页上，选择你的群集，然后选择“&#9632; 终止”将其关闭 。 否则，让它继续运行以便在下一个练习中使用。
