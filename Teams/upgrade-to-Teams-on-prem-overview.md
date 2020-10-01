---
title: Переход на Teams из локального развертывания Skype для бизнеса (Microsoft Teams)
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Переход со Skype для бизнеса на Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8030f1504e56fb6bd9aee528e7969c9d66bf8c96
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328238"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="30b82-103">Переход с Skype для бизнеса на Teams &mdash; для ИТ-администраторов</span><span class="sxs-lookup"><span data-stu-id="30b82-103">Upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

## <a name="overview"></a><span data-ttu-id="30b82-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="30b82-104">Overview</span></span>

<span data-ttu-id="30b82-105">При переходе с Skype для бизнеса на Teams для некоторых организаций требуется прогрессивный выпуск, который планируется и управляется ИТ-подразделениями.</span><span class="sxs-lookup"><span data-stu-id="30b82-105">When upgrading from Skype for Business to Teams, some organizations require a progressive rollout that is planned and managed by their IT departments.</span></span> <span data-ttu-id="30b82-106">Статьи в этом разделе предназначены преимущественно для ИТ – администраторов в крупных организациях.</span><span class="sxs-lookup"><span data-stu-id="30b82-106">The articles in this section apply primarily to IT administrators in large organizations.</span></span> <span data-ttu-id="30b82-107">Эти организации обычно являются локальными, но они также могут быть крупными организациями Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="30b82-107">These organizations are typically on-premises, but they might also be large Skype for Business Online organizations.</span></span> <span data-ttu-id="30b82-108">Перед тем как читать эти статьи, ознакомьтесь со статьей начало [работы с обновлением Teams](upgrade-start-here.md) и [средой обновления](upgrade-framework.md).</span><span class="sxs-lookup"><span data-stu-id="30b82-108">Before reading these articles, be sure to read [Getting started with your Teams Upgrade](upgrade-start-here.md) and [About the Upgrade framework](upgrade-framework.md).</span></span>


<span data-ttu-id="30b82-109">В следующих статьях вы найдете инструкции по обновлению для своей организации:</span><span class="sxs-lookup"><span data-stu-id="30b82-109">The following articles will guide you through the upgrade process for your organization:</span></span> 

