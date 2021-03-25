---
title: Настройка параметров парка вызовов в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Изменение параметров парка вызовов в Skype для бизнеса server Корпоративная голосовая связь.
ms.openlocfilehash: c1eecd55dac398752915ccb63886bbf85858fe47
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111915"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a><span data-ttu-id="5682a-103">Настройка параметров парка вызовов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5682a-103">Configure Call Park settings in Skype for Business</span></span>

<span data-ttu-id="5682a-104">Изменение параметров парка вызовов в Skype для бизнеса server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="5682a-104">Modify Call Park settings in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="5682a-105">Если вы не хотите использовать параметры Call Park по умолчанию, их можно настроить.</span><span class="sxs-lookup"><span data-stu-id="5682a-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="5682a-106">При установке приложения Call Park глобальные параметры настраиваются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5682a-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="5682a-107">Можно изменить глобальные параметры, а также указать параметры, определенные для сайта.</span><span class="sxs-lookup"><span data-stu-id="5682a-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="5682a-108">Для создания новых параметров, определенных для сайта, используйте комлет **New-CsCpsConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="5682a-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="5682a-109">Чтобы изменить существующие параметры, используйте комлет **Set-CsCpsConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="5682a-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

> [!NOTE]
> <span data-ttu-id="5682a-110">Мы рекомендуем вам настроить хотя бы параметр **OnTimeoutURI** для резервного назначения, используемого в случае истечения времени ожидания запаркованного вызова и сбоя переключения на удерживаемого абонента.</span><span class="sxs-lookup"><span data-stu-id="5682a-110">At a minimum, we recommend that you configure the **OnTimeoutURI** option for the fallback destination to use when a parked call times out and ringback fails.</span></span>

<span data-ttu-id="5682a-111">Используйте командлет **New-CsCpsConfiguration** или **Set-CsCpsConfiguration** для настройки любых из приведенных ниже параметров:</span><span class="sxs-lookup"><span data-stu-id="5682a-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


| <span data-ttu-id="5682a-112">**Данный параметр:**</span><span class="sxs-lookup"><span data-stu-id="5682a-112">**This option:**</span></span>                     | <span data-ttu-id="5682a-113">**Указывает следующее:**</span><span class="sxs-lookup"><span data-stu-id="5682a-113">**Specifies this:**</span></span>                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5682a-114">**CallPickupTimeoutThreshold**</span><span class="sxs-lookup"><span data-stu-id="5682a-114">**CallPickupTimeoutThreshold**</span></span> <br/> | <span data-ttu-id="5682a-115">Период времени, по истечении которого припаркованный вызов перенаправляется обратно на номер телефона, с которого ответили на звонок.</span><span class="sxs-lookup"><span data-stu-id="5682a-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span>  <br/> <span data-ttu-id="5682a-p102">Значение следует вводить в формате чч:мм:сс, где чч — это часы, мм — минуты, сс — секунды. Минимальное значение составляет 10 секунд, максимальное — 10 минут. Значение по умолчанию — 00:01:30.</span><span class="sxs-lookup"><span data-stu-id="5682a-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span>  <br/> |
| <span data-ttu-id="5682a-119">**EnableMusicOnHold**</span><span class="sxs-lookup"><span data-stu-id="5682a-119">**EnableMusicOnHold**</span></span> <br/>          | <span data-ttu-id="5682a-120">Воспроизводится ли музыка для звонящего при парковке вызова.</span><span class="sxs-lookup"><span data-stu-id="5682a-120">Whether music plays for a caller while a call is parked.</span></span>  <br/> <span data-ttu-id="5682a-p103">Доступны значения True и False. Значение по умолчанию — True.</span><span class="sxs-lookup"><span data-stu-id="5682a-p103">Values are True or False. The default is True.</span></span>  <br/>                                                                                                                                                                                                                 |
| <span data-ttu-id="5682a-123">**MaxCallPickupAttempts**</span><span class="sxs-lookup"><span data-stu-id="5682a-123">**MaxCallPickupAttempts**</span></span> <br/>      | <span data-ttu-id="5682a-p104">Число повторных звонков припаркованного вызова на ответивший телефон перед перенаправлением на резервный универсальный код ресурса (URI), указанный для **OnTimeoutURI**. Значение по умолчанию — 1.</span><span class="sxs-lookup"><span data-stu-id="5682a-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for **OnTimeoutURI**. The default is 1.  </span></span><br/>                                                                                                                         |
| <span data-ttu-id="5682a-126">**OnTimeoutURI**</span><span class="sxs-lookup"><span data-stu-id="5682a-126">**OnTimeoutURI**</span></span> <br/>               | <span data-ttu-id="5682a-127">SIP-адрес пользователя или группы ответа, которым перенаправляется неотвеченный припаркованный вызов в случае превышения значения **MaxCallPickupAttempts**.</span><span class="sxs-lookup"><span data-stu-id="5682a-127">The SIP address of the user or response group to which an unanswered parked call is routed when **MaxCallPickupAttempts** is exceeded.</span></span> <br/> <span data-ttu-id="5682a-p105">Значение должно быть кодом URI SIP. начинающимся со строки sip:. Например, sip:bob@contoso.com. По умолчанию адрес пересылки не используется.</span><span class="sxs-lookup"><span data-stu-id="5682a-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.  </span></span><br/>                                                   |

### <a name="to-configure-call-park-settings"></a><span data-ttu-id="5682a-131">Настройка параметров парка вызовов</span><span class="sxs-lookup"><span data-stu-id="5682a-131">To configure Call Park settings</span></span>

1. <span data-ttu-id="5682a-132">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="5682a-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="5682a-133">Выполните команду: </span><span class="sxs-lookup"><span data-stu-id="5682a-133">Run:</span></span>

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > <span data-ttu-id="5682a-134">Используйте командлет **Get-CsSite** для идентификации сайта.</span><span class="sxs-lookup"><span data-stu-id="5682a-134">Use the **Get-CsSite** cmdlet to identify the site.</span></span> <span data-ttu-id="5682a-135">Подробные сведения см. в документации skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5682a-135">For details, see Skype for Business Server Management Shell documentation.</span></span>

    <span data-ttu-id="5682a-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="5682a-136">For example:</span></span>

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a><span data-ttu-id="5682a-137">См. также</span><span class="sxs-lookup"><span data-stu-id="5682a-137">See also</span></span>

[<span data-ttu-id="5682a-138">Настройка музыки Call Park для удержания вSkype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="5682a-138">Customize Call Park music on hold inSkype for Business 2015</span></span>](customize-call-park-music-on-hold.md)

[<span data-ttu-id="5682a-139">New-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="5682a-139">New-CsCpsConfiguration</span></span>](/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="5682a-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="5682a-140">Set-CsCpsConfiguration</span></span>](/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="5682a-141">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="5682a-141">Get-CsSite</span></span>](/powershell/module/skype/get-cssite?view=skype-ps)