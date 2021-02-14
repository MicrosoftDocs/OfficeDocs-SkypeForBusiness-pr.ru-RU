---
title: Пример дела с голосовой почтой Contoso в Teams
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
description: Пример голосовой работы Teams для многоязычной корпорации
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786114"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="29608-103">Пример работы с Contoso: аудиоконференция</span><span class="sxs-lookup"><span data-stu-id="29608-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="29608-104">Чтобы получить общее представление об аудиоконференциях, их стоимости, доступности и работе в Contoso, мы просмотрели их в &mdash; &mdash; Office [365.](deploy-audio-conferencing-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="29608-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="29608-105">Обзор</span><span class="sxs-lookup"><span data-stu-id="29608-105">Overview</span></span> 

<span data-ttu-id="29608-106">Для аудиоконференции в Contoso использовались номера телефонов, хорошо известные как для организации, так и для внешних организаций.</span><span class="sxs-lookup"><span data-stu-id="29608-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="29608-107">Так как компания Contoso хочет обслуживать эти номера по возможности, она просмотрела сведения о назначении выделенных и общих номеров телефонов мосту аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="29608-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="29608-108">На основе исследований компания Contoso принимает следующие решения:</span><span class="sxs-lookup"><span data-stu-id="29608-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="29608-109">Лицензии на аудиоконференцию получит только та часть людей, которые регулярно проводят аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="29608-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="29608-110">Contoso использует выделенные телефонные номера и переносит существующие номера для использования с аудиоконференцией.</span><span class="sxs-lookup"><span data-stu-id="29608-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="29608-111">Так как пользователи Contoso использовали Skype для бизнеса, а почтовые ящики всех пользователей находятся в сети, у многих пользователей уже запланировано собрание.</span><span class="sxs-lookup"><span data-stu-id="29608-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="29608-112">Если вы используете службу переноса собраний [(MMS),](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) contoso прочитает статью о том, что существующие собрания для Contoso обновляются автоматически при смене пользователя на режим TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="29608-112">Contoso read [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="29608-113">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="29608-113">Configuration</span></span>

<span data-ttu-id="29608-114">Телефонные номера, связанные с аудиоконференцией, называются номерами служб в телефонной системе.</span><span class="sxs-lookup"><span data-stu-id="29608-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="29608-115">Для местоположений, использующих планы звонков, для переноса существующих номеров телефонов от оператора связи в Office 365 компания Contoso, как и при получении номеров телефонов службы, придерживается [действий.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="29608-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="29608-116">Чтобы назначить лицензию на аудиоконференцию пользователю в пилотном проекте, администратор Contoso следовал за действиями, которые были предприняты в параметрах аудиоконференции для вашей [организации.](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="29608-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="29608-117">В пилотном проекте и миграции Компания Contoso использовала групповое лицензирование с помощью действий, следующих в процедуре назначения лицензий пользователям по признаку участия в группах [в Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="29608-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

 