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
description: Командлет Set-CcSiteDirectory задает каталог, в котором будут храниться файлы конфигурации уровня сайта для Skype для бизнеса Cloud Connector Edition. В папке будут находиться файлы конфигурации базового виртуального жесткого диска и Cloud Connector.
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824193"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="a29ba-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="a29ba-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="a29ba-105">Командлет Set-CcSiteDirectory задает каталог, в котором будут храниться файлы конфигурации уровня сайта для Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="a29ba-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="a29ba-106">В папке будут находиться файлы конфигурации базового виртуального жесткого диска и Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a29ba-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="a29ba-107">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="a29ba-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="a29ba-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="a29ba-108">Examples</span></span>
<span data-ttu-id="a29ba-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a29ba-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="a29ba-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="a29ba-110">Example 1</span></span>

<span data-ttu-id="a29ba-111">В следующем примере для корневого каталога сайта задается значение \\ситешаре\клаудконнектор:</span><span class="sxs-lookup"><span data-stu-id="a29ba-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="a29ba-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="a29ba-112">Detailed Description</span></span>
<span data-ttu-id="a29ba-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a29ba-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="a29ba-114">Для обеспечения соответствия шлюза и высокой доступности устройства облачного соединителя можно объединять на сайтах.</span><span class="sxs-lookup"><span data-stu-id="a29ba-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="a29ba-115">Пользователи назначаются на сайты, а не в облачных устройствах-соединителях.</span><span class="sxs-lookup"><span data-stu-id="a29ba-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="a29ba-116">На каждом сайте есть общая папка, в которой хранятся базовые установочные файлы VHD и Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a29ba-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="a29ba-117">Устройства используют эту папку во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="a29ba-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="a29ba-118">Эта папка должна быть предоставлена всем другим устройствам на сайте облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="a29ba-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="a29ba-119">По умолчанию используется папка\%к:\усерс усерпрофиле%\клаудконнектор\ситерут.</span><span class="sxs-lookup"><span data-stu-id="a29ba-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="a29ba-120">Путь можно просмотреть с помощью командлета Get-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="a29ba-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="a29ba-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="a29ba-121">Parameters</span></span>
<span data-ttu-id="a29ba-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a29ba-122"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="a29ba-123">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="a29ba-123">**Parameter**</span></span>|<span data-ttu-id="a29ba-124">**Обязательный**</span><span class="sxs-lookup"><span data-stu-id="a29ba-124">**Required**</span></span>|<span data-ttu-id="a29ba-125">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a29ba-125">**Type**</span></span>|<span data-ttu-id="a29ba-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a29ba-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="a29ba-127">Путь</span><span class="sxs-lookup"><span data-stu-id="a29ba-127">Path</span></span> <br/> | <span data-ttu-id="a29ba-128">Обязательно</span><span class="sxs-lookup"><span data-stu-id="a29ba-128">Required</span></span> <br/> | <span data-ttu-id="a29ba-129">System.String</span><span class="sxs-lookup"><span data-stu-id="a29ba-129">System.String</span></span> <br/> |<span data-ttu-id="a29ba-130">Путь к папке, в которой будут храниться файлы сайта облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="a29ba-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="a29ba-131">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="a29ba-131">Input Types</span></span>
<span data-ttu-id="a29ba-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a29ba-132"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="a29ba-133">Отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="a29ba-133">None.</span></span> <span data-ttu-id="a29ba-134">Командлет Set-CcSiteDirectory не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="a29ba-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a29ba-135">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="a29ba-135">Return Types</span></span>
<span data-ttu-id="a29ba-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a29ba-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="a29ba-137">Нет</span><span class="sxs-lookup"><span data-stu-id="a29ba-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a29ba-138">См. также</span><span class="sxs-lookup"><span data-stu-id="a29ba-138">See also</span></span>
<span data-ttu-id="a29ba-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a29ba-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="a29ba-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="a29ba-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

