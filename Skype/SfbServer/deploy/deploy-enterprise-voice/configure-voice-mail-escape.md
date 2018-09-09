---
title: Настройка отмены для голосовой почты в Скайп для бизнеса
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Сводка: Сведения о настройке отмены для голосовой почты в Скайп для Business Server с помощью Скайп для консоли Business Server.'
ms.openlocfilehash: 260488701348fdf52eaccb82cc6dc41c19c68339
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "23891267"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="f18d6-103">Настройка отмены для голосовой почты в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f18d6-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="f18d6-104">**Сводка:** Сведения о настройке отмены для голосовой почты в Скайп для Business Server с помощью Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="f18d6-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="f18d6-105">Когда пользователь настраивает одновременных звонков на мобильный телефон, вызывающий объект обычно направляются в личную голосовую почту пользователя Если мобильный телефон является выключены, от батарей или вне диапазона.</span><span class="sxs-lookup"><span data-stu-id="f18d6-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="f18d6-106">С Скайп Business Server связанной с бизнесом вызовы, направляемые в свои системы корпоративной голосовой почты выбранных пользователей.</span><span class="sxs-lookup"><span data-stu-id="f18d6-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="f18d6-107">В частности можно настроить таймера, а если звонок был дан ответ с транспортной голосовой почты в интервал времени определенные, Скайп для Business Server будет отключиться от транспортной системы голосовой почты (и личную голосовую почту пользователя), при пользователя Оставшиеся конечных точек в корпоративной системе продолжить звонок.</span><span class="sxs-lookup"><span data-stu-id="f18d6-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="f18d6-108">Таким образом, вызывающего автоматически маршрутизируются для корпоративной голосовой почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="f18d6-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="f18d6-109">Эта настройка выполняется с помощью Скайп для командлета консоли Business Server, **Set-CsVoicePolicy**, на уровне политики голосовой связи, используя следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="f18d6-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="f18d6-110">Настройка escape-последовательности голосовой почты</span><span class="sxs-lookup"><span data-stu-id="f18d6-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="f18d6-111">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="f18d6-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="f18d6-112">Задайте следующие параметры для **Set-CsVoicePolicy**:</span><span class="sxs-lookup"><span data-stu-id="f18d6-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="f18d6-113">**EnableVoicemailEscapeTimer** — включает или отключает таймер escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="f18d6-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="f18d6-p102">**PSTNVoicemailEscapeTimer** — задает значение времени ожидания в миллисекундах. Значение по умолчанию составляет 1500 миллисекунд; допустимы значения из диапазона 0 – 8000 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="f18d6-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="f18d6-116">Пример</span><span class="sxs-lookup"><span data-stu-id="f18d6-116">Example</span></span>

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="f18d6-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f18d6-117">See also</span></span>

[<span data-ttu-id="f18d6-118">Настройка политик голосовой связи и записей использования ТСОП для авторизации функций звонков и привилегии</span><span class="sxs-lookup"><span data-stu-id="f18d6-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

