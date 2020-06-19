---
title: Исследование успеха в голосовых сообщениях в Teams contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Исследование вариантов голосовой связи в среде Teams для международной Организации
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786114"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="a5443-103">Исследование успеха Contoso: Голосовая Конференция</span><span class="sxs-lookup"><span data-stu-id="a5443-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="a5443-104">Чтобы узнать, что такое видеоконференция &mdash; , стоимость ее доступности, а также как она работает &mdash; [в Office 365 с помощью голосовой конференции](deploy-audio-conferencing-teams-landing-page.md)contoso.</span><span class="sxs-lookup"><span data-stu-id="a5443-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="a5443-105">Обзор</span><span class="sxs-lookup"><span data-stu-id="a5443-105">Overview</span></span> 

<span data-ttu-id="a5443-106">Для голосовой связи компания Contoso использует номера телефонов, которые известны в Организации, и внешне.</span><span class="sxs-lookup"><span data-stu-id="a5443-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="a5443-107">Так как компания Contoso хотела бы сохранить эти номера там, где это возможно, они проверили информацию о назначении выделенных и общих номеров телефонов для моста звуковых конференций.</span><span class="sxs-lookup"><span data-stu-id="a5443-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="a5443-108">В соответствии с их исследованием компания Contoso предвнесла следующие решения:</span><span class="sxs-lookup"><span data-stu-id="a5443-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="a5443-109">Только сегмент Генеральной совокупности, на котором регулярные телефонные конференции будут получать лицензии на голосовую конференцию.</span><span class="sxs-lookup"><span data-stu-id="a5443-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="a5443-110">Компания Contoso использует выделенные телефонные номера и переносит их на существующие номера, чтобы использовать для голосовой конференции.</span><span class="sxs-lookup"><span data-stu-id="a5443-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="a5443-111">Поскольку пользователи Contoso использовали Skype для бизнеса, а все почтовые ящики пользователей находятся в сети, для многих пользователей запланированы собрания.</span><span class="sxs-lookup"><span data-stu-id="a5443-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="a5443-112">Чтение Contoso [с помощью службы миграции собраний (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) для получения сведений о том, что существующие собрания обновляются автоматически при изменении конечных пользователей на TeamsOnly режим.</span><span class="sxs-lookup"><span data-stu-id="a5443-112">Contoso read [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="a5443-113">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="a5443-113">Configuration</span></span>

<span data-ttu-id="a5443-114">Номера телефонов, связанные с голосовой Конференцией, обозначаются как служебные номера в телефонной системе.</span><span class="sxs-lookup"><span data-stu-id="a5443-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="a5443-115">Для местоположений, использующих планы звонков, для переноса существующих номеров телефонов из телефонной платы в Office 365 компания Contoso продемонстрирует действия, описанные в статье как [получить номера служебных телефонов](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="a5443-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="a5443-116">Чтобы назначить лицензию на проведение голосовой связи конечным пользователям в техническом пилотном проекте, администратор Contoso выполнил действия, описанные в разделе [Управление параметрами голосовой конференции для вашей организации](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="a5443-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="a5443-117">Для корпоративных пилотных и переносных пользователей корпоративное лицензирование на основе групп выполнив действия, описанные в разделе [Назначение лицензий пользователям в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="a5443-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

 