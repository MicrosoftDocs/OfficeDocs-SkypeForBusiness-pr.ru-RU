---
title: Обновление до Teams из локального развертывания Skype для бизнеса — Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
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
ms.openlocfilehash: cf034969c2b6ca030eede72ff358a517fafe501f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533596"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a><span data-ttu-id="41ce6-103">Вопросы обновления для организаций с локальной учетной записью Skype для бизнеса Server &mdash; для ИТ-администраторов</span><span class="sxs-lookup"><span data-stu-id="41ce6-103">Upgrade considerations for organizations with Skype for Business Server on-premises &mdash; for IT administrators</span></span>

<span data-ttu-id="41ce6-104">В этой статье описаны дополнительные факторы, которые могут учитываться для организаций с локальной учетной записью Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="41ce6-104">This article describes additional considerations for organizations with Skype for Business Server on-premises.</span></span> <span data-ttu-id="41ce6-105">Эта статья является четвертой из нескольких, в статье описаны концепции обновления и реализации для ИТ-администраторов.</span><span class="sxs-lookup"><span data-stu-id="41ce6-105">This article is the fourth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="41ce6-106">Обзор</span><span class="sxs-lookup"><span data-stu-id="41ce6-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="41ce6-107">Способы обновления</span><span class="sxs-lookup"><span data-stu-id="41ce6-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="41ce6-108">Инструменты для управления обновлением</span><span class="sxs-lookup"><span data-stu-id="41ce6-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- <span data-ttu-id="41ce6-109">**Дополнительные соображения для организаций с локальной** учетной записью Skype для бизнеса (в этой статье)</span><span class="sxs-lookup"><span data-stu-id="41ce6-109">**Additional considerations for organizations with Skype for Business on-premises** (this article)</span></span>
- [<span data-ttu-id="41ce6-110">Реализация обновления</span><span class="sxs-lookup"><span data-stu-id="41ce6-110">Implementing your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="41ce6-111">Вопросы, которые следует учесть при переходе на телефонную сеть общего перейти на телефонную сеть (ПС)</span><span class="sxs-lookup"><span data-stu-id="41ce6-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="41ce6-112">Кроме того, в следующих статьях описаны важные понятия обновления и принципы сосуществования.</span><span class="sxs-lookup"><span data-stu-id="41ce6-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="41ce6-113">Совместное сосуществование Teams и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="41ce6-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="41ce6-114">Режимы сосуществования — ссылки</span><span class="sxs-lookup"><span data-stu-id="41ce6-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="41ce6-115">Взаимодействие с клиентом Teams и соответствие режимам сосуществования</span><span class="sxs-lookup"><span data-stu-id="41ce6-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a><span data-ttu-id="41ce6-116">Вопросы, которые рассматриваются организациями, у нас есть локальное приложение Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="41ce6-116">Considerations for organizations with Skype for Business Server on-premises</span></span>

- <span data-ttu-id="41ce6-117">Для перехода в режим TeamsOnly необходимо настраивать гибридное приложение Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="41ce6-117">Setting up Skype for Business hybrid is a prerequisite to migrate to TeamsOnly mode.</span></span> <span data-ttu-id="41ce6-118">Хотя можно использовать Teams в режиме "О-ва" без гибридного решения, переход в режим TeamsOnly невозможен, пока пользователь не будет перемещен из локальной системы Skype для бизнеса в Skype для бизнеса Online (с помощью [Move-CsUser).](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)</span><span class="sxs-lookup"><span data-stu-id="41ce6-118">While it is possible to use Teams in Islands mode without hybrid, the transition to TeamsOnly mode cannot be made until the user is moved from Skype for Business on-premises to Skype for Business Online (using [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span></span> <span data-ttu-id="41ce6-119">Дополнительные сведения см. [в сведениях о настройке гибридного подключения.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="41ce6-119">For more information, see [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span></span>

- <span data-ttu-id="41ce6-120">Если в вашей организации используется Skype для бизнеса Server и вы не настроили гибридное подключение, но все равно хотите использовать Teams, для администрирования функций Teams необходимо использовать административную учетную запись с доменом .onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="41ce6-120">If your organization has Skype for Business Server and you have not configured hybrid connectivity, but you still want to use Teams, to administer Teams functionality, you must use an administrative account that has an .onmicrosoft.com domain.</span></span> 

- <span data-ttu-id="41ce6-121">Пользователи Teams с локальной учетной записью Skype для бизнеса (то есть еще не перемещены в облако с помощью Move-CsUser) не могут работать вместе с пользователями Skype для бизнеса и не могут федерировать их с внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="41ce6-121">Teams users who have a Skype for Business account on-premises (that is, they have not yet been moved to the cloud by using Move-CsUser) cannot interoperate with any Skype for Business users, nor can they federate with external users.</span></span> <span data-ttu-id="41ce6-122">Эта функция доступна только после того, как пользователи перемещаются в облако (в режиме "Острова" или как пользователи TeamsOnly).</span><span class="sxs-lookup"><span data-stu-id="41ce6-122">This functionality is only available once the users are moved to the cloud (either in Islands mode, or as TeamsOnly users).</span></span> 

- <span data-ttu-id="41ce6-123">Если у вас есть пользователи с локальной учетной записью Skype для бизнеса, вы не сможете назначить режим TeamsOnly на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="41ce6-123">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="41ce6-124">Для завершения миграции в облако необходимо сначала переместить всех пользователей с локальной учетной записью Skype для бизнеса в облако, а затем отключить гибридную `Move-CsUser` [долю.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)</span><span class="sxs-lookup"><span data-stu-id="41ce6-124">You must first move all  users with on-premises Skype for Business accounts to the cloud using `Move-CsUser` and then [disable hybrid to complete migration to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>  <span data-ttu-id="41ce6-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` не будет работать на уровне клиента, если обнаружена запись DNS lyncdiscover, которая указывает на расположение, которое не является Office 365.</span><span class="sxs-lookup"><span data-stu-id="41ce6-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` will not work at the tenant level if a lyncdiscover DNS record is detected that points to a location other than Office 365.</span></span>

- <span data-ttu-id="41ce6-126">Убедитесь, что пользователи правильно синхронизированы с Azure AD с правильными атрибутами Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="41ce6-126">You must ensure your users are properly synchronized into Azure AD with the correct Skype for Business attributes.</span></span> <span data-ttu-id="41ce6-127">Все эти атрибуты являются префиксами msRTCSIP-.</span><span class="sxs-lookup"><span data-stu-id="41ce6-127">These attributes are all prefixes with “msRTCSIP-”.</span></span> <span data-ttu-id="41ce6-128">Если пользователи не синхронизированы с Azure AD надлежащим образом, средства управления в Teams не смогут управлять этими пользователями.</span><span class="sxs-lookup"><span data-stu-id="41ce6-128">If users are not synchronized properly to Azure AD, the management tools in Teams will not be able to manage these users.</span></span> <span data-ttu-id="41ce6-129">(Например, вы не сможете назначать политики Teams пользователям локальной сети, если не синхронизируете эти атрибуты надлежащим образом.) Дополнительные сведения см. в [настройках Azure AD Connect для Teams и Skype для бизнеса.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)</span><span class="sxs-lookup"><span data-stu-id="41ce6-129">(For example, you won’t be able to assign Teams policies to on-premises users unless you are properly syncing these attributes.) For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span></span>

- <span data-ttu-id="41ce6-130">Чтобы создать нового пользователя TeamsOnly или Skype для бизнеса Online в гибридной организации, необходимо сначала включить его в локальной организации Skype для бизнеса *Server,* а затем переместить его из локальной сети в облако с помощью Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="41ce6-130">To create a new TeamsOnly or Skype for Business Online user in a hybrid organization, *you must first enable the user in Skype for Business Server on-premises*, and then move the user from on-premises to the cloud using Move-CsUser.</span></span>  <span data-ttu-id="41ce6-131">При создании пользователя в локальной сети все остальные оставшиеся пользователи Skype для бизнеса смогут перенау числеть созданному пользователю маршрут.</span><span class="sxs-lookup"><span data-stu-id="41ce6-131">Creating the user in on-premises first ensures that any other remaining on-premises Skype for Business users will be able route to the newly created user.</span></span> <span data-ttu-id="41ce6-132">После того как все пользователи будут перемещены в сеть, их не нужно сначала включить в локальной сети.</span><span class="sxs-lookup"><span data-stu-id="41ce6-132">Once all users have been moved online, it is no longer necessary to first enable users in on-premises.</span></span>

- <span data-ttu-id="41ce6-133">При перемещении пользователя из локальной службы в облако собрания, организованные этим пользователем, переносются в Skype для бизнеса Online или Teams в зависимости от того, указан ли переключатель -MoveToTeams.</span><span class="sxs-lookup"><span data-stu-id="41ce6-133">When a user is moved from on-premises to the cloud, meetings organized by that user are migrated to either Skype for Business Online or Teams--depending on whether or not the -MoveToTeams switch is specified.</span></span>

- <span data-ttu-id="41ce6-134">Если вы хотите, чтобы в клиенте Skype для бизнеса отображались уведомления для пользователей локальной сети, используйте TeamsUpgradePolicy в локальном средстве.</span><span class="sxs-lookup"><span data-stu-id="41ce6-134">If you would like display notifications in the Skype for Business client for on-premises users, you must use TeamsUpgradePolicy in the on-premises toolset.</span></span> <span data-ttu-id="41ce6-135">Для пользователей локальной сети имеет значение только параметр NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="41ce6-135">Only the NotifySfbUsers parameter is relevant for on-premises users.</span></span>  <span data-ttu-id="41ce6-136">Пользователи локальной сети получают свой режим от интернет-экземпляров TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="41ce6-136">On-premises users receive their mode from the online instances of TeamsUpgradePolicy.</span></span> <span data-ttu-id="41ce6-137">См. примечания [в Grant-CsTeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="41ce6-137">See the notes in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> 

>[!NOTE]
> <span data-ttu-id="41ce6-138">Все новые клиенты, созданные после 3 сентября 2019 г., создаются как клиенты TeamsOnly, если в организации уже есть локальное развертывание Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="41ce6-138">Any new tenants created after Sept 3, 2019 are created as TeamsOnly tenants unless the organization already has an on-premises deployment of Skype for Business Server.</span></span> <span data-ttu-id="41ce6-139">Корпорация Майкрософт использует записи DNS для идентификации локальной организации Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="41ce6-139">Microsoft uses DNS records to identify on-premises Skype for Business Server organizations.</span></span> <span data-ttu-id="41ce6-140">Если в вашей организации есть локальное приложение Skype для бизнеса Server без общедоступных записей DNS, вам потребуется позвонить в службу поддержки Майкрософт, чтобы низить градиент для нового клиента.</span><span class="sxs-lookup"><span data-stu-id="41ce6-140">If your organization has on-premises Skype for Business Server with no public DNS entries, you will need to call Microsoft Support to have your new tenant downgraded.</span></span> 













## <a name="related-links"></a><span data-ttu-id="41ce6-141">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="41ce6-141">Related links</span></span>

[<span data-ttu-id="41ce6-142">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="41ce6-142">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="41ce6-143">Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="41ce6-143">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="41ce6-144">Перемещение пользователей между локальной средой и облаком</span><span class="sxs-lookup"><span data-stu-id="41ce6-144">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="41ce6-145">Настройка сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="41ce6-145">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="41ce6-146">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="41ce6-146">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="41ce6-147">Использование службы переноса собраний (MMS)</span><span class="sxs-lookup"><span data-stu-id="41ce6-147">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

