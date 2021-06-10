---
title: Маскировка номеров телефонов Microsoft Teams собраниях
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как маскировать номера телефонов Microsoft Teams собраниях
ms.openlocfilehash: bc3325805db63f86937a27d63cfc08ab0de84006
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117717"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a><span data-ttu-id="2127a-103">Маскировка номеров телефонов Microsoft Teams собраниях</span><span class="sxs-lookup"><span data-stu-id="2127a-103">Mask phone numbers in Microsoft Teams meetings</span></span>

<span data-ttu-id="2127a-104">Для обеспечения конфиденциальности номера телефонов участников, которые используют Teams аудиоконференцию, полностью отображаются внутренним участникам.</span><span class="sxs-lookup"><span data-stu-id="2127a-104">For added privacy, the phone numbers of participants who dial in to a Teams meeting using audio conferencing are fully displayed to the internal participants.</span></span> <span data-ttu-id="2127a-105">Эти числа маскироваться от участников за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2127a-105">The numbers are masked from the participants outside of your organization.</span></span> <span data-ttu-id="2127a-106">Этот параметр по умолчанию для всех организаций.</span><span class="sxs-lookup"><span data-stu-id="2127a-106">This setting is the default for all organizations.</span></span> <span data-ttu-id="2127a-107">Маскировка отображается, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="2127a-107">The masked number is displayed as shown in the following image:</span></span>

![Пример маскировки номера телефона](media/hiddenPhoneNum.png)

<span data-ttu-id="2127a-109">В определенных случаях использования в отрасли администраторы могут выбрать, как номера телефонов участников аудиоконференции будут отображаться на собраниях, организованных в их клиенте.</span><span class="sxs-lookup"><span data-stu-id="2127a-109">For specific industry use cases, admins have the ability to choose how the audio conferencing participants' phone numbers appear in meetings that are organized in their tenant.</span></span> <span data-ttu-id="2127a-110">Администраторы могут выбрать один из трех вариантов:</span><span class="sxs-lookup"><span data-stu-id="2127a-110">The admins can choose from three options:</span></span>

- <span data-ttu-id="2127a-111">Телефон номера маскироваться только от внешних участников.</span><span class="sxs-lookup"><span data-stu-id="2127a-111">Phone numbers are masked only from external participants.</span></span> <span data-ttu-id="2127a-112">Участники, которые входят в клиент организатора собрания, по-прежнему видят полный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="2127a-112">The participants who belong to the meeting organizer's tenant still see the full phone number.</span></span>
- <span data-ttu-id="2127a-113">Телефон всех на собрании, кроме организатора, в масках.</span><span class="sxs-lookup"><span data-stu-id="2127a-113">Phone numbers are masked from everyone in the meeting except the organizer.</span></span>
- <span data-ttu-id="2127a-114">Телефон будут отсвечены, что делает их видимыми для всех на собрании.</span><span class="sxs-lookup"><span data-stu-id="2127a-114">Phone numbers are unmasked, which makes them visible to everyone in the meeting.</span></span>

<span data-ttu-id="2127a-115">Этот параметр применяется во всех поверхностях собрания, где вы можете получить номера телефонов.</span><span class="sxs-lookup"><span data-stu-id="2127a-115">This setting is applied to all the surfaces in the meeting where phone numbers are exposed.</span></span>

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a><span data-ttu-id="2127a-116">Настройка маски для номеров телефонов с помощью Microsoft PowerShell</span><span class="sxs-lookup"><span data-stu-id="2127a-116">Use Microsoft PowerShell to set phone-number masking</span></span>

<span data-ttu-id="2127a-117">Чтобы изменить параметр маскировки телефонной сети общего перейти на другой телефон (ОКП), задате один из доступных параметров для параметра **`MaskPstnNumbersType`** [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="2127a-117">To change the Public Switched Telephone Network (PSTN) masking setting, set the **`MaskPstnNumbersType`** parameter of the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to one of the available options.</span></span>

<span data-ttu-id="2127a-118">Чтобы скрыть телефонные номера только внешних участников, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2127a-118">To mask phone numbers only from external participants, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

<span data-ttu-id="2127a-119">Чтобы скрыть телефонные номера всех участников собрания (кроме организатора), запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2127a-119">To mask phone numbers from all participants in the meeting (except the organizer), run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

<span data-ttu-id="2127a-120">Чтобы отключить маску номеров телефонов, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2127a-120">To disable phone number masking, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```