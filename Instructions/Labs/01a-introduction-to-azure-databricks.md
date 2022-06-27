---
lab:
  title: 开始使用 Azure Databricks
  module: Module 1 - Introduction to Azure Databricks
ms.openlocfilehash: 3dace63ca6c25357be8d092ba74c31b493f7abef
ms.sourcegitcommit: 5015d3cb2e5dc2e5b15ad64d92029b6acd0f9435
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2022
ms.locfileid: "146541474"
---
# <a name="getting-started-with-azure-databricks"></a>开始使用 Azure Databricks

Azure Databricks 是基于 Spark 的快速、简单和协作分析服务。 它用于加速大数据分析、人工智能、高性能数据湖、交互式数据科学、机器学习和协作。
你将发现 Azure Databricks 环境以及围绕它的主要主题：工作区、群集、笔记本。

首先，你需要使用交互式群集访问 Azure Databricks 工作区。 如果没有工作区和/或所需的群集，请按照下面的说明操作。 否则，可以跳到下面的“上传数据”部分。

## <a name="create-azure-databricks-resources"></a>创建 Azure Databricks 资源

若要使用 Azure Databricks，首先需要在 Azure 订阅中部署 Azure Databricks 工作区，并创建运行笔记本和代码的群集。 然后，可以上传数据和笔记本以在工作区中进行试验。

### <a name="deploy-an-azure-databricks-workspace"></a>部署 Azure Databricks 工作区

1. 在 Azure 门户 (https://portal.azure.com ) 中，创建新的 Azure Databricks 资源，并指定以下设置：
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
   - **群集模式**：单节点
   - **Databricks Runtime 版本**：选择运行时最新可用版本的 ML 版本，而不是标准运行时版本。** 确保已选择 ML 版本：
      - 不使用 GPU
      - 包括 Scala > 2.11
      - 包括 Spark > 3.0
   - 终止时间：120 分钟不活动
   - 节点类型：Standard_DS3_v2

2. 选择“创建群集”。

1. 等待创建群集，可能需要几分钟时间。 群集将自动启动，最终群集名称旁边的旋转“挂起”指示器将更改为绿色实心圆圈，以指示“正在运行”状态 。

### <a name="upload-data"></a>上传数据

1. 将 `https://raw.githubusercontent.com/MicrosoftLearning/dp-090-databricks-ml/master/data/nyc-taxi.csv` 下载到计算机，并以 nyc-taxi.csv 名称保存到任何文件夹中。

1. 在 Databricks 工作区的“数据”页上，选择“创建表”选项 。

1. 在“文件”区域中，选择“浏览”，然后浏览到已下载的 nyc-taxi.csv 文件  。

1. 将文件上传到工作区后，选择“使用 UI 创建表”。 然后选择群集，并选择“预览表”。

1. 指定以下表属性：

    - 表名称：nyc_taxi
    - 在数据库中创建：默认值
    - **文件类型**：CSV
    - 列分隔符：,（逗号）
    - 第一行是标头：勾选
    - 推断架构：勾选
    - 多行：不勾选

1. 为每列设置适当的数据类型：找到 passengerCount 列。 在下拉菜单中，将列设置为 INT。

    - passengerCount：INT
    - tripDistance：DOUBLE
    - hour_of_day：INT
    - day_of_week：INT
    - month_num：INT
    - normalizeHolidayName：STRING
    - isPaidTimeOff：BOOLEAN
    - snowDepth：DOUBLE
    - precipTime：DOUBLE
    - precipDepth：DOUBLE
    - temperature:DOUBLE
    - totalAmount：DOUBLE

1. 单击“创建表”。

1. 创建表后，在工作区中查看它。

### <a name="import-databricks-notebooks"></a>导入 Databricks 笔记本

1. 在 Azure Databricks 工作区中，使用左侧的命令栏，选择“工作区”。 然后选择“用户”，和 **&#9751; *your_user_name***。

1. 在显示的边栏选项卡中，选择名称旁边的向下指向 V 形符号 (v)，然后选择“导入” 。

1. 在“导入笔记本”对话框中，从以下 URL 导入笔记本存档，注意已创建一个具有存档名称的文件夹，其中包含一个或多个笔记本：
   - `https://github.com/MicrosoftLearning/dp-090-databricks-ml/raw/master/01%20-%20Introduction%20to%20Azure%20Databricks.dbc`

1. 重复上一步以导入以下笔记本存档，请注意，在导入每个存档时会为每个存档创建一个文件夹。

   - `https://github.com/MicrosoftLearning/dp-090-databricks-ml/raw/master/02%20-%20Training%20and%20Evaluating%20Machine%20Learning%20Models.dbc`
   - `https://github.com/MicrosoftLearning/dp-090-databricks-ml/raw/master/03%20-%20Managing%20Experiments%20and%20Models.dbc`
   - `https://github.com/MicrosoftLearning/dp-090-databricks-ml/raw/master/04%20-%20Integrating%20Azure%20Databricks%20and%20Azure%20Machine%20Learning.dbc`

## <a name="explore-azure-databricks"></a>了解 Azure Databricks

在本练习中，你将发现 Azure Databricks 环境。

1. 在工作区的“01 - Azure Databricks 简介”文件夹中，打开“Azure Databricks 入门”笔记本 。

1. 在左上角下拉菜单中，选择群集以将笔记本附加到该群集。 （或者，在未附加的笔记本中运行第一个单元时，系统将提示你附加群集）。

1. 阅读笔记本中的笔记，依次运行每个代码单元。

## <a name="clean-up"></a>清理

如果现在已完成使用 Azure Databricks，请在 Azure Databricks 工作区的“计算”页上，选择你的群集，然后选择“&#9632; 终止”将其关闭 。 否则，让它继续运行以便你在下一个练习中使用。
