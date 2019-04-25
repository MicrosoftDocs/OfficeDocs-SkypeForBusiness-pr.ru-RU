---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Командлет ввод CcUpdate подготавливает Скайп для соединителя Cloud Business Edition хост-сервера для процесса обновления, поместив его в режиме обслуживания. Isdrained устройство, то есть все существующие звонки по выполнению, но новые звонки, отклоняются.
ms.openlocfilehash: 45972058cd9263330b6a4c0a68a5a1b800a85d9d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234065"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="aea74-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="aea74-104">Enter-CcUpdate</span></span>
 
<span data-ttu-id="aea74-105">Командлет ввод CcUpdate подготавливает Скайп для соединителя Cloud Business Edition хост-сервера для процесса обновления, поместив его в режиме обслуживания.</span><span class="sxs-lookup"><span data-stu-id="aea74-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="aea74-106">Устройства «опустошены» — то есть, все существующие звонки по выполнению, но новые звонки, отклоняются.</span><span class="sxs-lookup"><span data-stu-id="aea74-106">The appliance is "drained"—that is, all existing calls will complete, but new calls are rejected.</span></span> 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="aea74-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="aea74-107">Parameters</span></span>

<span data-ttu-id="aea74-108">Нет</span><span class="sxs-lookup"><span data-stu-id="aea74-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="aea74-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="aea74-109">Examples</span></span>
<span data-ttu-id="aea74-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="aea74-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="aea74-111">Пример 1</span><span class="sxs-lookup"><span data-stu-id="aea74-111">Example 1</span></span>

<span data-ttu-id="aea74-112">В следующем примере устройство переводится в режим обслуживания для подготовки к процессу обновления:</span><span class="sxs-lookup"><span data-stu-id="aea74-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="aea74-113">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="aea74-113">Detailed Description</span></span>
<span data-ttu-id="aea74-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="aea74-114"></span></span>

<span data-ttu-id="aea74-115">Командлет CcUpdate ввод сразу же будет остановите все службы, к концу все текущие вызовы и устройство будет отклонять все новые вызовы, которые переносятся в других устройств для производственной.</span><span class="sxs-lookup"><span data-stu-id="aea74-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="aea74-116">Необходимо убедиться, что остальные appliances рабочей имеют достаточную емкость для обработки звонков из устройства, Подготовка к обновлению.</span><span class="sxs-lookup"><span data-stu-id="aea74-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="aea74-p104">Режим обслуживание полезен в тех случаях, когда на вашем устройстве включено автоматическое обновление и, например, очередной выпуск компонентов Майкрософт содержит критически важные исправления. Кроме того, режим обслуживания применяется в тех случаях, когда вы отключаете автоматическое обновление, но продолжаете регулярно выполнять обновления вручную.</span><span class="sxs-lookup"><span data-stu-id="aea74-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="aea74-119">После установки обновлений, устройство может быть переведен обратно в рабочий режим, выполнив командлет CcUpdate выход.</span><span class="sxs-lookup"><span data-stu-id="aea74-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aea74-120">Если вы решите вручную обновите appliance облачных соединителя, необходимо обновить в течение 60 дней после следующей версии выпускаемых корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="aea74-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="aea74-121">Майкрософт поддерживает ранее версии облачных соединителя на 60 дней после выпуска новой версии</span><span class="sxs-lookup"><span data-stu-id="aea74-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="aea74-122">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="aea74-122">Input Types</span></span>
<span data-ttu-id="aea74-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="aea74-123"></span></span>

<span data-ttu-id="aea74-p106">Нет. Командлет Enter-CCUpdate не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="aea74-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="aea74-126">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="aea74-126">Return Types</span></span>
<span data-ttu-id="aea74-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="aea74-127"></span></span>

<span data-ttu-id="aea74-128">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="aea74-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="aea74-129">См. также</span><span class="sxs-lookup"><span data-stu-id="aea74-129">See also</span></span>
<span data-ttu-id="aea74-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="aea74-130"></span></span>

[<span data-ttu-id="aea74-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="aea74-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

