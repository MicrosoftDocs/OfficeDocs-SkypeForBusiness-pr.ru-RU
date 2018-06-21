---
title: Расширитель параметров регистратора
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: Устойчивость предоставляет высокой доступности и аварийного восстановления для пула регистратора. С указанием регистратора резервного копирования в случае сбоя основного регистратора Registrar взять на себя для неудачных регистратора резервной копии позволяя пользователям входить в систему и общаться. Пользователи могут использовать потенциально ограниченной функциональности, в зависимости от того, который системы не были выполнены в основном регистраторе.
ms.openlocfilehash: b1609bfa8fd3fe9fb58d02c2154a3427c5ba94c0
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/20/2018
ms.locfileid: "19964690"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="77cf3-105">Расширитель параметров регистратора</span><span class="sxs-lookup"><span data-stu-id="77cf3-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="77cf3-106">Устойчивость предоставляет высокой доступности и аварийного восстановления для пула регистратора.</span><span class="sxs-lookup"><span data-stu-id="77cf3-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="77cf3-107">С указанием регистратора резервного копирования в случае сбоя основного регистратора Registrar взять на себя для неудачных регистратора резервной копии позволяя пользователям входить в систему и общаться.</span><span class="sxs-lookup"><span data-stu-id="77cf3-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="77cf3-108">Пользователи могут использовать потенциально ограниченной функциональности, в зависимости от того, который системы не были выполнены в основном регистраторе.</span><span class="sxs-lookup"><span data-stu-id="77cf3-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="77cf3-109">В разделе **устойчивость** диалогового окна **Изменение свойств** для обеспечения связи в филиалах или для обеспечения связи в филиалах можно изменить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="77cf3-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="77cf3-110">**Связанная служба пользователей и пул резервного регистратора** В раскрывающемся списке выберите пул переднего плана Enterprise Edition или Standard Edition сервера переднего плана, чтобы выступать в качестве резервного регистратора для обеспечения связи в филиалах или для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="77cf3-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="77cf3-111">**Включение отработки отказа и восстановления размещения** Выберите этот параметр, чтобы разрешить автоматическое обнаружение сбоя регистратора и автоматическое определение, регистратор основным резервное копирование и готовы продолжить процесс регистратора.</span><span class="sxs-lookup"><span data-stu-id="77cf3-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="77cf3-112">**Интервал обнаружения сбоев (сек)** Введите число секунд, по истечении которого определяется, что основной регистратора завершен с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="77cf3-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="77cf3-113">Значение по умолчанию — 120 секунд.</span><span class="sxs-lookup"><span data-stu-id="77cf3-113">The default value is 120 seconds.</span></span> <span data-ttu-id="77cf3-114">Это поле является обязательным, если выбрано **Включение отработки отказа и восстановления размещения**.</span><span class="sxs-lookup"><span data-stu-id="77cf3-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="77cf3-115">**Интервал резервного обнаружения (сек)** Введите число секунд, по истечении которого определяется, что регистратор основным создается резервная копия.</span><span class="sxs-lookup"><span data-stu-id="77cf3-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="77cf3-116">Значение по умолчанию — 240 секунд.</span><span class="sxs-lookup"><span data-stu-id="77cf3-116">The default value is 240 seconds.</span></span> <span data-ttu-id="77cf3-117">Это поле является обязательным, если выберите **Включить отработки отказа и возврат**.</span><span class="sxs-lookup"><span data-stu-id="77cf3-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="77cf3-118">При определении интервал обнаружения сбоев и интервал резервный обнаружения быть не следует ввести интервал, который будет отображено отработки отказа и возврата в случае, если не отвечает на короткое время регистратора.</span><span class="sxs-lookup"><span data-stu-id="77cf3-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="77cf3-119">Существует возможность, что регистратор основным перестает отвечать на короткое время в зависимости от загрузки пула или серверов.</span><span class="sxs-lookup"><span data-stu-id="77cf3-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

