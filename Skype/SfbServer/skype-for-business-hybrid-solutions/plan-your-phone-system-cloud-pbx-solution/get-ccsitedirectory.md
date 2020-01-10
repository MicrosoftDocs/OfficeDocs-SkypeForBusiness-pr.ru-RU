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
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Командлет Get-CcSiteDirectory показывает текущий каталог, в котором хранятся файлы конфигурации уровня сайта. В папке находятся файлы установки базового виртуального жесткого диска и Skype для бизнеса Cloud Connector Edition. Эта папка должна быть предоставлена всем другим устройствам на сайте облачного соединителя.
ms.openlocfilehash: 095776a680fbbcc8c43a8f99700b357175010b5a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003369"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="2c45b-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="2c45b-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="2c45b-106">Командлет Get-CcSiteDirectory показывает текущий каталог, в котором хранятся файлы конфигурации уровня сайта.</span><span class="sxs-lookup"><span data-stu-id="2c45b-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="2c45b-107">В папке находятся файлы установки базового виртуального жесткого диска и Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="2c45b-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="2c45b-108">Эта папка должна быть предоставлена всем другим устройствам на сайте облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="2c45b-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="2c45b-109">Этот командлет применяется к версии Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="2c45b-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="2c45b-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c45b-110">Parameters</span></span>

<span data-ttu-id="2c45b-111">Нет</span><span class="sxs-lookup"><span data-stu-id="2c45b-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="2c45b-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="2c45b-112">Examples</span></span>
<span data-ttu-id="2c45b-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2c45b-113"></span></span>

### <a name="example-1"></a><span data-ttu-id="2c45b-114">Пример 1</span><span class="sxs-lookup"><span data-stu-id="2c45b-114">Example 1</span></span>

<span data-ttu-id="2c45b-115">В следующем примере показана текущая папка, в которой хранятся файлы конфигурации и виртуальных машин в компонентах облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="2c45b-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="2c45b-116">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="2c45b-116">Detailed Description</span></span>
<span data-ttu-id="2c45b-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2c45b-117"></span></span>

<span data-ttu-id="2c45b-118">Для обеспечения соответствия шлюза и высокой доступности устройства облачного соединителя можно объединять на сайтах.</span><span class="sxs-lookup"><span data-stu-id="2c45b-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="2c45b-119">Пользователи назначаются на сайты, а не в облачных устройствах-соединителях.</span><span class="sxs-lookup"><span data-stu-id="2c45b-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="2c45b-120">На каждом сайте есть общая папка, в которой хранятся базовые установочные файлы VHD и Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="2c45b-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="2c45b-121">Устройства используют эту папку во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="2c45b-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="2c45b-122">По умолчанию используется папка\%к:\усерс усерпрофиле%\клаудконнектор\ситерут.</span><span class="sxs-lookup"><span data-stu-id="2c45b-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="2c45b-123">Путь можно изменить с помощью командлета Set-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="2c45b-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="2c45b-124">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="2c45b-124">Input Types</span></span>
<span data-ttu-id="2c45b-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2c45b-125"></span></span>

<span data-ttu-id="2c45b-p104">Отсутствуют. Командлет Get-CcSiteDirectory не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="2c45b-p104">None. The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2c45b-128">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="2c45b-128">Return Types</span></span>
<span data-ttu-id="2c45b-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2c45b-129"></span></span>

<span data-ttu-id="2c45b-130">Эта команда возвращает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="2c45b-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2c45b-131">См. также</span><span class="sxs-lookup"><span data-stu-id="2c45b-131">See also</span></span>
<span data-ttu-id="2c45b-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2c45b-132"></span></span>

[<span data-ttu-id="2c45b-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="2c45b-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

