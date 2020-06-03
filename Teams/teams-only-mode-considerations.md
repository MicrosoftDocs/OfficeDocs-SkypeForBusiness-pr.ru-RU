---
title: Сведения о режиме "Только Teams"
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Администратор может узнать о том, как подготовиться к обновлению в режиме "только для Microsoft Teams" в центре администрирования Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 882bb40d1d7f300f51fded6321f29bafd7f8ba92
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2020
ms.locfileid: "44522502"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="de115-103">Сведения о режиме "Только Teams"</span><span class="sxs-lookup"><span data-stu-id="de115-103">Teams Only mode considerations</span></span>

<span data-ttu-id="de115-104">Если вы являетесь администратором вашей организации Office 365, вы увидите параметр для перехода в режим "только для Teams" в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de115-104">If you are an administrator on your Office 365 organization, you will now see the option to upgrade to Teams Only mode in the Microsoft Teams admin center.</span></span> <span data-ttu-id="de115-105">С помощью этой функции можно обновить как отдельных пользователей, так и весь клиент.</span><span class="sxs-lookup"><span data-stu-id="de115-105">With this functionality you can upgrade either individual users, or alternatively, the entire tenant.</span></span>  

<span data-ttu-id="de115-106">При переходе в режим "только для Team" пользователи смогут пользоваться всеми преимуществами Microsoft Teams, основным центром для совместной работы в Office 365 с помощью одного из клиентов.</span><span class="sxs-lookup"><span data-stu-id="de115-106">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Office 365, via a single client experience.</span></span> <span data-ttu-id="de115-107">Кроме того, пользователи в режиме "только Teams" будут получать все звонки и разговоры в Teams, независимо от того, используете ли отправитель Skype для бизнеса или группы, а также от поддержки взаимодействия и Федерации.</span><span class="sxs-lookup"><span data-stu-id="de115-107">Additionally, users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="de115-108">Несмотря на то, что тысячи клиентов успешно обновились до Microsoft Teams, вы можете повлиять на временную шкалу и работу пользователей вашей организации.</span><span class="sxs-lookup"><span data-stu-id="de115-108">While thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization's upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="de115-109">В частности, возможность обновления не обязательно означает, что ваша организация готова к этим изменениям.</span><span class="sxs-lookup"><span data-stu-id="de115-109">In particular, having the option to upgrade doesn't necessarily mean your organization is ready for this change.</span></span> <span data-ttu-id="de115-110">Для максимального удобства пользователей сначала убедитесь, что Teams соответствует вашим потребностям для связи и совместной работы, а ваша сеть готова поддерживать Teams, после чего реализуйте свой план подготовки пользователей, прежде чем переводить их на Teams.</span><span class="sxs-lookup"><span data-stu-id="de115-110">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="de115-111">Если вы только начинаете планирование обновления, не забудьте ознакомиться со статьей [Приступая к работе с руководством по обновлению Microsoft Teams](upgrade-start-here.md) .</span><span class="sxs-lookup"><span data-stu-id="de115-111">If you are just starting your upgrade planning, be sure to review our [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md) guide.</span></span> 

<span data-ttu-id="de115-112">**Рекомендации по сосуществованию**: Организации, которые уже используют Skype для бизнеса Online и/или Skype для бизнеса Server, могут познакомиться с группами в своей среде, чтобы они соответствовали их требованиям.</span><span class="sxs-lookup"><span data-stu-id="de115-112">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="de115-113">Организации могут выполнять инкрементное развертывание групп для нужного набора пользователей, и пользователи, которые используют Teams, могут общаться с пользователями Skype для бизнеса и наоборот.</span><span class="sxs-lookup"><span data-stu-id="de115-113">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="de115-114">Для управления этим интерфейсом администраторы используют режимы сосуществования, определяющие взаимодействие с конечным пользователем для пользователей, маршрутизацию входящих чатов и звонков, а также планирование новых собраний в Teams или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="de115-114">To manage this experience, administrators use coexistence modes, which define the end user client experience, the routing behavior of incoming chats and calls, as well as whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="de115-115">Пользователи могут выполнять Федерацию с пользователями в других организациях, если пользователь обновлен до **Teams**; Тем не менее, наилучший интерфейс предоставляется в том случае, если оба пользователя используют Teams.</span><span class="sxs-lookup"><span data-stu-id="de115-115">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="de115-116">Пользователи, обновленные до Teams, могут присоединиться к собраниям Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="de115-116">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!NOTE]
> <span data-ttu-id="de115-117">Пользователи, обновленные до Teams, не смогут общаться с пользователями Skype для потребителей.</span><span class="sxs-lookup"><span data-stu-id="de115-117">Users who are upgraded to Teams Only cannot communicate with users who are using Skype for Consumer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de115-118">Для получения более подробной информации о сосуществовании ознакомьтесь со статьей [Знакомство с Microsoft Teams и Skype для бизнеса и их взаимодействие](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="de115-118">For more detailed information about coexistence please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> 

