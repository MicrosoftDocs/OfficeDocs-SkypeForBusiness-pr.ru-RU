---
title: 'Конфигурация устройства: создание новой или редактирование существующей'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: На странице "Новая конфигурация устройства" или "Изменение конфигурации устройства" можно создать или изменить коллекцию параметров, используемых для управления Skype для бизнеса Phone Edition. Эти настройки позволяют настраивать такие параметры, как требуемый режим безопасности, уровень ведения журнала на устройстве, качество обслуживания голосовой связи (QoS), и определять необходимость автоматической блокировки телефонов по истечении заданного периода неактивности.
ms.openlocfilehash: ba84c6b9f820d0130940fce4dadad1cd38e7efec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807309"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="86ea0-104">Конфигурация устройств: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="86ea0-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="86ea0-105">На странице **"Новая конфигурация** **устройства"** или "Изменение конфигурации устройства" можно создать или изменить коллекцию параметров, используемых для управления Skype для бизнеса Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="86ea0-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="86ea0-106">Эти настройки позволяют настраивать такие параметры, как требуемый режим безопасности, уровень ведения журнала на устройстве, качество обслуживания голосовой связи (QoS), и определять необходимость автоматической блокировки телефонов по истечении заданного периода неактивности.</span><span class="sxs-lookup"><span data-stu-id="86ea0-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="86ea0-107">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="86ea0-107">Tasks you can perform</span></span>

<span data-ttu-id="86ea0-108">На странице **Создание конфигурации устройства** или **Изменение конфигурации устройства** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="86ea0-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="86ea0-109">добавить новую конфигурацию устройства;</span><span class="sxs-lookup"><span data-stu-id="86ea0-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="86ea0-110">изменить свойства существующей конфигурации устройства.</span><span class="sxs-lookup"><span data-stu-id="86ea0-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="86ea0-111">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="86ea0-111">UI Reference</span></span>

<span data-ttu-id="86ea0-112">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="86ea0-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="86ea0-113">**Область действия** Определяет область (глобальную или на уровне сайта) конфигурации устройства.</span><span class="sxs-lookup"><span data-stu-id="86ea0-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="86ea0-114">**Имя** Можно добавить или изменить имя конфигурации устройства.</span><span class="sxs-lookup"><span data-stu-id="86ea0-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="86ea0-115">**Безопасность SIP** Вы можете настроить требования к транспорту и проверке подлинности для устройств Skype для бизнеса Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="86ea0-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="86ea0-116">Можно выбрать один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="86ea0-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="86ea0-117">**Низкая** Разрешить любой тип авторизации или транспорта.</span><span class="sxs-lookup"><span data-stu-id="86ea0-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="86ea0-118">**Средний** Для проверки подлинности пользователей требуется NTLM или Kerberos.</span><span class="sxs-lookup"><span data-stu-id="86ea0-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="86ea0-119">**Высокая** Для проверки подлинности пользователей требуется NTLM или Kerberos, а для подключений SIP требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="86ea0-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="86ea0-120">**Уровень ведения журнала** Ведение журнала можно включить на устройстве UC.</span><span class="sxs-lookup"><span data-stu-id="86ea0-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="86ea0-121">Допустимые значения: Off; Низкий; Средний; и High.</span><span class="sxs-lookup"><span data-stu-id="86ea0-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="86ea0-122">Значение по умолчанию — Off (Выкл.).</span><span class="sxs-lookup"><span data-stu-id="86ea0-122">The default value is Off.</span></span>
    
- <span data-ttu-id="86ea0-123">**Качество обслуживания голосовой почты (QoS)** Можно указать значение DSCP, назначенное голосовым трафиком, поступающим с устройства Skype для бизнеса Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="86ea0-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="86ea0-124">Значение по умолчанию — 40.</span><span class="sxs-lookup"><span data-stu-id="86ea0-124">The default is 40.</span></span> <span data-ttu-id="86ea0-125">Однако для голосового трафика вместо значения 40 практически всегда используется значение DSCP 46.</span><span class="sxs-lookup"><span data-stu-id="86ea0-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="86ea0-126">Для обеспечения единообразия в сети может потребоваться изменить это значение на 46.</span><span class="sxs-lookup"><span data-stu-id="86ea0-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="86ea0-127">**Блокировка телефона** Вы можете указать, будут ли телефоны UC автоматически заблокироваться после указанного периода бездействия.</span><span class="sxs-lookup"><span data-stu-id="86ea0-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="86ea0-128">Ниже параметров можно настроить:</span><span class="sxs-lookup"><span data-stu-id="86ea0-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="86ea0-129">**Принудительное блокировка устройства** Вы можете принудительно заблокировать устройство, выбрав этот блокировок.</span><span class="sxs-lookup"><span data-stu-id="86ea0-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="86ea0-130">**Минимальная длина ПИН-кода** Можно указать минимальную длину пин-кода, используемого для разблокировки телефона.</span><span class="sxs-lookup"><span data-stu-id="86ea0-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="86ea0-131">Диапазон значений данного параметра — от 4 до 15 цифр.</span><span class="sxs-lookup"><span data-stu-id="86ea0-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="86ea0-132">Значение по умолчанию — шесть.</span><span class="sxs-lookup"><span data-stu-id="86ea0-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="86ea0-133">**Время простоя блокировки телефона** Вы можете указать минимальную продолжительность времени до того, как телефон заблокирует себя.</span><span class="sxs-lookup"><span data-stu-id="86ea0-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="86ea0-134">Диапазон времени от 0 до 60 минут; Значение по умолчанию — 10 минут.</span><span class="sxs-lookup"><span data-stu-id="86ea0-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="86ea0-135">Введите значение в формате ЧЧ:ММ:СС.</span><span class="sxs-lookup"><span data-stu-id="86ea0-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="86ea0-136">См. также</span><span class="sxs-lookup"><span data-stu-id="86ea0-136">See also</span></span>

[<span data-ttu-id="86ea0-137">Конфигурация устройств</span><span class="sxs-lookup"><span data-stu-id="86ea0-137">Device Configuration</span></span>](device-configuration.md)

[<span data-ttu-id="86ea0-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="86ea0-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
