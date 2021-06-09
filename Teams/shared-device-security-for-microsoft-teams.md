---
title: Руководство по безопасности для Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Руководство по безопасному использованию Microsoft Teams на общем компьютере рабочего места.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45497c824cfc20644a59e35f7812b17058f61c2c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117057"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a><span data-ttu-id="13694-103">Безопасное использование Microsoft Teams на общих компьютерах</span><span class="sxs-lookup"><span data-stu-id="13694-103">Use Microsoft Teams securely on shared computers</span></span>

<span data-ttu-id="13694-104">По возможности предприятиям *рекомендуется* использовать подход "Никому не доверяй" для клиентских устройств посредством возможностей управления устройством, проверок работоспособности и внедрения политик устройства, шифрования на уровне устройства и других функций безопасности.</span><span class="sxs-lookup"><span data-stu-id="13694-104">When possible, it is *recommended* Enterprises make use of a Zero Trust approach to client devices making use of device management capabilities, device health checks and policy enforcement, device-level encryption, and other security features.</span></span>

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="Изображение подхода Никому не доверяй c демонстрацией явной проверки, предоставления минимальных разрешений и предположения бреши в системе безопасности (основных принципов подхода "Никому не доверяй") в синих кругах.":::

<span data-ttu-id="13694-106">Администраторы могут создавать очень безопасные условия, *настаивая* на проверке, предоставляя минимальные разрешения и предполагая компрометацию, — стандарты, обеспечивающие действия, снижающие риски для пользователей и данных.</span><span class="sxs-lookup"><span data-stu-id="13694-106">Administrators can create very secure conditions by *insisting* on verification, least privilege, and by assuming compromise -- standards that lead to actions that minimize risk to both users and data.</span></span>

> [!TIP]
> <span data-ttu-id="13694-107">Более подробный анализ принципов "Никому не доверяй" см. в [этих видео](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).</span><span class="sxs-lookup"><span data-stu-id="13694-107">For a deeper examination of Zero Trust principles, see [these videos](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).</span></span>

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a><span data-ttu-id="13694-108">Советы по безопасному использованию Microsoft Teams на общем компьютере</span><span class="sxs-lookup"><span data-stu-id="13694-108">Tips for using Microsoft Teams securely from a shared computer</span></span>

<span data-ttu-id="13694-109">Признавая невозможность или нецелесообразность для каждого сценария, тем не менее администраторам важно соблюдать руководство по использованию Teams на общем компьютере или неуправляемом устройстве, прилагая для этого все усилия.</span><span class="sxs-lookup"><span data-stu-id="13694-109">Recognizing that this may not be possible or practical in all scenarios, it is still important for security administrators to follow guidance for using Teams from a shared computer or unmanaged device as best they can.</span></span>

<span data-ttu-id="13694-110">Планы по возможности сразу должны разрабатываться в соответствии с руководством.</span><span class="sxs-lookup"><span data-stu-id="13694-110">Plans should be developed to adhere to guidelines as promptly as is possible.</span></span>

1. <span data-ttu-id="13694-111">Используйте функции безопасности платформы операционной системы.</span><span class="sxs-lookup"><span data-stu-id="13694-111">Make use of Operating System platform security capabilities.</span></span>
    1. <span data-ttu-id="13694-112">Настройте операционную систему на установку автоматических обновлений, получаемых от поставщика операционной системы (для систем Майкрософт это можно сделать с помощью [**Центра обновления Windows**](https://support.microsoft.com/help/12373/windows-update-faq)).</span><span class="sxs-lookup"><span data-stu-id="13694-112">Ensure that the operating system is configured to install automatic updates from the Operating System provider (for Microsoft systems, this can be accomplished via [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)).</span></span> 
    1. <span data-ttu-id="13694-113">Включите все функции шифрования устройства, такие как [**BitLocker**](/windows/security/information-protection/bitlocker/bitlocker-overview), и используйте безопасный ключ для доступа к устройству.</span><span class="sxs-lookup"><span data-stu-id="13694-113">Ensure that any device encryption capabilities such as [**bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-overview) are enabled, and the key used to access the device is secured.</span></span>  <span data-ttu-id="13694-114">Обратите внимание, что большинство современных [**устройств с Windows 10 поддерживают BitLocker**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10).</span><span class="sxs-lookup"><span data-stu-id="13694-114">Note that most modern [**Windows 10 devices support bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10).</span></span> 
    1. <span data-ttu-id="13694-115">Используйте функции антивирусной защиты, например предоставляемые [**Защитником Windows**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), на своих устройствах.</span><span class="sxs-lookup"><span data-stu-id="13694-115">Use anti-virus capabilities such as those offered by [**Windows Defender**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) on your devices.</span></span>
    1. <span data-ttu-id="13694-116">Настоятельно рекомендуется использовать [отдельные учетные записи пользователей](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) для каждого пользователя в системе.</span><span class="sxs-lookup"><span data-stu-id="13694-116">Use of [separate user accounts](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) for each user of the system is highly recommended.</span></span>
    1. <span data-ttu-id="13694-117">*Не* предоставляйте и не используйте права администратора права для неадминистративных функций (например, для просмотра веб-страниц, запуска Teams и т. д.).</span><span class="sxs-lookup"><span data-stu-id="13694-117">*Do not* grant, or use, administrator privileges for non-administrative functions (such as browsing the web, running Teams, et cetera).</span></span>

<span data-ttu-id="13694-118">Если невозможно выполнить инструкции, указанные выше, советуем использовать дополнительные рекомендации по защите браузера:</span><span class="sxs-lookup"><span data-stu-id="13694-118">If the above guidance cannot be met, we recommend making use of additional browser security best practices:</span></span>

1. <span data-ttu-id="13694-119">Используйте возможности защиты браузера.</span><span class="sxs-lookup"><span data-stu-id="13694-119">Leverage browser security capabilities.</span></span>
    1. <span data-ttu-id="13694-120">Используйте приватные сеансы просмотров, чтобы свести к минимуму данные и журнал, сохраняемые на диске.</span><span class="sxs-lookup"><span data-stu-id="13694-120">Use private browsing sessions to minimize data and history that persists to disk.</span></span> <span data-ttu-id="13694-121">Например, используйте [просмотр InPrivate в Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [просмотр в режиме инкогнито в Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en) или возможности вашего конкретного браузера для просмотра веб-страниц в приватном режиме.</span><span class="sxs-lookup"><span data-stu-id="13694-121">For example, use [inPrivate browsing in Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [Incognito browsing in Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en), or the capabilities your specific browser for browsing privately.</span></span> 
    1. <span data-ttu-id="13694-122">Рекомендуется изменить поведение системы на включение приватного режима просмотра *по умолчанию*.</span><span class="sxs-lookup"><span data-stu-id="13694-122">Changing the system behavior to engage private browsing *by default* is recommended.</span></span> 

2. <span data-ttu-id="13694-123">Открывайте и используйте [веб-приложение Teams](https://teams.microsoft.com) (иногда называемое *веб-* клиентом), а не скачиваемый клиент Teams.</span><span class="sxs-lookup"><span data-stu-id="13694-123">Browse to and use the [Teams web app](https://teams.microsoft.com) (sometimes called the *web* client) not the downloadable Teams client.</span></span>

3. <span data-ttu-id="13694-124">После завершения использования общей системы вы должны выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="13694-124">When you are done using the shared system, you must:</span></span> 
    1. <span data-ttu-id="13694-125">[Выйдите из Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).</span><span class="sxs-lookup"><span data-stu-id="13694-125">[Sign out of Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).</span></span>
    1. <span data-ttu-id="13694-126">Закройте все вкладки и окна браузера.</span><span class="sxs-lookup"><span data-stu-id="13694-126">Close all browser tabs and windows.</span></span>
    1. <span data-ttu-id="13694-127">Выйдите из устройства.</span><span class="sxs-lookup"><span data-stu-id="13694-127">Sign out of the device.</span></span>

<span data-ttu-id="13694-128">Перечисленные выше элементы не являются исчерпывающим списком рекомендаций или элементов безопасности, охватывающих все случаи. Могут существовать дополнительные действия, применяемые в вашей среде (например, администраторы безопасности могут использовать безопасные ссылки и безопасные вложения для Teams, если вы применяете [Office 365 ATP план 1 или 2](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)).</span><span class="sxs-lookup"><span data-stu-id="13694-128">The items above are not a comprehensive list of best practices or security controls covering all cases, and there may be extra actions that can be taken in your environment, (for instance, security administrators may choose to use Safe Links and Safe Attachments for Teams if you have [Office 365 ATP Plan 1 or 2](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)).</span></span> <span data-ttu-id="13694-129">Однако эти действия являются отправной точкой для создания руководства по использованию Teams на общих устройствах.</span><span class="sxs-lookup"><span data-stu-id="13694-129">However, these steps are a starting point for building guidance for using Teams from shared devices.</span></span>

## <a name="more-information"></a><span data-ttu-id="13694-130">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="13694-130">More Information</span></span>

[<span data-ttu-id="13694-131">BitLocker в диспетчере конфигураций</span><span class="sxs-lookup"><span data-stu-id="13694-131">Bitlocker in Configuration Manager</span></span>](/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[<span data-ttu-id="13694-132">BitLocker для Windows 10 в Intune</span><span class="sxs-lookup"><span data-stu-id="13694-132">Bitlocker for Windows 10 in Intune</span></span>](/mem/intune/protect/encrypt-devices)

[<span data-ttu-id="13694-133">Безопасность конечной точки в Intune</span><span class="sxs-lookup"><span data-stu-id="13694-133">Endpoint security in Intune</span></span>](/mem/intune/protect/endpoint-security)

<span data-ttu-id="13694-134">[Включение](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) антивирусной программы в Microsoft Defender в параметрах безопасности Windows и [выполнение сканирований](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)</span><span class="sxs-lookup"><span data-stu-id="13694-134">[Enable](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender Antivirus in your Windows Security and [run scans](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)</span></span>

[<span data-ttu-id="13694-135">Статья о центре безопасности Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="13694-135">Microsoft Defender security center article</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[<span data-ttu-id="13694-136">Веб-клиент Teams/веб-приложение Teams</span><span class="sxs-lookup"><span data-stu-id="13694-136">Teams web client/teams web app</span></span>](./get-clients.md#web-client)

[<span data-ttu-id="13694-137">Безопасность и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="13694-137">Security and Microsoft Teams</span></span>](./teams-security-guide.md)