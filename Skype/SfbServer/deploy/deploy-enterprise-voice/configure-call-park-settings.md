---
title: Настройка параметров парковки вызовов в Скайп для бизнеса
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Изменение параметров парковки вызовов в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: ab2fec9a0455316ea1b0fcba6a771b91f0d115d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223685"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a><span data-ttu-id="3a8a9-103">Настройка параметров парковки вызовов в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3a8a9-103">Configure Call Park settings in Skype for Business</span></span>

<span data-ttu-id="3a8a9-104">Изменение параметров парковки вызовов в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="3a8a9-104">Modify Call Park settings in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="3a8a9-105">Если не хотите использовать параметры по умолчанию парковка вызовов, можно настроить их.</span><span class="sxs-lookup"><span data-stu-id="3a8a9-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="3a8a9-106">При установке приложения приостановки звонков по умолчанию настраиваются глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="3a8a9-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="3a8a9-107">Можно изменять глобальные параметры, а также можно указать параметры узла.</span><span class="sxs-lookup"><span data-stu-id="3a8a9-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="3a8a9-108">Командлет **New-CsCpsConfiguration** для создания новых параметров сайта.</span><span class="sxs-lookup"><span data-stu-id="3a8a9-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="3a8a9-109">Командлет **Set-CsCpsConfiguration** используется для изменения существующих параметров.</span><span class="sxs-lookup"><span data-stu-id="3a8a9-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

> [!NOTE]
> <span data-ttu-id="3a8a9-110">Мы рекомендуем настроить хотя бы параметр **OnTimeoutURI** для резервного назначения, используемого в случае истечения времени ожидания запаркованного вызова и сбоя переключения на удерживаемого абонента.</span><span class="sxs-lookup"><span data-stu-id="3a8a9-110">At a minimum, we recommend that you configure the **OnTimeoutURI** option for the fallback destination to use when a parked call times out and ringback fails.</span></span>

<span data-ttu-id="3a8a9-111">Используйте командлет **New-CsCpsConfiguration** или **Set-CsCpsConfiguration** для настройки любых из приведенных ниже параметров:</span><span class="sxs-lookup"><span data-stu-id="3a8a9-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


| <span data-ttu-id="3a8a9-112">**Данный параметр:**</span><span class="sxs-lookup"><span data-stu-id="3a8a9-112">**This option:**</span></span>                     | <span data-ttu-id="3a8a9-113">**Указывает следующее:**</span><span class="sxs-lookup"><span data-stu-id="3a8a9-113">**Specifies this:**</span></span>                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="3a8a9-114">**CallPickupTimeoutThreshold**</span><span class="sxs-lookup"><span data-stu-id="3a8a9-114">**CallPickupTimeoutThreshold**</span></span> <br/> | <span data-ttu-id="3a8a9-115">Период времени, по истечении которого припаркованный вызов перенаправляется обратно на номер телефона, с которого ответили на звонок.</span><span class="sxs-lookup"><span data-stu-id="3a8a9-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span>  <br/> <span data-ttu-id="3a8a9-p102">Значение следует вводить в формате чч:мм:сс, где чч — это часы, мм — минуты, сс — секунды. Минимальное значение составляет 10 секунд, максимальное — 10 минут. Значение по умолчанию — 00:01:30.</span><span class="sxs-lookup"><span data-stu-id="3a8a9-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span>  <br/> |
| <span data-ttu-id="3a8a9-119">**EnableMusicOnHold**</span><span class="sxs-lookup"><span data-stu-id="3a8a9-119">**EnableMusicOnHold**</span></span> <br/>          | <span data-ttu-id="3a8a9-120">Воспроизводится ли музыка для звонящего при парковке вызова.</span><span class="sxs-lookup"><span data-stu-id="3a8a9-120">Whether music plays for a caller while a call is parked.</span></span>  <br/> <span data-ttu-id="3a8a9-p103">Доступны значения True и False. Значение по умолчанию — True.</span><span class="sxs-lookup"><span data-stu-id="3a8a9-p103">Values are True or False. The default is True.</span></span>  <br/>                                                                                                                                                                                                                 |
| <span data-ttu-id="3a8a9-123">**MaxCallPickupAttempts**</span><span class="sxs-lookup"><span data-stu-id="3a8a9-123">**MaxCallPickupAttempts**</span></span> <br/>      | <span data-ttu-id="3a8a9-p104">Число повторных звонков припаркованного вызова на ответивший телефон перед перенаправлением на резервный универсальный код ресурса (URI), указанный для **OnTimeoutURI**. Значение по умолчанию — 1.</span><span class="sxs-lookup"><span data-stu-id="3a8a9-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for **OnTimeoutURI**. The default is 1.  </span></span><br/>                                                                                                                         |
| <span data-ttu-id="3a8a9-126">**OnTimeoutURI**</span><span class="sxs-lookup"><span data-stu-id="3a8a9-126">**OnTimeoutURI**</span></span> <br/>               | <span data-ttu-id="3a8a9-127">SIP-адрес пользователя или группы ответа, которым перенаправляется неотвеченный припаркованный вызов в случае превышения значения **MaxCallPickupAttempts**.</span><span class="sxs-lookup"><span data-stu-id="3a8a9-127">The SIP address of the user or response group to which an unanswered parked call is routed when **MaxCallPickupAttempts** is exceeded.</span></span> <br/> <span data-ttu-id="3a8a9-p105">Значение должно быть кодом URI SIP. начинающимся со строки sip:. Например, sip:bob@contoso.com. По умолчанию адрес пересылки не используется.</span><span class="sxs-lookup"><span data-stu-id="3a8a9-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.  </span></span><br/>                                                   |

### <a name="to-configure-call-park-settings"></a><span data-ttu-id="3a8a9-131">Настройка параметров парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="3a8a9-131">To configure Call Park settings</span></span>

1. <span data-ttu-id="3a8a9-132">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="3a8a9-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="3a8a9-133">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3a8a9-133">Run:</span></span>

   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > <span data-ttu-id="3a8a9-134">Используйте командлет **Get-CsSite** для идентификации сайта.</span><span class="sxs-lookup"><span data-stu-id="3a8a9-134">Use the **Get-CsSite** cmdlet to identify the site.</span></span> <span data-ttu-id="3a8a9-135">Дополнительные сведения см Скайп для документации по консоли управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a8a9-135">For details, see Skype for Business Server Management Shell documentation.</span></span>

    <span data-ttu-id="3a8a9-136">Например:</span><span class="sxs-lookup"><span data-stu-id="3a8a9-136">For example:</span></span>

   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a><span data-ttu-id="3a8a9-137">См. также</span><span class="sxs-lookup"><span data-stu-id="3a8a9-137">See also</span></span>

[<span data-ttu-id="3a8a9-138">Настройка функции воспроизведения музыки для режима удержания при парковке вызова в Skype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="3a8a9-138">Customize Call Park music on hold inSkype for Business 2015</span></span>](customize-call-park-music-on-hold.md)

[<span data-ttu-id="3a8a9-139">New-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="3a8a9-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="3a8a9-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="3a8a9-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="3a8a9-141">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="3a8a9-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)
