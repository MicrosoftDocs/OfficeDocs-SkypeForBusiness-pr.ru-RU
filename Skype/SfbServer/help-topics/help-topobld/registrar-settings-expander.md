---
title: Расширитель параметров регистратора
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 8ab5fc804b6fad1f049e70477d7c16cb35111f79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818299"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="1b68d-105">Расширитель параметров регистратора</span><span class="sxs-lookup"><span data-stu-id="1b68d-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="1b68d-p102">Компонент устойчивости обеспечивает высокую доступность и аварийное восстановление для пула регистратора. Если при сбое основного регистратора доступен резервный регистратор, он может взять на себя функции основного неработающего регистратора, позволяя пользователям выполнять вход и взаимодействовать. В этом случае пользователям могут быть доступны не все функциональные возможности, это зависит от того, на каких еще системах, кроме основного регистратора, возник сбой.</span><span class="sxs-lookup"><span data-stu-id="1b68d-p102">Resiliency provides high availability and disaster recovery for the Registrar pool. By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate. Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="1b68d-109">В разделе **Устойчивость** диалогового окна **Изменение свойств** для устройства или сервера для обеспечения связи в филиалах можно изменить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="1b68d-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="1b68d-110">**Связанная служба пользователей и резервный пул регистратора** В выпадаемом списке выберите пул переднего плановых серверов Enterprise Edition или сервер переднего сервера Standard Edition, который будет выступать в качестве резервного регистратора для устройства или сервера survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="1b68d-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="1b68d-111">**Включить откат и откат** Выберите этот параметр, чтобы разрешить автоматическое обнаружение сбойного регистратора и автоматическое определение готовности основного регистратора к возобновлению процесса регистратора.</span><span class="sxs-lookup"><span data-stu-id="1b68d-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="1b68d-112">**Интервал обнаружения сбоев (с)** Введите время в секундах до того, как будет определено, что основной регистратор не сбой.</span><span class="sxs-lookup"><span data-stu-id="1b68d-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="1b68d-113">Значение по умолчанию: 120 секунд.</span><span class="sxs-lookup"><span data-stu-id="1b68d-113">The default value is 120 seconds.</span></span> <span data-ttu-id="1b68d-114">Это поле необходимо при выборе "Включить откат" и **"Откат".**</span><span class="sxs-lookup"><span data-stu-id="1b68d-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="1b68d-115">**Интервал обнаружения отката (с)** Введите время в секундах до того, как будет определено, что для основного регистратора будет заархивироваться.</span><span class="sxs-lookup"><span data-stu-id="1b68d-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="1b68d-116">Значение по умолчанию — 240 секунд.</span><span class="sxs-lookup"><span data-stu-id="1b68d-116">The default value is 240 seconds.</span></span> <span data-ttu-id="1b68d-117">Это поле необходимо при выборе "Включить откат" **и "Откат".**</span><span class="sxs-lookup"><span data-stu-id="1b68d-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="1b68d-118">При определении интервала обнаружения сбоев и интервала обнаружения отказа не вводите интервал, который приведет к откату и откату, если регистратор не отвечает в течение короткого периода времени.</span><span class="sxs-lookup"><span data-stu-id="1b68d-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="1b68d-119">Возможно, основной регистратор не будет отвечать в течение короткого периода времени в зависимости от загрузки пула или серверов.</span><span class="sxs-lookup"><span data-stu-id="1b68d-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

