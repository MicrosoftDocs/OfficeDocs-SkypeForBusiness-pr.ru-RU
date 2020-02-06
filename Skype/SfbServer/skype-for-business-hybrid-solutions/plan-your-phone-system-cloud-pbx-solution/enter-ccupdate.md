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
description: Командлет Enter-Ккупдате подготавливает сервер узла Skype для бизнеса Cloud Connector для процесса обновления, переводя его в режим обслуживания. Управляющее устройство немедленно останавливает все службы, заканчивая всеми текущими звонками и отклоняет любые новые звонки.
ms.openlocfilehash: 25d2fbc56bd4de6a08985de18c178d5a8f993492
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802179"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="6a3c1-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="6a3c1-104">Enter-CcUpdate</span></span>

<span data-ttu-id="6a3c1-105">Командлет Enter-Ккупдате подготавливает сервер узла Skype для бизнеса Cloud Connector для процесса обновления, переводя его в режим обслуживания.</span><span class="sxs-lookup"><span data-stu-id="6a3c1-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="6a3c1-106">Управляющее устройство немедленно останавливает все службы, заканчивая всеми текущими звонками и отклоняет любые новые звонки.</span><span class="sxs-lookup"><span data-stu-id="6a3c1-106">The appliance immediately stops all services, ending any ongoing calls and rejecting any new calls.</span></span>
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="6a3c1-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="6a3c1-107">Parameters</span></span>

<span data-ttu-id="6a3c1-108">Нет</span><span class="sxs-lookup"><span data-stu-id="6a3c1-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="6a3c1-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="6a3c1-109">Examples</span></span>
<span data-ttu-id="6a3c1-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6a3c1-110"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="6a3c1-111">Пример 1</span><span class="sxs-lookup"><span data-stu-id="6a3c1-111">Example 1</span></span>

<span data-ttu-id="6a3c1-112">В следующем примере устройство переводится в режим обслуживания для подготовки к процессу обновления:</span><span class="sxs-lookup"><span data-stu-id="6a3c1-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="6a3c1-113">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="6a3c1-113">Detailed Description</span></span>
<span data-ttu-id="6a3c1-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="6a3c1-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="6a3c1-115">Командлет Enter-Ккупдате сразу же останавливает все службы, завершающие все выполняемые звонки, и устройство будет отклонять любые новые звонки, которые передаются другим производственным устройствам.</span><span class="sxs-lookup"><span data-stu-id="6a3c1-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="6a3c1-116">Необходимо убедиться в том, что у остальных производственных приборов достаточно свободного места для обработки звонков с устройства, которое вы готовитесь обновлять.</span><span class="sxs-lookup"><span data-stu-id="6a3c1-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="6a3c1-p104">Режим обслуживание полезен в тех случаях, когда на вашем устройстве включено автоматическое обновление и, например, очередной выпуск компонентов Майкрософт содержит критически важные исправления. Кроме того, режим обслуживания применяется в тех случаях, когда вы отключаете автоматическое обновление, но продолжаете регулярно выполнять обновления вручную.</span><span class="sxs-lookup"><span data-stu-id="6a3c1-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="6a3c1-119">После установки обновлений устройство может быть возвращено в производственный режим, запустив командлет Exit-Ккупдате.</span><span class="sxs-lookup"><span data-stu-id="6a3c1-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a3c1-120">Если вы решите вручную обновить устройство облачного соединителя, вам нужно обновить его в течение 60 дней после выпуска следующей версии Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6a3c1-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="6a3c1-121">Корпорация Майкрософт поддерживает ранее выпущенную версию облачного соединителя для 60 дней после выпуска новой версии</span><span class="sxs-lookup"><span data-stu-id="6a3c1-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="6a3c1-122">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="6a3c1-122">Input Types</span></span>
<span data-ttu-id="6a3c1-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6a3c1-123"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="6a3c1-p106">Нет. Командлет Enter-CCUpdate не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="6a3c1-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6a3c1-126">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="6a3c1-126">Return Types</span></span>
<span data-ttu-id="6a3c1-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6a3c1-127"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="6a3c1-128">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="6a3c1-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6a3c1-129">См. также</span><span class="sxs-lookup"><span data-stu-id="6a3c1-129">See also</span></span>
<span data-ttu-id="6a3c1-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6a3c1-130"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="6a3c1-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="6a3c1-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

