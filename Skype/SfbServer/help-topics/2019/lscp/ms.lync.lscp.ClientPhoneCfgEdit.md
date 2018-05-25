---
title: Создание новой или редактирование существующей конфигурации устройства
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: На странице Создание конфигурации устройства или изменение конфигурации устройства можно создать или изменить набор параметров, используемый для управления Скайп для Business Phone Edition. Эти настройки позволяют настраивать такие параметры, как требуемый режим безопасности, уровень ведения журнала на устройстве, качество обслуживания голосовой связи (QoS), и определять необходимость автоматической блокировки телефонов по истечении заданного периода неактивности.
ms.openlocfilehash: c6d8f291b6602ad41ca2942e2d4b507d2727bcd1
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2018
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="45318-104">Конфигурация устройств: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="45318-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="45318-105">На странице **Создание конфигурации устройства** или **Изменение конфигурации устройства** можно создать или изменить набор параметров, используемый для управления Скайп для Business Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="45318-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="45318-106">Эти настройки позволяют настраивать такие параметры, как требуемый режим безопасности, уровень ведения журнала на устройстве, качество обслуживания голосовой связи (QoS), и определять необходимость автоматической блокировки телефонов по истечении заданного периода неактивности.</span><span class="sxs-lookup"><span data-stu-id="45318-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="45318-107">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="45318-107">Tasks you can perform</span></span>

<span data-ttu-id="45318-108">На странице **Создание конфигурации устройства** или **Изменение конфигурации устройства** можно выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="45318-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="45318-109">добавить новую конфигурацию устройства;</span><span class="sxs-lookup"><span data-stu-id="45318-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="45318-110">изменить свойства существующей конфигурации устройства.</span><span class="sxs-lookup"><span data-stu-id="45318-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="45318-111">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="45318-111">UI Reference</span></span>

<span data-ttu-id="45318-112">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="45318-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="45318-113">**Область** Определяет область (глобальную или сайтов) конфигурации устройства.</span><span class="sxs-lookup"><span data-stu-id="45318-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="45318-114">**Имя** Вы можете добавить или изменить имя конфигурации устройства.</span><span class="sxs-lookup"><span data-stu-id="45318-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="45318-115">**SIP-безопасность** Вы можете настроить требования транспортировки и проверки подлинности для Скайп для устройств Business Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="45318-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="45318-116">Можно выбрать один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="45318-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="45318-117">**Низкий** Разрешить любой тип авторизации или транспорта.</span><span class="sxs-lookup"><span data-stu-id="45318-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="45318-118">**Средний** NTLM или Kerberos является обязательным для проверки подлинности пользователей.</span><span class="sxs-lookup"><span data-stu-id="45318-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="45318-119">**Высокая** Для проверки подлинности пользователя требуется NTLM или Kerberos, а для SIP-подключений требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="45318-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="45318-120">**Уровень ведения журнала** Можно включить ведение журнала на устройство системы объединенных Коммуникаций.</span><span class="sxs-lookup"><span data-stu-id="45318-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="45318-121">Допустимые значения: отключена; Низкий уровень; Средний; и высокой.</span><span class="sxs-lookup"><span data-stu-id="45318-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="45318-122">Значение по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="45318-122">The default value is Off.</span></span>
    
- <span data-ttu-id="45318-123">**Качество обслуживания (QoS) голосовой связи** Можно указать значение DSCP, назначенных для передачи голосовых данных при из Скайп для устройства Business Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="45318-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="45318-124">Значение по умолчанию — 40.</span><span class="sxs-lookup"><span data-stu-id="45318-124">The default is 40.</span></span> <span data-ttu-id="45318-125">Тем не менее 40 не является значение, обычно используется для трафика аудио; Вместо этого трафика аудио почти всегда помечается кодом DSCP 46.</span><span class="sxs-lookup"><span data-stu-id="45318-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="45318-126">Для обеспечения согласованности по сети, можно изменить это значение 46.</span><span class="sxs-lookup"><span data-stu-id="45318-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="45318-127">**Блокировки телефона** Можно указать ли чтобы телефоны объединенных Коммуникаций будет автоматически заблокировать свои после определенного периода бездействия.</span><span class="sxs-lookup"><span data-stu-id="45318-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="45318-128">Ниже приведены параметры, которые можно настроить.</span><span class="sxs-lookup"><span data-stu-id="45318-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="45318-129">**Принудительная блокировка устройств** Вы можете принудительно заблокировать, установив этот флажок устройство.</span><span class="sxs-lookup"><span data-stu-id="45318-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="45318-130">**Длина ПИН-кода как минимум** Можно указать минимальную длину для персонального идентификационного номера (ПИН-кода), который используется для разблокировки телефона.</span><span class="sxs-lookup"><span data-stu-id="45318-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="45318-131">Значения длины ПИН-код — от четырех до 15 цифр.</span><span class="sxs-lookup"><span data-stu-id="45318-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="45318-132">Длина по умолчанию состоит из шести цифр.</span><span class="sxs-lookup"><span data-stu-id="45318-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="45318-133">**Время ожидания блокировки телефона** Минимальный интервал времени до блокировки телефона можно указать самого.</span><span class="sxs-lookup"><span data-stu-id="45318-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="45318-134">Значения времени ожидания — от 0 до 60 минут. значение по умолчанию — 10 минут.</span><span class="sxs-lookup"><span data-stu-id="45318-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="45318-135">Введите значение в формате чч.</span><span class="sxs-lookup"><span data-stu-id="45318-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="45318-136">См. также</span><span class="sxs-lookup"><span data-stu-id="45318-136">See also</span></span>

#### 

[<span data-ttu-id="45318-137">Конфигурация устройств</span><span class="sxs-lookup"><span data-stu-id="45318-137">Device Configuration</span></span>](device-configuration.md)
#### 

[<span data-ttu-id="45318-138">SET-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="45318-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)

