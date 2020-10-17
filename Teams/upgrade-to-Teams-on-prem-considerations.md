---
title: Переход на Teams из локального развертывания Skype для бизнеса (Microsoft Teams)
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
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a><span data-ttu-id="eae43-103">Рекомендации по обновлению для организаций с локальной версией Skype для бизнеса Server &mdash; для ИТ-администраторов</span><span class="sxs-lookup"><span data-stu-id="eae43-103">Upgrade considerations for organizations with Skype for Business Server on-premises &mdash; for IT administrators</span></span>

<span data-ttu-id="eae43-104">В этой статье описаны дополнительные вопросы для организаций с локальным приложением Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="eae43-104">This article describes additional considerations for organizations with Skype for Business Server on-premises.</span></span> <span data-ttu-id="eae43-105">Эта статья является четвертой из нескольких описанных выше принципов и реализации обновлений для ИТ – администраторов.</span><span class="sxs-lookup"><span data-stu-id="eae43-105">This article is the fourth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="eae43-106">Обзор</span><span class="sxs-lookup"><span data-stu-id="eae43-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="eae43-107">Способы обновления</span><span class="sxs-lookup"><span data-stu-id="eae43-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="eae43-108">Инструменты для управления обновлением</span><span class="sxs-lookup"><span data-stu-id="eae43-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- <span data-ttu-id="eae43-109">**Дополнительные рекомендации для организаций с локальными приложениями Skype для бизнеса (в** этой статье)</span><span class="sxs-lookup"><span data-stu-id="eae43-109">**Additional considerations for organizations with Skype for Business on-premises** (this article)</span></span>
- [<span data-ttu-id="eae43-110">Реализация обновления</span><span class="sxs-lookup"><span data-stu-id="eae43-110">Implementing your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="eae43-111">Общие сведения о коммутируемых телефонных сетях (КТСОП)</span><span class="sxs-lookup"><span data-stu-id="eae43-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="eae43-112">Кроме того, в следующих статьях описаны важные концепции обновления и поведение сосуществования.</span><span class="sxs-lookup"><span data-stu-id="eae43-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="eae43-113">Сосуществование Teams и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="eae43-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="eae43-114">Режимы сосуществования — справочные материалы</span><span class="sxs-lookup"><span data-stu-id="eae43-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="eae43-115">Взаимодействие с клиентом Teams и соответствие режимам сосуществования</span><span class="sxs-lookup"><span data-stu-id="eae43-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a><span data-ttu-id="eae43-116">Рекомендации для организаций с локальным подключением Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="eae43-116">Considerations for organizations with Skype for Business Server on-premises</span></span>

- <span data-ttu-id="eae43-117">Настройка гибридного развертывания Skype для бизнеса является обязательным условием для перехода в режим TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="eae43-117">Setting up Skype for Business hybrid is a prerequisite to migrate to TeamsOnly mode.</span></span> <span data-ttu-id="eae43-118">Несмотря на то что вы можете использовать Teams в режиме "острова" без гибридного развертывания, переход в режим TeamsOnly невозможно, пока пользователь не перейдет из Skype для бизнеса локально в Skype для бизнеса Online (с помощью функции [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span><span class="sxs-lookup"><span data-stu-id="eae43-118">While it is possible to use Teams in Islands mode without hybrid, the transition to TeamsOnly mode cannot be made until the user is moved from Skype for Business on-premises to Skype for Business Online (using [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span></span> <span data-ttu-id="eae43-119">Дополнительные сведения можно найти в разделе [Настройка гибридного подключения](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span><span class="sxs-lookup"><span data-stu-id="eae43-119">For more information, see [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span></span>

- <span data-ttu-id="eae43-120">Если в вашей организации используется приложение Skype для бизнеса и вы не настроили гибридное подключение, но вы по-прежнему хотите использовать Teams для управления функциями Teams, необходимо использовать учетную запись администратора с onmicrosoft.com доменом.</span><span class="sxs-lookup"><span data-stu-id="eae43-120">If your organization has Skype for Business Server and you have not configured hybrid connectivity, but you still want to use Teams, to administer Teams functionality, you must use an administrative account that has an .onmicrosoft.com domain.</span></span> 

- <span data-ttu-id="eae43-121">Пользователи Teams, у которых есть учетная запись Skype для бизнеса, локально (то есть они еще не были перемещены в облако с помощью функции Move-CsUser), не могут взаимодействовать с пользователями Skype для бизнеса, а также не могут использовать их вместе с внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="eae43-121">Teams users who have a Skype for Business account on-premises (that is, they have not yet been moved to the cloud by using Move-CsUser) cannot interoperate with any Skype for Business users, nor can they federate with external users.</span></span> <span data-ttu-id="eae43-122">Эта функция доступна только в том случае, если пользователи перемещаются в облако (как в режиме острова, так и в качестве пользователей TeamsOnly).</span><span class="sxs-lookup"><span data-stu-id="eae43-122">This functionality is only available once the users are moved to the cloud (either in Islands mode, or as TeamsOnly users).</span></span> 

- <span data-ttu-id="eae43-123">Если у вас есть пользователи с локальными учетными записями Skype для бизнеса, вы не сможете назначить режим TeamsOnly на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="eae43-123">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="eae43-124">Вы должны сначала переместить всех пользователей с локальными учетными записями Skype для бизнеса в облако с помощью `Move-CsUser` и затем [Отключить гибридную среду для завершения миграции в облако](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span><span class="sxs-lookup"><span data-stu-id="eae43-124">You must first move all  users with on-premises Skype for Business accounts to the cloud using `Move-CsUser` and then [disable hybrid to complete migration to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>  <span data-ttu-id="eae43-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` не будет работать на уровне клиента, если обнаружена DNS-запись lyncdiscover, указывающая на расположение, отличное от Office 365.</span><span class="sxs-lookup"><span data-stu-id="eae43-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` will not work at the tenant level if a lyncdiscover DNS record is detected that points to a location other than Office 365.</span></span>

- <span data-ttu-id="eae43-126">Вы должны убедиться, что ваши пользователи правильно синхронизируются с Azure AD с правильными атрибутами Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="eae43-126">You must ensure your users are properly synchronized into Azure AD with the correct Skype for Business attributes.</span></span> <span data-ttu-id="eae43-127">Эти атрибуты являются всеми префиксами с помощью "msRTCSIP-".</span><span class="sxs-lookup"><span data-stu-id="eae43-127">These attributes are all prefixes with “msRTCSIP-”.</span></span> <span data-ttu-id="eae43-128">Если пользователи не будут правильно синхронизованы с Azure AD, средства управления в Teams не смогут управлять этими пользователями.</span><span class="sxs-lookup"><span data-stu-id="eae43-128">If users are not synchronized properly to Azure AD, the management tools in Teams will not be able to manage these users.</span></span> <span data-ttu-id="eae43-129">(Например, вы не сможете назначать политики для локальных пользователей, если только они не синхронизируются должным образом.) Дополнительные сведения можно найти в разделе [Настройка Azure AD Connect для Teams и Skype для бизнеса](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="eae43-129">(For example, you won’t be able to assign Teams policies to on-premises users unless you are properly syncing these attributes.) For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span></span>

- <span data-ttu-id="eae43-130">Чтобы создать в гибридной организации нового пользователя TeamsOnly или Skype для бизнеса Online, *необходимо сначала включить пользователя в локальной среде Skype для бизнеса Server*, а затем переместить пользователя из локальной сети в облако с помощью функции Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="eae43-130">To create a new TeamsOnly or Skype for Business Online user in a hybrid organization, *you must first enable the user in Skype for Business Server on-premises*, and then move the user from on-premises to the cloud using Move-CsUser.</span></span>  <span data-ttu-id="eae43-131">Предварительное создание пользователя в локальной системе гарантирует, что все остальные пользователи Skype для бизнеса смогут перенаправляться на только что созданному пользователю.</span><span class="sxs-lookup"><span data-stu-id="eae43-131">Creating the user in on-premises first ensures that any other remaining on-premises Skype for Business users will be able route to the newly created user.</span></span> <span data-ttu-id="eae43-132">После того как все пользователи будут перемещены в сеть, вам больше не нужно, чтобы они были включены в локальную версию.</span><span class="sxs-lookup"><span data-stu-id="eae43-132">Once all users have been moved online, it is no longer necessary to first enable users in on-premises.</span></span>

- <span data-ttu-id="eae43-133">Когда пользователь перемещается из локальной сети в облако, собрания, упорядоченные по этому пользователю, переносятся в Skype для бизнеса Online или Teams, в зависимости от того, указан ли параметр-MoveToTeams.</span><span class="sxs-lookup"><span data-stu-id="eae43-133">When a user is moved from on-premises to the cloud, meetings organized by that user are migrated to either Skype for Business Online or Teams--depending on whether or not the -MoveToTeams switch is specified.</span></span>

- <span data-ttu-id="eae43-134">Если вы хотите, чтобы уведомления отображались в клиенте Skype для бизнеса для локальных пользователей, необходимо использовать TeamsUpgradePolicy в локальном наборе инструментов.</span><span class="sxs-lookup"><span data-stu-id="eae43-134">If you would like display notifications in the Skype for Business client for on-premises users, you must use TeamsUpgradePolicy in the on-premises toolset.</span></span> <span data-ttu-id="eae43-135">Для локальных пользователей применим только параметр NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="eae43-135">Only the NotifySfbUsers parameter is relevant for on-premises users.</span></span>  <span data-ttu-id="eae43-136">Локальные пользователи получают доступ к своим режимам из Интернет-экземпляров TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="eae43-136">On-premises users receive their mode from the online instances of TeamsUpgradePolicy.</span></span> <span data-ttu-id="eae43-137">Ознакомьтесь с заметками в [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="eae43-137">See the notes in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> 

>[!NOTE]
> <span data-ttu-id="eae43-138">Все новые клиенты, созданные после сентября 3, 2019 создаются как клиенты TeamsOnly, если в Организации уже не настроено локальное развертывание Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="eae43-138">Any new tenants created after Sept 3, 2019 are created as TeamsOnly tenants unless the organization already has an on-premises deployment of Skype for Business Server.</span></span> <span data-ttu-id="eae43-139">Корпорация Майкрософт использует записи DNS для идентификации локальных организаций в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="eae43-139">Microsoft uses DNS records to identify on-premises Skype for Business Server organizations.</span></span> <span data-ttu-id="eae43-140">Если в вашей организации есть локальный сервер Skype для бизнеса, в котором нет общедоступных DNS-записей, вам потребуется позвонить в службу поддержки Майкрософт, чтобы понизить уровень нового клиента.</span><span class="sxs-lookup"><span data-stu-id="eae43-140">If your organization has on-premises Skype for Business Server with no public DNS entries, you will need to call Microsoft Support to have your new tenant downgraded.</span></span> 













## <a name="related-links"></a><span data-ttu-id="eae43-141">Дополнительные ссылки</span><span class="sxs-lookup"><span data-stu-id="eae43-141">Related links</span></span>

[<span data-ttu-id="eae43-142">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="eae43-142">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="eae43-143">Настройка гибридной связи между Skype для бизнеса Server и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="eae43-143">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="eae43-144">Перемещение пользователей между локальной средой и облаком</span><span class="sxs-lookup"><span data-stu-id="eae43-144">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="eae43-145">Настройка сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="eae43-145">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="eae43-146">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="eae43-146">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="eae43-147">Использование службы миграции собраний (MMS)</span><span class="sxs-lookup"><span data-stu-id="eae43-147">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

