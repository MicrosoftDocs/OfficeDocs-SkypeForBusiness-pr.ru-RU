---
title: Расширитель параметров регистратора
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: Устойчивость обеспечивает высокую доступность и восстановление после аварии для пула регистраторов. Предоставляя регистратор резервных копий в случае сбоя основного регистратора, он может пройти для регистратора, который входит в систему, чтобы он мог зарегистрироваться и обмениваться данными с другими пользователями. Пользователи могут столкнуться с ограниченными возможностями, в зависимости от того, какие системы завершились сбоем основного регистратора.
ms.openlocfilehash: c603310e6b99721aace04c4e596989fc394ef0ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819331"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="d2e7c-105">Расширитель параметров регистратора</span><span class="sxs-lookup"><span data-stu-id="d2e7c-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="d2e7c-106">Устойчивость обеспечивает высокую доступность и восстановление после аварии для пула регистраторов.</span><span class="sxs-lookup"><span data-stu-id="d2e7c-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="d2e7c-107">Предоставляя регистратор резервных копий в случае сбоя основного регистратора, он может пройти для регистратора, который входит в систему, чтобы он мог зарегистрироваться и обмениваться данными с другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="d2e7c-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="d2e7c-108">Пользователи могут столкнуться с ограниченными возможностями, в зависимости от того, какие системы завершились сбоем основного регистратора.</span><span class="sxs-lookup"><span data-stu-id="d2e7c-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="d2e7c-109">В разделе " **устойчивость** " диалогового окна " **изменение свойств** " для работающего устройства филиала или для бесперебойно работающего филиала вы можете изменить указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="d2e7c-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="d2e7c-110">**Сопоставленный пул регистраторов пользователей и резервных копий** В раскрывающемся списке выберите пул переднего плана Enterprise Edition или стандартный сервер переднего плана, который должен выступать в качестве регистратора резервных копий для работающего устройства филиала или для бесперебойной ветви сервера.</span><span class="sxs-lookup"><span data-stu-id="d2e7c-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="d2e7c-111">**Включение отработки отказа и восстановления размещения** Выберите этот параметр, чтобы разрешить автоматическое обнаружение сбойного регистратора и автоматическое определение того, что основной регистратор является резервным и готовым к возобновлению регистратора.</span><span class="sxs-lookup"><span data-stu-id="d2e7c-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="d2e7c-112">**Интервал обнаружения отказов (сек)** Введите количество секунд, которое должно пройти до того, как оно будет определяться сбоем основного регистратора.</span><span class="sxs-lookup"><span data-stu-id="d2e7c-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="d2e7c-113">Значение по умолчанию — 120 секунд.</span><span class="sxs-lookup"><span data-stu-id="d2e7c-113">The default value is 120 seconds.</span></span> <span data-ttu-id="d2e7c-114">Это поле является обязательным, если выбран параметр **включить перемещения при сбое и восстановление после сбоя**.</span><span class="sxs-lookup"><span data-stu-id="d2e7c-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="d2e7c-115">**Интервал обнаружения резервной стратегии (в секундах)** Введите количество секунд, которое должно пройти до того, как будет определено, что резервная копия основного регистратора.</span><span class="sxs-lookup"><span data-stu-id="d2e7c-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="d2e7c-116">Значение по умолчанию — 240 секунд.</span><span class="sxs-lookup"><span data-stu-id="d2e7c-116">The default value is 240 seconds.</span></span> <span data-ttu-id="d2e7c-117">Это поле является обязательным, если выбран параметр **включить отказоустойчивость и возврат**.</span><span class="sxs-lookup"><span data-stu-id="d2e7c-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="d2e7c-118">При определении интервала обнаружения отказов и интервала проверки резервной стратегии следует избегать ввода интервалов, которые приводят к возникновению сбоя и отката, если регистратор не отвечает на короткий период времени.</span><span class="sxs-lookup"><span data-stu-id="d2e7c-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="d2e7c-119">Возможно, что основной регистратор может не отвечать на короткие промежутки времени, основываясь на загрузке пула или серверов.</span><span class="sxs-lookup"><span data-stu-id="d2e7c-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

