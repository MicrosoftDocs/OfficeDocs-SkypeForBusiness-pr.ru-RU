---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Этот Set-CcSiteDirectory задает каталог, в котором будут храниться файлы конфигурации уровня сайта для Skype для бизнеса Cloud Connector Edition. В папке будут содержаться файлы конфигурации базового VHD и Cloud Connector.
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824193"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="c83e2-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="c83e2-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="c83e2-105">Этот Set-CcSiteDirectory задает каталог, в котором будут храниться файлы конфигурации уровня сайта для Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="c83e2-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="c83e2-106">В папке будут содержаться файлы конфигурации базового VHD и Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c83e2-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="c83e2-107">Этот cmdlet применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="c83e2-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="c83e2-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="c83e2-108">Examples</span></span>
<span data-ttu-id="c83e2-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c83e2-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="c83e2-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="c83e2-110">Example 1</span></span>

<span data-ttu-id="c83e2-111">В следующем примере для корневого каталога сайта устанавливается \\ siteShare\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="c83e2-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="c83e2-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="c83e2-112">Detailed Description</span></span>
<span data-ttu-id="c83e2-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c83e2-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="c83e2-114">Чтобы обеспечить сходство шлюзов и высокую доступность, устройства Cloud Connector можно объединить на сайтах.</span><span class="sxs-lookup"><span data-stu-id="c83e2-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="c83e2-115">Пользователи назначены сайтам, а не устройствам Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c83e2-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="c83e2-116">Каждый сайт имеет общую папку, в которой хранятся файлы установки базового VHD и Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c83e2-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="c83e2-117">Устройства используют эту папку во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="c83e2-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="c83e2-118">Эта папка должна совместно работать со всеми другими устройствами на сайте Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c83e2-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="c83e2-119">Папка по умолчанию C:\Users \% userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="c83e2-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="c83e2-120">Путь можно просмотреть с помощью Get-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="c83e2-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="c83e2-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="c83e2-121">Parameters</span></span>
<span data-ttu-id="c83e2-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c83e2-122"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="c83e2-123">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="c83e2-123">**Parameter**</span></span>|<span data-ttu-id="c83e2-124">**Required**</span><span class="sxs-lookup"><span data-stu-id="c83e2-124">**Required**</span></span>|<span data-ttu-id="c83e2-125">**Тип**</span><span class="sxs-lookup"><span data-stu-id="c83e2-125">**Type**</span></span>|<span data-ttu-id="c83e2-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c83e2-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c83e2-127">Path</span><span class="sxs-lookup"><span data-stu-id="c83e2-127">Path</span></span> <br/> | <span data-ttu-id="c83e2-128">Обязательный</span><span class="sxs-lookup"><span data-stu-id="c83e2-128">Required</span></span> <br/> | <span data-ttu-id="c83e2-129">System.String</span><span class="sxs-lookup"><span data-stu-id="c83e2-129">System.String</span></span> <br/> |<span data-ttu-id="c83e2-130">Предоставляет путь к папке, в которой будут храниться файлы сайта Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c83e2-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="c83e2-131">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="c83e2-131">Input Types</span></span>
<span data-ttu-id="c83e2-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c83e2-132"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="c83e2-133">Нет.</span><span class="sxs-lookup"><span data-stu-id="c83e2-133">None.</span></span> <span data-ttu-id="c83e2-134">Этот Set-CcSiteDirectory не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="c83e2-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c83e2-135">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="c83e2-135">Return Types</span></span>
<span data-ttu-id="c83e2-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c83e2-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="c83e2-137">Нет</span><span class="sxs-lookup"><span data-stu-id="c83e2-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c83e2-138">См. также</span><span class="sxs-lookup"><span data-stu-id="c83e2-138">See also</span></span>
<span data-ttu-id="c83e2-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c83e2-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="c83e2-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="c83e2-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

