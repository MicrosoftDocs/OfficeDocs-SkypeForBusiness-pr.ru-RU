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
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: Компонент устойчивости обеспечивает высокую доступность и аварийное восстановление для пула регистратора. Если при сбое основного регистратора доступен резервный регистратор, он может взять на себя функции основного неработающего регистратора, позволяя пользователям выполнять вход и взаимодействовать. В этом случае пользователям могут быть доступны не все функциональные возможности, это зависит от того, на каких еще системах, кроме основного регистратора, возник сбой.
ms.openlocfilehash: f6ea6907942111db92ca3bfe2dfef1712bd53a62
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217160"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="1a633-105">Расширитель параметров регистратора</span><span class="sxs-lookup"><span data-stu-id="1a633-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="1a633-p102">Компонент устойчивости обеспечивает высокую доступность и аварийное восстановление для пула регистратора. Если при сбое основного регистратора доступен резервный регистратор, он может взять на себя функции основного неработающего регистратора, позволяя пользователям выполнять вход и взаимодействовать. В этом случае пользователям могут быть доступны не все функциональные возможности, это зависит от того, на каких еще системах, кроме основного регистратора, возник сбой.</span><span class="sxs-lookup"><span data-stu-id="1a633-p102">Resiliency provides high availability and disaster recovery for the Registrar pool. By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate. Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="1a633-109">В разделе **Устойчивость** диалогового окна **Изменение свойств** для устройства или сервера для обеспечения связи в филиалах можно изменить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="1a633-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="1a633-110">**Связанная служба пользователей и пул регистратора резервного копирования** В раскрывающемся списке выберите интерфейсный пул переднего плана Enterprise Edition или сервер переднего плана Standard Edition, который будет использоваться в качестве регистратора резервного копирования для устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="1a633-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="1a633-111">**Включение отработки отказа и восстановления размещения** Выберите этот параметр, чтобы разрешить автоматическое обнаружение неисправного регистратора и автоматическое определение того, что основной регистратор выполняет резервное копирование и готов к возобновлению процесса регистратора.</span><span class="sxs-lookup"><span data-stu-id="1a633-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="1a633-112">**Интервал обнаружения отказов (сек)** Введите количество секунд, которое должно пройти до того, как будет определено, что основной регистратор завершился ошибкой.</span><span class="sxs-lookup"><span data-stu-id="1a633-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="1a633-113">Значение по умолчанию: 120 секунд.</span><span class="sxs-lookup"><span data-stu-id="1a633-113">The default value is 120 seconds.</span></span> <span data-ttu-id="1a633-114">Это поле является обязательным, если выбран параметр **включить отработку отказа и восстановление после сбоя**.</span><span class="sxs-lookup"><span data-stu-id="1a633-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="1a633-115">**Интервал обнаружения резервных возвратов (сек)** Введите количество секунд, которое должно пройти до того, как будет определено резервное копирование основного регистратора.</span><span class="sxs-lookup"><span data-stu-id="1a633-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="1a633-116">Значение по умолчанию 240 секунд.</span><span class="sxs-lookup"><span data-stu-id="1a633-116">The default value is 240 seconds.</span></span> <span data-ttu-id="1a633-117">Это поле является обязательным, если выбран параметр **включить отработку отказа и резервное**восстановление.</span><span class="sxs-lookup"><span data-stu-id="1a633-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="1a633-118">При определении интервала обнаружения отказов и интервала обнаружения резервной стратегии следует следить за тем, чтобы не указать интервал, в результате которого происходит отработка отказа и отката, если регистратор не отвечает на короткий период времени.</span><span class="sxs-lookup"><span data-stu-id="1a633-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="1a633-119">Возможно, основной регистратор может не отвечать на несколько периодов времени в зависимости от загрузки пула или серверов.</span><span class="sxs-lookup"><span data-stu-id="1a633-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

