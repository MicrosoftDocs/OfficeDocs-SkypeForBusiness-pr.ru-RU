---
title: Начало работы с шаблонами Teams для организаций здравоохранения
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Начало работы с шаблонами Teams для организаций здравоохранения
ms.openlocfilehash: e5116ecf2ab9fa0bbad25222e69317c47cf0c892
ms.sourcegitcommit: 8e62025d630c511ffb0361b9643d46c762188102
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2019
ms.locfileid: "30664702"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>Начало работы с шаблонами Teams для организаций здравоохранения

Шаблоны рабочих групп Майкрософт позволяют быстро и легко создавать группы, предоставляя готовый шаблон настроек, каналов и предварительно установленные приложения.

Для организаций, здравоохранения шаблоны может быть особенно широкими возможностями, как они обеспечивают структуру для пользователей станет ориентацию с тем, как наилучшим образом использовать группам эффективно. Шаблоны также дают администраторы могут развертывать согласованные группами в своей организации. Эта статья является для вас, кто отвечает за планирование, развертывание и управление нескольких групп внутри организации здравоохранения.

Мы в настоящее время предложение два первой стороны здравоохранения шаблоны, которые можно использовать в различных ситуациях. Для получения дополнительных сведений о группы шаблонов в общем случае можно найти [Начало работы с группами шаблонов](../get-started-with-teams-templates.md).

## <a name="ward-template"></a>Шаблон Ворд

Шаблон Ворд предназначен для обмена данными и совместной работы в рамках Ворд, модуль или отдела. Шаблон можно использовать для упрощения пациентов, а также требований Ворд. Например Ворд объявлений можно размещать в канала *объявлений* и смены может осуществляться в *набору сотрудников*. Если вас интересует оптимизацию Ворд операции, этот шаблон является для вас.

|Тип базового шаблона |Идентификатор базового шаблона |Каналы базового шаблона|
|:--- |:---|:---|
|Здравоохранение - Ворд | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Объявления\* <br> Huddles\* <br> Округляет\* <br> Набору кадров\* <br> Учебный курс по\* |
|     | |         |

\*Auto-favorited

## <a name="hospital-template"></a>Шаблон больница

Шаблон больница предназначен для обмена данными и совместной работы между несколькими wards, модулей и подразделений внутри больницы. Включены в этот шаблон нескольких каналов действующие в том числе *извещения*, *Custodial*и *лекарственной*, но также предоставляют скрипт ниже которого расширяет шаблон с различными дополнительные отдела или ориентированный на специальные каналы, которые можно добавить, удалить из или изменить по своему вкусу. К примеру имеют отделу *Endocrinology* , но нет необходимости канала для *Ophthalmology*, скрипта можно адаптировать включают канал *Endocrinology* и удаление канала *Ophthalmology* . Мы рекомендуем эти специальные или смоделировать Ворд каналы не использовать favorited автоматически, чтобы избежать перегрузки уведомлений. Пользователи обычно избранные любые каналы, что они важна.

|Тип базового шаблона |Идентификатор базового шаблона |Каналы базового шаблона|
|:--- |:---|:---|
|Здравоохранение - больница | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Объявления\* <br> Соответствие требованиям\* <br> Наказание <br> Отдел кадров <br> Лекарства |
| | |  |

\*Auto-favorited 

## <a name="how-to-use-first-party-templates"></a>Как использовать первой стороны шаблонов

Чтобы использовать эти шаблоны, просто измените свойство «template@odata.bind» в теле запроса из «стандартный» TemplateIDs выше.  Дополнительные сведения о том, как развертывать шаблоны группы, Microsoft Graph [статьи о создании группы](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

### <a name="example-hospital-template-extension-script"></a>Пример: Больница шаблона расширения сценариев

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women’s Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```
