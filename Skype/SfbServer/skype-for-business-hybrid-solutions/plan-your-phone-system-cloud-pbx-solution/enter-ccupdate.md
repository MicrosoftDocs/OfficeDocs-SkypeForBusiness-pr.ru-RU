---
title: Введите CcUpdate
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Командлет Enter-CcUpdate подготавливает сервер узла Skype для бизнеса Cloud Connector Edition к процессу обновления, переводя его в режим обслуживания. Isdrained устройство, то есть все существующие звонки по выполнению, но новые звонки, отклоняются.
ms.openlocfilehash: ed9f3f614829cd5b6bc2cd5499c6889258d67531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="enter-ccupdate"></a><span data-ttu-id="9ce47-104">Введите CcUpdate</span><span class="sxs-lookup"><span data-stu-id="9ce47-104">Enter-CcUpdate</span></span>
 
<span data-ttu-id="9ce47-105">Командлет Enter-CcUpdate подготавливает сервер узла Skype для бизнеса Cloud Connector Edition к процессу обновления, переводя его в режим обслуживания.</span><span class="sxs-lookup"><span data-stu-id="9ce47-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="9ce47-106">Устройства «опустошены» — то есть, все существующие звонки по выполнению, но новые звонки, отклоняются.</span><span class="sxs-lookup"><span data-stu-id="9ce47-106">The appliance is "drained"—that is, all existing calls will complete, but new calls are rejected.</span></span> 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="9ce47-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="9ce47-107">Parameters</span></span>

<span data-ttu-id="9ce47-108">Нет</span><span class="sxs-lookup"><span data-stu-id="9ce47-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="9ce47-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="9ce47-109">Examples</span></span>
<span data-ttu-id="9ce47-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9ce47-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="9ce47-111">Пример 1</span><span class="sxs-lookup"><span data-stu-id="9ce47-111">Example 1</span></span>

<span data-ttu-id="9ce47-112">В следующем примере устройство переводится в режим обслуживания для подготовки к процессу обновления:</span><span class="sxs-lookup"><span data-stu-id="9ce47-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="9ce47-113">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="9ce47-113">Detailed Description</span></span>
<span data-ttu-id="9ce47-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9ce47-114"></span></span>

<span data-ttu-id="9ce47-115">Командлет ввод CcUpdate гарантирует, что все звонки работает на устройстве облачных соединитель будет завершен, но устройство будет отклонять все новые вызовы, которые переносятся в других устройств для производственной.</span><span class="sxs-lookup"><span data-stu-id="9ce47-115">The Enter-CcUpdate cmdlet will ensure that all running calls on a Cloud Connector appliance will complete, but the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="9ce47-116">Таким образом, этот командлет позволяет обновить устройство, не препятствуя совершению звонков конечными пользователями.</span><span class="sxs-lookup"><span data-stu-id="9ce47-116">This cmdlet enables you to update an appliance without affecting end users calls.</span></span> <span data-ttu-id="9ce47-117">Необходимо убедиться, что производительности оставшихся рабочих устройств хватит, чтобы обработать все звонки с устройства, которое вы готовите к обновлению.</span><span class="sxs-lookup"><span data-stu-id="9ce47-117">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="9ce47-p104">Режим обслуживание полезен в тех случаях, когда на вашем устройстве включено автоматическое обновление и, например, очередной выпуск компонентов Майкрософт содержит критически важные исправления. Кроме того, режим обслуживания применяется в тех случаях, когда вы отключаете автоматическое обновление, но продолжаете регулярно выполнять обновления вручную.</span><span class="sxs-lookup"><span data-stu-id="9ce47-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="9ce47-120">После установки обновлений устройство можно снова перевести в рабочий режим, выполнив командлет Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="9ce47-120">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9ce47-121">Если вы решите вручную обновите appliance облачных соединителя, необходимо обновить в течение 60 дней после следующей версии выпускаемых корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9ce47-121">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="9ce47-122">Майкрософт поддерживает ранее версии облачных соединителя на 60 дней после выпуска новой версии</span><span class="sxs-lookup"><span data-stu-id="9ce47-122">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="9ce47-123">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="9ce47-123">Input Types</span></span>
<span data-ttu-id="9ce47-124"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9ce47-124"></span></span>

<span data-ttu-id="9ce47-p106">Нет. Командлет Enter-CCUpdate не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="9ce47-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9ce47-127">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="9ce47-127">Return Types</span></span>
<span data-ttu-id="9ce47-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9ce47-128"></span></span>

<span data-ttu-id="9ce47-129">Нет</span><span class="sxs-lookup"><span data-stu-id="9ce47-129">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9ce47-130">См. также</span><span class="sxs-lookup"><span data-stu-id="9ce47-130">See also</span></span>
<span data-ttu-id="9ce47-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9ce47-131"></span></span>

[<span data-ttu-id="9ce47-132">Выход CcUpdate</span><span class="sxs-lookup"><span data-stu-id="9ce47-132">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

