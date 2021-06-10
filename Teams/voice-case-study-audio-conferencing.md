---
title: 'Teams голосом: пример: Contoso'
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
description: Teams на примере голосовой почты для многоязычной корпорации
appliesto:
- Microsoft Teams
ms.openlocfilehash: 085c9994bc2522d1ab56abc1670113e22d35f642
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121307"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="c68eb-103">Пример работы с Contoso: аудиоконференция</span><span class="sxs-lookup"><span data-stu-id="c68eb-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="c68eb-104">Чтобы понять, что это такое аудиоконференция, что это за затраты, доступность и как работает аудиоконференция, рассмотренная в &mdash; &mdash; Contoso в Office 365. [](deploy-audio-conferencing-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="c68eb-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="c68eb-105">Обзор</span><span class="sxs-lookup"><span data-stu-id="c68eb-105">Overview</span></span> 

<span data-ttu-id="c68eb-106">Для аудиоконференций Contoso использовали номера телефонов, хорошо известные как в организации, так и за ее внешними границами.</span><span class="sxs-lookup"><span data-stu-id="c68eb-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="c68eb-107">Так как contoso хотел сохранить эти номера по возможности, они просмотрели сведения о назначении выделенных и общих номеров телефонов мосту аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="c68eb-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="c68eb-108">На основе исследований Компания Contoso принимает следующие решения:</span><span class="sxs-lookup"><span data-stu-id="c68eb-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="c68eb-109">Лицензии на аудиоконференцию получит только та часть населения, которая регулярно принимает звонки на аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="c68eb-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="c68eb-110">Contoso использует выделенные телефонные номера и переносит существующие номера для аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="c68eb-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="c68eb-111">Так как пользователи Contoso использовали Skype для бизнеса и почтовые ящики всех пользователей находятся в сети, у многих пользователей запланировано собрание.</span><span class="sxs-lookup"><span data-stu-id="c68eb-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="c68eb-112">Contoso прочитает Статью Использование службы переноса собраний [(MMS),](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) чтобы узнать, что существующие собрания для Contoso обновляются автоматически при смене пользователя на режим TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="c68eb-112">Contoso read [Using the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="c68eb-113">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="c68eb-113">Configuration</span></span>

<span data-ttu-id="c68eb-114">Телефон, связанные с аудиоконференцией, называются номерами служб в телефонная система.</span><span class="sxs-lookup"><span data-stu-id="c68eb-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="c68eb-115">Для местоположений, использующих планы звонков, для переноса существующих номеров телефонов от своего оператора Office 365, Компания Contoso, как было последовано за действиями в области Получение номеров телефонов [службы.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="c68eb-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="c68eb-116">Чтобы назначить лицензию на аудиоконференцию конечному пользователю в техническом пилотном проекте, администратор Contoso, как и администратор Contoso, должен будет управлять настройками аудиоконференций для вашей [организации.](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="c68eb-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="c68eb-117">Для бизнес-пилотного проекта и миграции компания Contoso использовала групповое лицензирование, следуя шагам из процедуры Назначение лицензий пользователям по признаку участия в [группах Azure Active Directory.](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="c68eb-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