<span data-ttu-id="de115-119">**Вопросы на уровне клиента**: Мы работаем над включением групп в указанных ниже средах. Однако сейчас администраторы не должны обновить пользователей в своей организации, если их клиент Skype для бизнеса размещен в одной из следующих сред.</span><span class="sxs-lookup"><span data-stu-id="de115-119">**Tenant-wide considerations**: We are working on enabling Teams in the following environments; however, for now, administrators shouldn't upgrade any users in their organization if their Skype for Business tenant is hosted in one of the following environments:</span></span>

 - <span data-ttu-id="de115-120">Office 365, предоставляемый 21Vianet</span><span class="sxs-lookup"><span data-stu-id="de115-120">Office 365 operated by 21Vianet</span></span>
 - <span data-ttu-id="de115-121">Office 365 в Германии</span><span class="sxs-lookup"><span data-stu-id="de115-121">Office 365 Germany</span></span>
 - <span data-ttu-id="de115-122">Клиент Skype для бизнеса размещается в Южной Корее **, и** для организации требуется, чтобы данные Teams хранились в Южной Корее.</span><span class="sxs-lookup"><span data-stu-id="de115-122">Skype for Business tenant is hosted in South Korea **and** the organization requires Teams data to be stored in South Korea.</span></span> <span data-ttu-id="de115-123">В настоящее время Организации с данными Skype для бизнеса, которые хранятся в Южной Корее, будут иметь данные Teams, которые хранятся в регионе для стран, а не в центре обработки данных Южной зоны.</span><span class="sxs-lookup"><span data-stu-id="de115-123">Currently, organizations with Skype for Business data stored in South Korea that upgrade to Teams will have their Teams data stored in the Asia datacenter region, not in the South Korea datacenter region.</span></span>

<span data-ttu-id="de115-124">**Вопросы, связанные с пользователем**: некоторые сценарии для пользователей по-прежнему развиваются, а администраторы могут решить временно отложить обновление некоторых пользователей в Организации при обновлении других пользователей.</span><span class="sxs-lookup"><span data-stu-id="de115-124">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="de115-125">В частности, мы по-прежнему работаем над сценариями адресации для пользователей, основное устройство которых основано на VDI.</span><span class="sxs-lookup"><span data-stu-id="de115-125">In particular, we are still working on addressing scenarios for users whose primary device is VDI-based.</span></span> <span data-ttu-id="de115-126">Для просмотра извещений проследите за сайтами [планов Office 365](https://www.microsoft.com/microsoft-365/roadmap) .</span><span class="sxs-lookup"><span data-stu-id="de115-126">Please monitor the [Office 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) site for announcements.</span></span>

> [!NOTE]
> <span data-ttu-id="de115-127">Перед переходом в режим "только Teams" вам потребуется заменить или обновить устройства, не поддерживающие команды.</span><span class="sxs-lookup"><span data-stu-id="de115-127">Before you move to Teams Only mode you need to replace or update devices that don't support Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="de115-128">Не **забывайте**, что переход в Teams – это больше, чем техническая миграция.</span><span class="sxs-lookup"><span data-stu-id="de115-128">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="de115-129">Успешное обновление оценивает как техническую готовность, так и готовность конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="de115-129">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="de115-130">Ознакомьтесь с [руководством по обновлению](upgrade-framework.md) Skype для бизнеса в Teams, чтобы получить дополнительные сведения о планировании реализации обновления до Teams.</span><span class="sxs-lookup"><span data-stu-id="de115-130">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
