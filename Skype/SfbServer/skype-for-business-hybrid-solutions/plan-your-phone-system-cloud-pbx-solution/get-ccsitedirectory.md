---
title: Get-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Этот Get-CcSiteDirectory показывает текущий каталог, в котором хранятся файлы конфигурации на уровне сайта. Папка содержит базовые файлы установки VHD и Skype для бизнеса Cloud Connector Edition. Эта папка должна совместно работать со всеми другими устройствами сайта Cloud Connector.
ms.openlocfilehash: 6722b66f6c71feec158adaf442f9e57ef9943c84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799869"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="4ca55-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="4ca55-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="4ca55-106">Этот Get-CcSiteDirectory показывает текущий каталог, в котором хранятся файлы конфигурации на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="4ca55-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="4ca55-107">Папка содержит базовые файлы установки VHD и Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="4ca55-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="4ca55-108">Эта папка должна совместно работать со всеми другими устройствами сайта Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4ca55-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="4ca55-109">Этот cmdlet применяется к Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="4ca55-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="4ca55-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="4ca55-110">Parameters</span></span>

<span data-ttu-id="4ca55-111">Нет</span><span class="sxs-lookup"><span data-stu-id="4ca55-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="4ca55-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="4ca55-112">Examples</span></span>
<span data-ttu-id="4ca55-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4ca55-113"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="4ca55-114">Пример 1</span><span class="sxs-lookup"><span data-stu-id="4ca55-114">Example 1</span></span>

<span data-ttu-id="4ca55-115">В следующем примере показана текущая папка, в которой хранятся файлы конфигурации и виртуальных машин компонентов Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="4ca55-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="4ca55-116">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="4ca55-116">Detailed Description</span></span>
<span data-ttu-id="4ca55-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4ca55-117"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="4ca55-118">Чтобы обеспечить сходство шлюзов и высокую доступность, устройства Cloud Connector можно объединить на сайтах.</span><span class="sxs-lookup"><span data-stu-id="4ca55-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="4ca55-119">Пользователи назначены сайтам, а не устройствам Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4ca55-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="4ca55-120">Каждый сайт имеет общую папку, в которой хранятся файлы установки базового VHD и Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4ca55-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="4ca55-121">Устройства используют эту папку во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="4ca55-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="4ca55-122">Папка по умолчанию C:\Users \% userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="4ca55-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="4ca55-123">Путь можно изменить с помощью Set-CcSiteDirectory управления.</span><span class="sxs-lookup"><span data-stu-id="4ca55-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="4ca55-124">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="4ca55-124">Input Types</span></span>
<span data-ttu-id="4ca55-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4ca55-125"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="4ca55-126">Нет.</span><span class="sxs-lookup"><span data-stu-id="4ca55-126">None.</span></span> <span data-ttu-id="4ca55-127">Этот Get-CcSiteDirectory не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="4ca55-127">The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4ca55-128">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="4ca55-128">Return Types</span></span>
<span data-ttu-id="4ca55-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4ca55-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="4ca55-130">Эта команда возвращает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="4ca55-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4ca55-131">См. также</span><span class="sxs-lookup"><span data-stu-id="4ca55-131">See also</span></span>
<span data-ttu-id="4ca55-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4ca55-132"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="4ca55-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="4ca55-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

