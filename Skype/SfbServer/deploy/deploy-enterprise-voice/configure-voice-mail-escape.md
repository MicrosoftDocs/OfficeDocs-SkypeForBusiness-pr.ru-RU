---
title: Настройка эвакуации голосовой почты в Skype для бизнеса
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
description: Сводка. Узнайте, как настроить выход голосовой почты в Skype для бизнеса Server с помощью оболочки управления Skype для бизнес-серверов.
ms.openlocfilehash: c74142cf3b0f6c9d5a871e116d8e163a095ad3cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106375"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="86dbd-103">Настройка эвакуации голосовой почты в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="86dbd-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="86dbd-104">**Сводка:** Узнайте, как настроить выход голосовой почты в Skype для бизнеса Server с помощью оболочки управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="86dbd-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="86dbd-105">Когда пользователь настраивает одновременный звон на мобильный телефон, вызываемый пользователь обычно будет перенастроен на личную голосовую почту пользователя, если мобильный телефон отключен, отключен от батареи или вне диапазона.</span><span class="sxs-lookup"><span data-stu-id="86dbd-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="86dbd-106">С помощью Skype для бизнеса Server пользователи могут выбрать маршрутные вызовы, связанные с бизнесом, в корпоративную систему голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="86dbd-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="86dbd-107">В частности, можно настроить timer, и если на вызов отвечает голосовая почта перевозчика в течение определенного времени, Skype для бизнеса Server отключается от системы голосовой почты оператора (и личной голосовой почты пользователя), в то время как оставшиеся конечные точки пользователя в корпоративной системе продолжают звонить.</span><span class="sxs-lookup"><span data-stu-id="86dbd-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="86dbd-108">Таким образом, вызываемая почта автоматически перенанаписыется на корпоративную голосовую почту пользователя.</span><span class="sxs-lookup"><span data-stu-id="86dbd-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="86dbd-109">Эта конфигурация выполняется с помощью команды Команды управления Skype для **бизнес-серверов Set-CsVoicePolicy** на уровне голосовой политики со следующими параметрами.</span><span class="sxs-lookup"><span data-stu-id="86dbd-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="86dbd-110">Настройка побега голосовой почты</span><span class="sxs-lookup"><span data-stu-id="86dbd-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="86dbd-111">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="86dbd-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="86dbd-112">Задайте следующие параметры для **Set-CsVoicePolicy**:</span><span class="sxs-lookup"><span data-stu-id="86dbd-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="86dbd-113">**EnableVoicemailEscapeTimer** — включает или отключает таймер escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="86dbd-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="86dbd-p102">**PSTNVoicemailEscapeTimer** — задает значение времени ожидания в миллисекундах. Значение по умолчанию составляет 1500 миллисекунд; допустимыми являются значения из диапазона 0 – 8000 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="86dbd-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="86dbd-116">Пример</span><span class="sxs-lookup"><span data-stu-id="86dbd-116">Example</span></span>

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="86dbd-117">См. также</span><span class="sxs-lookup"><span data-stu-id="86dbd-117">See also</span></span>

[<span data-ttu-id="86dbd-118">Настройка политик голосовой связи и записей использования ТСОП для авторизации функций звонков и предоставления привилегий</span><span class="sxs-lookup"><span data-stu-id="86dbd-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges)