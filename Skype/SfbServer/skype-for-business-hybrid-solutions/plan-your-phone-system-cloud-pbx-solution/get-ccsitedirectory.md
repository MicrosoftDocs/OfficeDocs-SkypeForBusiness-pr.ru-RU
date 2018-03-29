---
title: Get-CcSiteDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Командлет Get-CcSiteDirectory показывает текущий каталог, в котором хранятся файлы конфигурации уровня сайта. В папке находятся файлы установки базового виртуального жесткого диска и Skype для бизнеса Cloud Connector Edition. Эта папка должна быть общей с другими приложениями, соединитель облака сайта.
ms.openlocfilehash: e75e20a18960510bf75a8ca4cfc97ffd9daa894f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="fa439-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="fa439-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="fa439-106">Командлет Get-CcSiteDirectory показывает текущий каталог, в котором хранятся файлы конфигурации уровня сайта.</span><span class="sxs-lookup"><span data-stu-id="fa439-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="fa439-107">В папке находятся файлы установки базового виртуального жесткого диска и Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="fa439-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="fa439-108">Эта папка должна быть общей с другими приложениями, соединитель облака сайта.</span><span class="sxs-lookup"><span data-stu-id="fa439-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="fa439-109">Этот командлет применяется к версии Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="fa439-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="fa439-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="fa439-110">Parameters</span></span>

<span data-ttu-id="fa439-111">Нет</span><span class="sxs-lookup"><span data-stu-id="fa439-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="fa439-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="fa439-112">Examples</span></span>
<span data-ttu-id="fa439-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fa439-113"></span></span>

### <a name="example-1"></a><span data-ttu-id="fa439-114">Пример 1</span><span class="sxs-lookup"><span data-stu-id="fa439-114">Example 1</span></span>

<span data-ttu-id="fa439-115">В следующем примере показано текущую папку, где хранятся файлы конфигурации и виртуальных машин из облака соединитель компонентов:</span><span class="sxs-lookup"><span data-stu-id="fa439-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="fa439-116">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="fa439-116">Detailed Description</span></span>
<span data-ttu-id="fa439-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fa439-117"></span></span>

<span data-ttu-id="fa439-118">Чтобы обеспечить соответствие шлюза и высокой доступности, устройств для соединителя облаке могут быть объединены в сайты.</span><span class="sxs-lookup"><span data-stu-id="fa439-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="fa439-119">Пользователи назначаются сайтов вместо устройств для соединителя облака.</span><span class="sxs-lookup"><span data-stu-id="fa439-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="fa439-120">На каждом сайте есть общая папка, в которой хранятся файлы установки базового виртуального жесткого диска и Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="fa439-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="fa439-121">Эта папка используется устройства во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="fa439-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="fa439-122">Папка по умолчанию является C:\Users\%userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="fa439-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="fa439-123">Путь можно изменить с помощью командлета Set-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="fa439-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="fa439-124">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="fa439-124">Input Types</span></span>
<span data-ttu-id="fa439-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fa439-125"></span></span>

<span data-ttu-id="fa439-p104">Отсутствуют. Командлет Get-CcSiteDirectory не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="fa439-p104">None. The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="fa439-128">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="fa439-128">Return Types</span></span>
<span data-ttu-id="fa439-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fa439-129"></span></span>

<span data-ttu-id="fa439-130">Эта команда возвращает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="fa439-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fa439-131">См. также</span><span class="sxs-lookup"><span data-stu-id="fa439-131">See also</span></span>
<span data-ttu-id="fa439-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fa439-132"></span></span>

[<span data-ttu-id="fa439-133">SET-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="fa439-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