- [<span data-ttu-id="30b82-110">Способы обновления</span><span class="sxs-lookup"><span data-stu-id="30b82-110">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="30b82-111">Инструменты для управления обновлением</span><span class="sxs-lookup"><span data-stu-id="30b82-111">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="30b82-112">Дополнительные рекомендации для организаций с локальными приложениями Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="30b82-112">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="30b82-113">Реализация перехода</span><span class="sxs-lookup"><span data-stu-id="30b82-113">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="30b82-114">Общие сведения о коммутируемых телефонных сетях (КТСОП)</span><span class="sxs-lookup"><span data-stu-id="30b82-114">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="30b82-115">Кроме того, в следующих статьях описаны важные концепции обновления и поведение сосуществования.</span><span class="sxs-lookup"><span data-stu-id="30b82-115">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="30b82-116">Сосуществование Teams и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="30b82-116">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="30b82-117">Режимы сосуществования — справочные материалы</span><span class="sxs-lookup"><span data-stu-id="30b82-117">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="30b82-118">Взаимодействие с клиентом Teams и соответствие режимам сосуществования</span><span class="sxs-lookup"><span data-stu-id="30b82-118">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
><span data-ttu-id="30b82-119">В этих статьях используются условия использования Skype для бизнеса Online, Skype для бизнеса Server и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="30b82-119">These articles use the terms Skype for Business Online, Skype for Business Server on-premises, and Skype for Business.</span></span> <span data-ttu-id="30b82-120">Последний термин относится как к сети, так и к локальным версиям.</span><span class="sxs-lookup"><span data-stu-id="30b82-120">The latter term refers to both online and on-premises versions.</span></span>

<span data-ttu-id="30b82-121">Прежде чем приступить к работе, имейте в виду, что пользователь, который выполнил миграцию в Teams, больше не использует клиент Skype для бизнеса, за исключением присоединения к собранию, размещенному в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="30b82-121">Before you get started, be aware that a user who has been migrated to Teams no longer uses a Skype for Business client except to join a meeting hosted in Skype for Business.</span></span>  <span data-ttu-id="30b82-122">Все входящие разговоры и звонки, находящиеся в клиенте Teams пользователя, независимо от того, использует ли отправитель Teams или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="30b82-122">All incoming chats and calls land in the user’s Teams client, regardless of whether the sender uses Teams or Skype for Business.</span></span> <span data-ttu-id="30b82-123">Все новые собрания, упорядоченные из мигрировавших пользователей, будут планироваться как собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="30b82-123">Any new meetings organized by the migrated user will be scheduled as Teams meetings.</span></span> <span data-ttu-id="30b82-124">Если пользователь попытается использовать клиент Skype для бизнеса, инициирование чатов и звонков блокируется.</span><span class="sxs-lookup"><span data-stu-id="30b82-124">If the user attempts to use the Skype for Business client, initiation of chats and calls is blocked.</span></span>  <span data-ttu-id="30b82-125">Тем не менее, пользователь может (и должен) по-прежнему использовать клиент Skype для бизнеса для присоединения к собраниям Skype для бизнеса, на которые они приглашены.</span><span class="sxs-lookup"><span data-stu-id="30b82-125">However, the user can (and must) still use the Skype for Business client to join Skype for Business meetings they are invited to.</span></span> <span data-ttu-id="30b82-126">(Старые клиенты Skype для бизнеса, которые поставлялись до 2017, не соблюдают TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="30b82-126">(Older Skype for Business clients that shipped before 2017 do not honor TeamsUpgradePolicy.</span></span> <span data-ttu-id="30b82-127">Убедитесь, что вы используете новейшую версию клиента Skype для бизнеса.)</span><span class="sxs-lookup"><span data-stu-id="30b82-127">Make sure you are using the latest Skype for Business client.)</span></span>
 
<span data-ttu-id="30b82-128">Управление переходом пользователя в Teams осуществляется с помощью концепции [mode](migration-interop-guidance-for-teams-with-skype.md), которая является свойством [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="30b82-128">You manage your user's transition to Teams using the concept of [mode](migration-interop-guidance-for-teams-with-skype.md), which is a property of [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> <span data-ttu-id="30b82-129">Пользователь, который был перенесен в Teams, как описано выше, находится в режиме "TeamsOnly".</span><span class="sxs-lookup"><span data-stu-id="30b82-129">A user who has been migrated to Teams as described above is in “TeamsOnly” mode.</span></span>  <span data-ttu-id="30b82-130">Для Организации, которая переносится в Teams, конечная цель состоит в том, чтобы переместить всех пользователей в режим TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="30b82-130">For an organization that is migrating to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span>

>[!NOTE]
><span data-ttu-id="30b82-131">Пользователи, у которых есть учетная запись в локальной среде Skype для бизнеса, не могут быть TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="30b82-131">Users who have a Skype for Business on-premises account cannot be TeamsOnly.</span></span> <span data-ttu-id="30b82-132">Несмотря на то что эти пользователи могут [использовать Teams в режиме острова](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype), это не предоставляет полный набор функциональных возможностей Teams, доступных в режиме TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="30b82-132">Although these users can [use Teams in Islands mode](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype), this does not provide the full set of Teams functionality that is available in TeamsOnly mode.</span></span> <span data-ttu-id="30b82-133">Чтобы эти пользователи TeamsOnly, они должны быть перемещены в облако с помощью `Move-CsUser` локальных средств Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="30b82-133">To make these users TeamsOnly, they must be moved to the cloud using `Move-CsUser` in the on-premises Skype for Business Server tools.</span></span>

<span data-ttu-id="30b82-134">Хорошо.</span><span class="sxs-lookup"><span data-stu-id="30b82-134">OK.</span></span> <span data-ttu-id="30b82-135">Приступим!</span><span class="sxs-lookup"><span data-stu-id="30b82-135">Let's get started.</span></span>  <span data-ttu-id="30b82-136">Первый шаг — общее представление о [доступных вам методах обновления](upgrade-to-teams-on-prem-upgrade-methods.md).</span><span class="sxs-lookup"><span data-stu-id="30b82-136">The first step is understanding the [upgrade methods available to you](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>







   

## <a name="related-links"></a><span data-ttu-id="30b82-137">Дополнительные ссылки</span><span class="sxs-lookup"><span data-stu-id="30b82-137">Related links</span></span>

[<span data-ttu-id="30b82-138">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="30b82-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="30b82-139">Настройка гибридной связи между Skype для бизнеса Server и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="30b82-139">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="30b82-140">Перемещение пользователей между локальной средой и облаком</span><span class="sxs-lookup"><span data-stu-id="30b82-140">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="30b82-141">Настройка сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="30b82-141">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="30b82-142">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="30b82-142">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="30b82-143">Использование службы миграции собраний (MMS)</span><span class="sxs-lookup"><span data-stu-id="30b82-143">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

