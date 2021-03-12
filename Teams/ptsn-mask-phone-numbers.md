---
title: Маскировка номеров телефонов в собраниях Microsoft Teams
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
description: Узнайте, как скрыть номера телефонов в собраниях Microsoft Teams
ms.openlocfilehash: 5a59ef07873660e79d6c8bc69b7e92095a2fac1a
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726798"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a><span data-ttu-id="e5c17-103">Маскировка номеров телефонов в собраниях Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e5c17-103">Mask phone numbers in Microsoft Teams meetings</span></span>

<span data-ttu-id="e5c17-104">Для обеспечения конфиденциальности номера телефонов участников, которые используют аудиоконференцию, полностью отображаются для внутренних участников.</span><span class="sxs-lookup"><span data-stu-id="e5c17-104">For added privacy, the phone numbers of participants who dial in to a Teams meeting using audio conferencing are fully displayed to the internal participants.</span></span> <span data-ttu-id="e5c17-105">Эти номера маскироваться от участников за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e5c17-105">The numbers are masked from the participants outside of your organization.</span></span> <span data-ttu-id="e5c17-106">Этот параметр по умолчанию для всех организаций.</span><span class="sxs-lookup"><span data-stu-id="e5c17-106">This setting is the default for all organizations.</span></span> <span data-ttu-id="e5c17-107">Маскировка отображается, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="e5c17-107">The masked number is displayed as shown in the following image:</span></span>

![Пример маскировки номера телефона](media/hiddenPhoneNum.png)

<span data-ttu-id="e5c17-109">В определенных отраслевых случаях использования администраторы могут выбирать, как номера телефонов участников аудиоконференции отображаются в собраниях, организованных в их клиенте.</span><span class="sxs-lookup"><span data-stu-id="e5c17-109">For specific industry use cases, admins have the ability to choose how the audio conferencing participants' phone numbers appear in meetings that are organized in their tenant.</span></span> <span data-ttu-id="e5c17-110">Администраторы могут выбрать один из трех вариантов:</span><span class="sxs-lookup"><span data-stu-id="e5c17-110">The admins can choose from three options:</span></span>

- <span data-ttu-id="e5c17-111">Номера телефонов маскируется только от внешних участников.</span><span class="sxs-lookup"><span data-stu-id="e5c17-111">Phone numbers are masked only from external participants.</span></span> <span data-ttu-id="e5c17-112">Участники, в которых состоит клиент организатора собрания, по-прежнему видят полный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="e5c17-112">The participants who belong to the meeting organizer's tenant still see the full phone number.</span></span>
- <span data-ttu-id="e5c17-113">Номера телефонов маскироваться от всех в собрании, кроме организатора.</span><span class="sxs-lookup"><span data-stu-id="e5c17-113">Phone numbers are masked from everyone in the meeting except the organizer.</span></span>
- <span data-ttu-id="e5c17-114">При этом будут отсвечены номера телефонов, что делает их видимыми для всех в собрании.</span><span class="sxs-lookup"><span data-stu-id="e5c17-114">Phone numbers are unmasked, which makes them visible to everyone in the meeting.</span></span>

<span data-ttu-id="e5c17-115">Этот параметр применяется на всех поверхностях собрания, где вы можете получить телефонные номера.</span><span class="sxs-lookup"><span data-stu-id="e5c17-115">This setting is applied to all the surfaces in the meeting where phone numbers are exposed.</span></span>

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a><span data-ttu-id="e5c17-116">Настройка маскровки номеров телефонов с помощью Microsoft PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5c17-116">Use Microsoft PowerShell to set phone-number masking</span></span>

<span data-ttu-id="e5c17-117">Чтобы изменить параметр маскровки телефонной сети общего перейти на другой телефонную сеть (STN), задате один из доступных параметров для параметра **`MaskPstnNumbersType`** [Set-CsOnlineDialInConferencingTenantSettings.](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e5c17-117">To change the Public Switched Telephone Network (PSTN) masking setting, set the **`MaskPstnNumbersType`** parameter of the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to one of the available options.</span></span>

<span data-ttu-id="e5c17-118">Чтобы скрыть номера телефонов только от внешних участников, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e5c17-118">To mask phone numbers only from external participants, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

<span data-ttu-id="e5c17-119">Чтобы скрыть номера телефонов от всех участников собрания (кроме организатора), запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e5c17-119">To mask phone numbers from all participants in the meeting (except the organizer), run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

<span data-ttu-id="e5c17-120">Чтобы отключить маскировку номеров телефонов, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e5c17-120">To disable phone number masking, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```
