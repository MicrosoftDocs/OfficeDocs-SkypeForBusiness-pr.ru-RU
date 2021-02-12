---
title: Обновление до Teams из локального развертывания Skype для бизнеса — Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
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
ms.openlocfilehash: 0fe5bb56979b9b4b430076602e76ece595b8661f
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578402"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="ed78c-103">Обновление Skype для бизнеса до Teams &mdash; для ИТ-администраторов</span><span class="sxs-lookup"><span data-stu-id="ed78c-103">Upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

## <a name="overview"></a><span data-ttu-id="ed78c-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="ed78c-104">Overview</span></span>

<span data-ttu-id="ed78c-105">При переходе со Skype для бизнеса на Teams в некоторых организациях требуется постепенное обновление, которое планируется и управляется ИТ-отделом.</span><span class="sxs-lookup"><span data-stu-id="ed78c-105">When upgrading from Skype for Business to Teams, some organizations require a progressive rollout that is planned and managed by their IT departments.</span></span> <span data-ttu-id="ed78c-106">Статьи в этом разделе в основном касаются ИТ-администраторов крупных организаций.</span><span class="sxs-lookup"><span data-stu-id="ed78c-106">The articles in this section apply primarily to IT administrators in large organizations.</span></span> <span data-ttu-id="ed78c-107">Эти организации обычно являются локальной, но, возможно, они также являются крупными организациями Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="ed78c-107">These organizations are typically on-premises, but they might also be large Skype for Business Online organizations.</span></span> <span data-ttu-id="ed78c-108">Прежде чем прочитать эти статьи, ознакомьтесь со статьями "Начало работы с обновлением [Teams"](upgrade-start-here.md) и ["Об обновлении".](upgrade-framework.md)</span><span class="sxs-lookup"><span data-stu-id="ed78c-108">Before reading these articles, be sure to read [Getting started with your Teams Upgrade](upgrade-start-here.md) and [About the Upgrade framework](upgrade-framework.md).</span></span>


<span data-ttu-id="ed78c-109">В следующих статьях вы можете перейти на следующую статью:</span><span class="sxs-lookup"><span data-stu-id="ed78c-109">The following articles will guide you through the upgrade process for your organization:</span></span> 

- [<span data-ttu-id="ed78c-110">Способы обновления</span><span class="sxs-lookup"><span data-stu-id="ed78c-110">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="ed78c-111">Инструменты для управления обновлением</span><span class="sxs-lookup"><span data-stu-id="ed78c-111">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="ed78c-112">Дополнительные соображения для организаций с локальной учетной записью Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ed78c-112">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="ed78c-113">Реализация перехода</span><span class="sxs-lookup"><span data-stu-id="ed78c-113">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="ed78c-114">Вопросы, которые следует учесть при переходе на телефонную сеть общего перейти на телефонную сеть (ПС)</span><span class="sxs-lookup"><span data-stu-id="ed78c-114">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="ed78c-115">Кроме того, в следующих статьях описаны важные понятия обновления и принципы сосуществования.</span><span class="sxs-lookup"><span data-stu-id="ed78c-115">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="ed78c-116">Совместное сосуществование Teams и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ed78c-116">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="ed78c-117">Режимы сосуществования — ссылки</span><span class="sxs-lookup"><span data-stu-id="ed78c-117">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="ed78c-118">Взаимодействие с клиентом Teams и соответствие режимам сосуществования</span><span class="sxs-lookup"><span data-stu-id="ed78c-118">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
><span data-ttu-id="ed78c-119">В этих статьях используются условия использования Skype для бизнеса Online, локального сервера Skype для бизнеса и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ed78c-119">These articles use the terms Skype for Business Online, Skype for Business Server on-premises, and Skype for Business.</span></span> <span data-ttu-id="ed78c-120">Последний термин относится как к сетевым, так и к локальной версиям.</span><span class="sxs-lookup"><span data-stu-id="ed78c-120">The latter term refers to both online and on-premises versions.</span></span>

<span data-ttu-id="ed78c-121">Прежде чем начать, вам следует знать, что пользователь, перенесенный в Teams, больше не использует клиент Skype для бизнеса, кроме звонков к собранию, которое проходит в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ed78c-121">Before you get started, be aware that a user who has been migrated to Teams no longer uses a Skype for Business client except to join a meeting hosted in Skype for Business.</span></span>  <span data-ttu-id="ed78c-122">Все входящие чаты и звонки отправляются в клиент Teams пользователя, независимо от того, использует ли отправитель Teams или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ed78c-122">All incoming chats and calls land in the user’s Teams client, regardless of whether the sender uses Teams or Skype for Business.</span></span> <span data-ttu-id="ed78c-123">Новые собрания, организованные перенесенным пользователем, будут запланированы как собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="ed78c-123">Any new meetings organized by the migrated user will be scheduled as Teams meetings.</span></span> <span data-ttu-id="ed78c-124">При попытке пользователя использовать клиент Skype для бизнеса, начало чатов и звонков блокируется.</span><span class="sxs-lookup"><span data-stu-id="ed78c-124">If the user attempts to use the Skype for Business client, initiation of chats and calls is blocked.</span></span>  <span data-ttu-id="ed78c-125">Однако пользователь может (и должен) по-прежнему использовать клиент Skype для бизнеса, чтобы присоединяться к собраниям Skype для бизнеса, на которые он приглашен.</span><span class="sxs-lookup"><span data-stu-id="ed78c-125">However, the user can (and must) still use the Skype for Business client to join Skype for Business meetings they are invited to.</span></span> <span data-ttu-id="ed78c-126">(Старые клиенты Skype для бизнеса, которые были отправлены до 2017 г., не будут использовать TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="ed78c-126">(Older Skype for Business clients that shipped before 2017 do not honor TeamsUpgradePolicy.</span></span> <span data-ttu-id="ed78c-127">Убедитесь, что вы используете последнюю версию клиента Skype для бизнеса.)</span><span class="sxs-lookup"><span data-stu-id="ed78c-127">Make sure you are using the latest Skype for Business client.)</span></span>
 
<span data-ttu-id="ed78c-128">Вы управляете переходом пользователя на Teams с помощью концепции [режима,](migration-interop-guidance-for-teams-with-skype.md)которое является свойством [TeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ed78c-128">You manage your user's transition to Teams using the concept of [mode](migration-interop-guidance-for-teams-with-skype.md), which is a property of [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> <span data-ttu-id="ed78c-129">Пользователь, который был перенесен в Teams, как описано выше, находится в режиме TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ed78c-129">A user who has been migrated to Teams as described above is in “TeamsOnly” mode.</span></span>  <span data-ttu-id="ed78c-130">В организации, которая перейдет на Teams, конечная цель — переместить всех пользователей в режим TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ed78c-130">For an organization that is migrating to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span>

>[!NOTE]
><span data-ttu-id="ed78c-131">Пользователи с локальной учетной записью Skype для бизнеса не могут использовать TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ed78c-131">Users who have a Skype for Business on-premises account cannot be TeamsOnly.</span></span> <span data-ttu-id="ed78c-132">Хотя эти пользователи могут [использовать Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)в режиме "О-ва", это не дает полный набор функций Teams, доступных в режиме TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ed78c-132">Although these users can [use Teams in Islands mode](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype), this does not provide the full set of Teams functionality that is available in TeamsOnly mode.</span></span> <span data-ttu-id="ed78c-133">Чтобы этих пользователей можно было использовать в TeamsOnly, их необходимо перенести в облако с помощью локального средства `Move-CsUser` Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ed78c-133">To make these users TeamsOnly, they must be moved to the cloud using `Move-CsUser` in the on-premises Skype for Business Server tools.</span></span>

<span data-ttu-id="ed78c-134">Хорошо.</span><span class="sxs-lookup"><span data-stu-id="ed78c-134">OK.</span></span> <span data-ttu-id="ed78c-135">Давайте начнем.</span><span class="sxs-lookup"><span data-stu-id="ed78c-135">Let's get started.</span></span>  <span data-ttu-id="ed78c-136">Прежде всего нужно понять, какие методы [обновления доступны вам.](upgrade-to-teams-on-prem-upgrade-methods.md)</span><span class="sxs-lookup"><span data-stu-id="ed78c-136">The first step is understanding the [upgrade methods available to you](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>







   

## <a name="related-links"></a><span data-ttu-id="ed78c-137">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ed78c-137">Related links</span></span>

[<span data-ttu-id="ed78c-138">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ed78c-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="ed78c-139">Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="ed78c-139">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="ed78c-140">Перемещение пользователей между локальной средой и облаком</span><span class="sxs-lookup"><span data-stu-id="ed78c-140">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="ed78c-141">Настройка сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="ed78c-141">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="ed78c-142">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="ed78c-142">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="ed78c-143">Использование службы переноса собраний (MMS)</span><span class="sxs-lookup"><span data-stu-id="ed78c-143">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

