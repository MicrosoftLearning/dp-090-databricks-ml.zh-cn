---
title: 联机托管说明
permalink: index.html
layout: home
ms.openlocfilehash: 8d795701e8cdc53c61c6df0d8ff245c0d8969940
ms.sourcegitcommit: e397eba14f6dd257b83e0584f42e459cfe84bfbd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "138100267"
---
# <a name="content-directory"></a>内容目录

下面列出了实验室练习。

## <a name="labs"></a>实验室

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %}
| 模块 | 实验室 |
| --- | --- | 
{% 表示实验室 % 中的活动}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} - {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
