---
title: Конфигурация устройства создание нового или изменение существующего
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: На странице Создание конфигурации устройства или изменение конфигурации устройства вы можете создавать и изменять наборы параметров, используемых для управления Skype для бизнеса Phone Edition. Эти настройки позволяют настраивать такие параметры, как требуемый режим безопасности, уровень ведения журнала на устройстве, качество обслуживания голосовой связи (QoS), и определять необходимость автоматической блокировки телефонов по истечении заданного периода неактивности.
ms.openlocfilehash: 2af651846a70605b36a8481ee53a54c47901e258
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285969"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="b0fcd-104">Конфигурация устройств: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="b0fcd-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="b0fcd-105">На странице **Создание конфигурации устройства** или **изменение конфигурации устройства** вы можете создавать и изменять наборы параметров, используемых для управления Skype для бизнеса Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="b0fcd-106">Эти настройки позволяют настраивать такие параметры, как требуемый режим безопасности, уровень ведения журнала на устройстве, качество обслуживания голосовой связи (QoS), и определять необходимость автоматической блокировки телефонов по истечении заданного периода неактивности.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="b0fcd-107">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="b0fcd-107">Tasks you can perform</span></span>

<span data-ttu-id="b0fcd-108">На странице **Создание конфигурации устройства** или **Изменение конфигурации устройства** можно выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="b0fcd-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="b0fcd-109">добавить новую конфигурацию устройства;</span><span class="sxs-lookup"><span data-stu-id="b0fcd-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="b0fcd-110">изменить свойства существующей конфигурации устройства.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="b0fcd-111">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="b0fcd-111">UI Reference</span></span>

<span data-ttu-id="b0fcd-112">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="b0fcd-113">**Область действия** Определяет область (глобальную или веб-сайт) конфигурации устройства.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="b0fcd-114">**Name (имя** ) Вы можете добавить или изменить название конфигурации устройства.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="b0fcd-115">**Безопасность SIP** Вы можете настроить требования к транспортировке и проверке подлинности для устройств Skype для бизнеса Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="b0fcd-116">Вы можете выбрать один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="b0fcd-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="b0fcd-117">**Низкий уровень** Разрешите любой тип авторизации или транспорта.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="b0fcd-118">**Средний уровень** Для проверки подлинности пользователей требуется протокол NTLM или Kerberos.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="b0fcd-119">**Высокий уровень** Для подключений SIP требуется протокол NTLM или Kerberos для проверки подлинности пользователей, а TLS.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="b0fcd-120">**Уровень ведения журнала** Вы можете включить ведение журнала на устройстве UC.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="b0fcd-121">Допустимые значения: Off; Низким Канал и высокий.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="b0fcd-122">Значение по умолчанию — OFF.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-122">The default value is Off.</span></span>
    
- <span data-ttu-id="b0fcd-123">**Качество обслуживания голоса (QoS)** Вы можете указать значение DSCP, назначенное для голосового трафика, еманатинг с устройства Skype для бизнеса Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="b0fcd-124">Значение по умолчанию — 40.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-124">The default is 40.</span></span> <span data-ttu-id="b0fcd-125">Однако 40 не является значением, которое обычно используется для передачи звука; Вместо этого голосовой трафик почти всегда помечается с помощью кода DSCP 46.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="b0fcd-126">Для обеспечения согласованности сети, возможно, потребуется изменить это значение на 46.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="b0fcd-127">**Блокировка телефона** Вы можете указать, будут ли телефонные номера автоматически блокироваться по истечении определенного периода бездействия.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="b0fcd-128">Ниже перечислены параметры, которые можно настроить.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="b0fcd-129">**Принудительная Блокировка устройства** Чтобы принудительно заблокировать устройства, установите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="b0fcd-130">**Минимальная длина ПИН-кода** Вы можете указать минимальную длину для персонального идентификационного номера (PIN), который используется для разблокировки телефона.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="b0fcd-131">Диапазон длины PIN-кода состоит из 4 – 15 цифр.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="b0fcd-132">Длина по умолчанию составляет шести цифр.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="b0fcd-133">**Время ожидания блокировки телефона** Вы можете указать минимальную продолжительность времени перед тем, как заблокировали телефон.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="b0fcd-134">Диапазон времени ожидания от 0 до 60 минут; значение по умолчанию — 10 минут.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="b0fcd-135">Введите значение в формате чч: мм: СС.</span><span class="sxs-lookup"><span data-stu-id="b0fcd-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b0fcd-136">См. также</span><span class="sxs-lookup"><span data-stu-id="b0fcd-136">See also</span></span>

[<span data-ttu-id="b0fcd-137">Конфигурация устройств</span><span class="sxs-lookup"><span data-stu-id="b0fcd-137">Device Configuration</span></span>](device-configuration.md)

[<span data-ttu-id="b0fcd-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="b0fcd-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
