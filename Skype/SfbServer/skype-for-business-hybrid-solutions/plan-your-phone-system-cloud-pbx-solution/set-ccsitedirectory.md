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
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Командлет Set-CcSiteDirectory задает каталог, в котором будут храниться файлы конфигурации уровня сайта для Skype для бизнеса Cloud Connector Edition. В папке будут находиться файлы конфигурации базового виртуального жесткого диска и Cloud Connector.
ms.openlocfilehash: d2627da8bcd2cae5e388571457f4d6d9eb6813c9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286966"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="2b0b4-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="2b0b4-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="2b0b4-105">Командлет Set-CcSiteDirectory задает каталог, в котором будут храниться файлы конфигурации уровня сайта для Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="2b0b4-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="2b0b4-106">В папке будут находиться файлы конфигурации базового виртуального жесткого диска и Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="2b0b4-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="2b0b4-107">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="2b0b4-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="2b0b4-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="2b0b4-108">Examples</span></span>
<span data-ttu-id="2b0b4-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2b0b4-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="2b0b4-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="2b0b4-110">Example 1</span></span>

<span data-ttu-id="2b0b4-111">В следующем примере для корневого каталога сайта задается значение \\ситешаре\клаудконнектор:</span><span class="sxs-lookup"><span data-stu-id="2b0b4-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="2b0b4-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="2b0b4-112">Detailed Description</span></span>
<span data-ttu-id="2b0b4-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2b0b4-113"></span></span>

<span data-ttu-id="2b0b4-114">Для обеспечения соответствия шлюза и высокой доступности устройства облачного соединителя можно объединять на сайтах.</span><span class="sxs-lookup"><span data-stu-id="2b0b4-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="2b0b4-115">Пользователи назначаются на сайты, а не в облачных устройствах-соединителях.</span><span class="sxs-lookup"><span data-stu-id="2b0b4-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="2b0b4-116">На каждом сайте есть общая папка, в которой хранятся базовые установочные файлы VHD и Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="2b0b4-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="2b0b4-117">Устройства используют эту папку во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="2b0b4-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="2b0b4-118">Эта папка должна быть предоставлена всем другим устройствам на сайте облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="2b0b4-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="2b0b4-119">По умолчанию используется папка\%к:\усерс усерпрофиле%\клаудконнектор\ситерут.</span><span class="sxs-lookup"><span data-stu-id="2b0b4-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="2b0b4-120">Путь можно просмотреть с помощью командлета Get-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="2b0b4-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="2b0b4-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="2b0b4-121">Parameters</span></span>
<span data-ttu-id="2b0b4-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2b0b4-122"></span></span>

|<span data-ttu-id="2b0b4-123">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="2b0b4-123">**Parameter**</span></span>|<span data-ttu-id="2b0b4-124">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="2b0b4-124">**Required**</span></span>|<span data-ttu-id="2b0b4-125">**Тип**</span><span class="sxs-lookup"><span data-stu-id="2b0b4-125">**Type**</span></span>|<span data-ttu-id="2b0b4-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2b0b4-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2b0b4-127">Путь</span><span class="sxs-lookup"><span data-stu-id="2b0b4-127">Path</span></span> <br/> | <span data-ttu-id="2b0b4-128">Обязательно</span><span class="sxs-lookup"><span data-stu-id="2b0b4-128">Required</span></span> <br/> | <span data-ttu-id="2b0b4-129">System.String</span><span class="sxs-lookup"><span data-stu-id="2b0b4-129">System.String</span></span> <br/> |<span data-ttu-id="2b0b4-130">Путь к папке, в которой будут храниться файлы сайта облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="2b0b4-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="2b0b4-131">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="2b0b4-131">Input Types</span></span>
<span data-ttu-id="2b0b4-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2b0b4-132"></span></span>

<span data-ttu-id="2b0b4-133">Отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="2b0b4-133">None.</span></span> <span data-ttu-id="2b0b4-134">Командлет Set-CcSiteDirectory не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="2b0b4-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2b0b4-135">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="2b0b4-135">Return Types</span></span>
<span data-ttu-id="2b0b4-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2b0b4-136"></span></span>

<span data-ttu-id="2b0b4-137">Нет</span><span class="sxs-lookup"><span data-stu-id="2b0b4-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2b0b4-138">См. также</span><span class="sxs-lookup"><span data-stu-id="2b0b4-138">See also</span></span>
<span data-ttu-id="2b0b4-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2b0b4-139"></span></span>

[<span data-ttu-id="2b0b4-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="2b0b4-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

