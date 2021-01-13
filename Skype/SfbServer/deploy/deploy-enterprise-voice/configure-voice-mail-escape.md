---
title: Настройка escape-сообщения голосовой почты в Skype для бизнеса
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
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: Сводка. Узнайте, как настроить escape-вызов голосовой почты в Skype для бизнеса Server с помощью оболочки управления Skype для бизнеса Server.
ms.openlocfilehash: c6326360a0e49715feb7e9f9c3c123ec42b9c330
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824929"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="c6360-103">Настройка escape-сообщения голосовой почты в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c6360-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="c6360-104">**Сводка:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c6360-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="c6360-105">Когда пользователь настраивает одновременные звонки на мобильный телефон, звонячий обычно перенанается на личную голосовую почту пользователя, если мобильный телефон отключен, выключен или находится вне диапазона.</span><span class="sxs-lookup"><span data-stu-id="c6360-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="c6360-106">С помощью Skype для бизнеса Server пользователи могут выбрать перена маршрутизов, связанных с бизнесом, в корпоративную систему голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="c6360-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="c6360-107">В частности, можно настроить timer, и если на вызов отвечает голосовая почта оператора в течение определенного диапазона времени, Skype для бизнеса Server отключается от системы голосовой почты оператора (и личной голосовой почты пользователя), а остальные конечные точки пользователя в корпоративной системе продолжают звонить.</span><span class="sxs-lookup"><span data-stu-id="c6360-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="c6360-108">Таким образом, вызываемая почта автоматически маршрутируется в корпоративную голосовую почту пользователя.</span><span class="sxs-lookup"><span data-stu-id="c6360-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="c6360-109">Эта конфигурация выполняется с помощью команды Skype для бизнеса Server Management Shell **Set-CsVoicePolicy** на уровне политики голосовой связи со следующими параметрами.</span><span class="sxs-lookup"><span data-stu-id="c6360-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="c6360-110">Настройка escape-сообщения голосовой почты</span><span class="sxs-lookup"><span data-stu-id="c6360-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="c6360-111">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="c6360-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="c6360-112">Задайте следующие параметры для **Set-CsVoicePolicy**:</span><span class="sxs-lookup"><span data-stu-id="c6360-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="c6360-113">**EnableVoicemailEscapeTimer** — включает или отключает таймер escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="c6360-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="c6360-p102">**PSTNVoicemailEscapeTimer** — задает значение времени ожидания в миллисекундах. Значение по умолчанию составляет 1500 миллисекунд; допустимыми являются значения из диапазона 0 – 8000 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="c6360-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="c6360-116">Пример</span><span class="sxs-lookup"><span data-stu-id="c6360-116">Example</span></span>

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="c6360-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c6360-117">See also</span></span>

[<span data-ttu-id="c6360-118">Настройка политик голосовой связи и записей использования ТСОП для авторизации функций звонков и предоставления привилегий</span><span class="sxs-lookup"><span data-stu-id="c6360-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

