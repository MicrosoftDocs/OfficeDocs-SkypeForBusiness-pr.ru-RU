---
title: SET-CcSiteDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Командлет Set-CcSiteDirectory задает каталог, в котором будут храниться файлы конфигурации уровня сайта для Skype для бизнеса Cloud Connector Edition. В папке будут находиться файлы конфигурации базового виртуального жесткого диска и Cloud Connector.
ms.openlocfilehash: d34945a17f32c275240e2cef0435f6e0ca3e63a0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="53975-104">SET-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="53975-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="53975-105">Командлет Set-CcSiteDirectory задает каталог, в котором будут храниться файлы конфигурации уровня сайта для Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="53975-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="53975-106">В папке будут находиться файлы конфигурации базового виртуального жесткого диска и Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="53975-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="53975-107">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="53975-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="53975-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="53975-108">Examples</span></span>
<span data-ttu-id="53975-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="53975-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="53975-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="53975-110">Example 1</span></span>

<span data-ttu-id="53975-111">В следующем примере задается корневого каталога веб-сайтов \\SiteShare\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="53975-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="53975-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="53975-112">Detailed Description</span></span>
<span data-ttu-id="53975-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="53975-113"></span></span>

<span data-ttu-id="53975-114">Чтобы обеспечить соответствие шлюза и высокой доступности, устройств для соединителя облаке могут быть объединены в сайты.</span><span class="sxs-lookup"><span data-stu-id="53975-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="53975-115">Пользователи назначаются сайтов вместо устройств для соединителя облака.</span><span class="sxs-lookup"><span data-stu-id="53975-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="53975-116">На каждом сайте есть общая папка, в которой хранятся файлы установки базового виртуального жесткого диска и Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="53975-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="53975-117">Эта папка используется устройства во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="53975-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="53975-118">Эта папка должна быть общей с другими приложениями, в облаке соединителя сайта.</span><span class="sxs-lookup"><span data-stu-id="53975-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="53975-119">Папка по умолчанию является C:\Users\%userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="53975-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="53975-120">Путь можно просмотреть с помощью командлета Get-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="53975-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="53975-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="53975-121">Parameters</span></span>
<span data-ttu-id="53975-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="53975-122"></span></span>

|<span data-ttu-id="53975-123">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="53975-123">**Parameter**</span></span>|<span data-ttu-id="53975-124">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="53975-124">**Required**</span></span>|<span data-ttu-id="53975-125">**Тип**</span><span class="sxs-lookup"><span data-stu-id="53975-125">**Type**</span></span>|<span data-ttu-id="53975-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="53975-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="53975-127">Путь</span><span class="sxs-lookup"><span data-stu-id="53975-127">Path</span></span> <br/> | <span data-ttu-id="53975-128">Обязательно</span><span class="sxs-lookup"><span data-stu-id="53975-128">Required</span></span> <br/> | <span data-ttu-id="53975-129">System.String</span><span class="sxs-lookup"><span data-stu-id="53975-129">System.String</span></span> <br/> |<span data-ttu-id="53975-130">Содержит путь к папке, где будут храниться файлы соединителя облака сайта.</span><span class="sxs-lookup"><span data-stu-id="53975-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="53975-131">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="53975-131">Input Types</span></span>
<span data-ttu-id="53975-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="53975-132"></span></span>

<span data-ttu-id="53975-133">Отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="53975-133">None.</span></span> <span data-ttu-id="53975-134">Командлет Set-CcSiteDirectory не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="53975-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="53975-135">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="53975-135">Return Types</span></span>
<span data-ttu-id="53975-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="53975-136"></span></span>

<span data-ttu-id="53975-137">Нет</span><span class="sxs-lookup"><span data-stu-id="53975-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="53975-138">См. также</span><span class="sxs-lookup"><span data-stu-id="53975-138">See also</span></span>
<span data-ttu-id="53975-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="53975-139"></span></span>

[<span data-ttu-id="53975-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="53975-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

