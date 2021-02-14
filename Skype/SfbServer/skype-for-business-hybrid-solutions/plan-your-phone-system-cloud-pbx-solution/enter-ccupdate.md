---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode. Устройство немедленно останавливает все службы, завершая все текущие вызовы и отклоняет все новые вызовы.
ms.openlocfilehash: 25d2fbc56bd4de6a08985de18c178d5a8f993492
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802179"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="1abc1-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="1abc1-104">Enter-CcUpdate</span></span>

<span data-ttu-id="1abc1-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span><span class="sxs-lookup"><span data-stu-id="1abc1-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="1abc1-106">Устройство немедленно останавливает все службы, завершая все текущие вызовы и отклоняет все новые вызовы.</span><span class="sxs-lookup"><span data-stu-id="1abc1-106">The appliance immediately stops all services, ending any ongoing calls and rejecting any new calls.</span></span>
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="1abc1-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="1abc1-107">Parameters</span></span>

<span data-ttu-id="1abc1-108">Нет</span><span class="sxs-lookup"><span data-stu-id="1abc1-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="1abc1-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="1abc1-109">Examples</span></span>
<span data-ttu-id="1abc1-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1abc1-110"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="1abc1-111">Пример 1</span><span class="sxs-lookup"><span data-stu-id="1abc1-111">Example 1</span></span>

<span data-ttu-id="1abc1-112">В следующем примере устройство подготавливается к процессу обновления, перейдя в режим обслуживания:</span><span class="sxs-lookup"><span data-stu-id="1abc1-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="1abc1-113">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="1abc1-113">Detailed Description</span></span>
<span data-ttu-id="1abc1-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1abc1-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="1abc1-115">Этот Enter-CcUpdate немедленно остановит все службы, завершив все текущие вызовы, и устройство отклоняет все новые вызовы, которые передаются на другие производственные устройства.</span><span class="sxs-lookup"><span data-stu-id="1abc1-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="1abc1-116">Необходимо убедиться, что на остальных производственных устройствах достаточно емкости для обработки вызовов с устройства, которое вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="1abc1-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="1abc1-117">Режим обслуживания полезен, если на вашем устройстве включено автоматическое обновление, например, и Корпорация Майкрософт выпускает критическое обновление.</span><span class="sxs-lookup"><span data-stu-id="1abc1-117">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix.</span></span> <span data-ttu-id="1abc1-118">Режим обслуживания также полезен, если вы решили отключить автоматические обновления, но вы выполняете обновления вручную на согласованной основе.</span><span class="sxs-lookup"><span data-stu-id="1abc1-118">Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="1abc1-119">После установки обновлений устройство можно вернуть в производственный режим с помощью Exit-CcUpdate управления.</span><span class="sxs-lookup"><span data-stu-id="1abc1-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1abc1-120">Если вы решили вручную обновить устройство Cloud Connector, вам потребуется обновить его в течение 60 дней после того, как корпорация Майкрософт выпустит следующую версию.</span><span class="sxs-lookup"><span data-stu-id="1abc1-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="1abc1-121">Корпорация Майкрософт поддерживает ранее выпущенную версию Cloud Connector в течение 60 дней после выпуска новой версии</span><span class="sxs-lookup"><span data-stu-id="1abc1-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="1abc1-122">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="1abc1-122">Input Types</span></span>
<span data-ttu-id="1abc1-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1abc1-123"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="1abc1-124">Нет.</span><span class="sxs-lookup"><span data-stu-id="1abc1-124">None.</span></span> <span data-ttu-id="1abc1-125">Этот Enter-CCUpdate не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="1abc1-125">The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1abc1-126">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="1abc1-126">Return Types</span></span>
<span data-ttu-id="1abc1-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1abc1-127"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="1abc1-128">Нет</span><span class="sxs-lookup"><span data-stu-id="1abc1-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1abc1-129">См. также</span><span class="sxs-lookup"><span data-stu-id="1abc1-129">See also</span></span>
<span data-ttu-id="1abc1-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1abc1-130"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="1abc1-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="1abc1-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

