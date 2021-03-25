---
title: Выход из собрания с выходом на телефон, чтобы другие люди могли присоединиться к собранию
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 3c2db9a5-3a19-4e19-b59e-8e5587f25d31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Организаторы собраний могут узнать, как звонить с помощью приложения Teams, чтобы другие люди могли присоединиться к собранию со своих телефонов.
ms.openlocfilehash: 55cbd5ccc9e9c364bcb829d9a392f61cbdd2f7f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119288"
---
# <a name="dialing-out-from-a-microsoft-teams-meeting-so-other-people-can-join-it"></a><span data-ttu-id="f33e2-103">Исходящие звонки, позволяющие другим людям присоединиться к собранию</span><span class="sxs-lookup"><span data-stu-id="f33e2-103">Dialing out from a Microsoft Teams meeting so other people can join it</span></span>

<span data-ttu-id="f33e2-104">Организатор собрания может звонить с помощью приложения Teams, чтобы другие люди могли присоединиться к собранию со своих телефонов.</span><span class="sxs-lookup"><span data-stu-id="f33e2-104">As the meeting organizer, you can dial out using the Teams app to let other people join the same meeting using their phones.</span></span>

<span data-ttu-id="f33e2-105">При звонках на номера телефонов рекомендуется использовать полные номера телефонов (включая код страны/региона — формат E.164).</span><span class="sxs-lookup"><span data-stu-id="f33e2-105">When you dial out to someone, we recommend that you do so using their full phone numbers (including the country/region code - E.164 format).</span></span>
  
  <span data-ttu-id="f33e2-106">Обратите внимание на то, что:</span><span class="sxs-lookup"><span data-stu-id="f33e2-106">Please note that:</span></span>

- <span data-ttu-id="f33e2-107">Вы можете звонить из teams только в том случае, если присоединились к собранию.</span><span class="sxs-lookup"><span data-stu-id="f33e2-107">You can dial out only if you join a meeting using Teams.</span></span>
- <span data-ttu-id="f33e2-108">Организатор собрания с разрешением на аудиоконференцию ИЛИ в случае, если не назначена лицензия на аудиоконференцию, может звонить на обную телефонную сеть через интернет-планы звонков или прямую маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="f33e2-108">The meeting organizer, has been enabled for audio conferencing, OR, in the case no audio conferencing license is assigned, is allowed to make calls to the public switched telephone network via online calling plans or direct routing.</span></span>
- <span data-ttu-id="f33e2-109">Организатору собрания [предоставляется политика онлайн-телефонного](/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps) дозвона, которая позволяет звонить из конференции</span><span class="sxs-lookup"><span data-stu-id="f33e2-109">The meeting organizer is [Granted an online dial out policy that enables dial out from conferencing enabled](/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="f33e2-110">Вот как можно сделать так, чтобы с номером работали:</span><span class="sxs-lookup"><span data-stu-id="f33e2-110">Here's how to get dial out to work:</span></span>

 <span data-ttu-id="f33e2-111">**Шаг 1.** На собрании воспользуйтесь кнопкой "Добавить людей" на кнопке "Добавить людей", чтобы позвонить на  ![ номер ](media/add-people-button.png) телефона.</span><span class="sxs-lookup"><span data-stu-id="f33e2-111">**Step 1:** In the meeting, use the **Add people** ![Screenshot of the Add people button](media/add-people-button.png) option to dial out to a phone number.</span></span>
 <span data-ttu-id="f33e2-112">**Шаг 2.** Введите полный номер телефона, включая код страны или региона, в поле "Пригласить человека" или **наберите номер.**</span><span class="sxs-lookup"><span data-stu-id="f33e2-112">**Step 2:** Enter the full phone number, including the country/region code in the **Invite someone or dial a number** box.</span></span>
  
![Снимок экрана: диалоговое окно "Пригласить человека или наберите номер"](media/invite-someone-box.png)
    
## <a name="supported-countries-and-regions"></a><span data-ttu-id="f33e2-114">Поддерживаемые страны и регионы</span><span class="sxs-lookup"><span data-stu-id="f33e2-114">Supported countries and regions</span></span>

<span data-ttu-id="f33e2-115">Dial-out is only available to some countries/regions.</span><span class="sxs-lookup"><span data-stu-id="f33e2-115">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="f33e2-116">Полный список см. в записи о доступности стран и регионов для аудиоконференций [и планов звонков.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="f33e2-116">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>

## <a name="allow-users-to-dial-in"></a><span data-ttu-id="f33e2-117">Разрешить пользователям звонить по телефонной сети</span><span class="sxs-lookup"><span data-stu-id="f33e2-117">Allow users to dial in</span></span>

<span data-ttu-id="f33e2-118">Если вам нужно получить инструкции о том, как позволить пользователям звонить на собрание Teams, см. номера телефонов для аудиоконференции [в Microsoft Teams.](phone-numbers-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f33e2-118">If you are looking for instructions on how to let your users dial in to a Teams meeting, please see [Phone numbers for Audio Conferencing in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>

## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="f33e2-119">Хотите узнать больше об аудиоконференции?</span><span class="sxs-lookup"><span data-stu-id="f33e2-119">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="f33e2-120">Попробуйте или приобретйте аудиоконференцию</span><span class="sxs-lookup"><span data-stu-id="f33e2-120">Try or purchase Audio Conferencing</span></span>](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
[<span data-ttu-id="f33e2-121">Лицензирование надстроек Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f33e2-121">Microsoft Teams add-on licensing</span></span>](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)