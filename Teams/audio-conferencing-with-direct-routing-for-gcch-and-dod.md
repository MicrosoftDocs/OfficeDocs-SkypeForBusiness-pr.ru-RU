---
title: Голосовые конференции с прямой маршрутизацией, GCCH и DoD
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: В этой статье рассказывается о том, как использовать голосовую конференцию с прямой маршрутизацией в GCCH и по требованию.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b8077e2bf376976c9906a8703ebd59a1d1cc23f
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141172"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="68d39-103">Аудиоконференции с прямой маршрутизацией для GCC High и DoD</span><span class="sxs-lookup"><span data-stu-id="68d39-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="68d39-104">Голосовые конференции с прямой маршрутизацией на GCC High и DoD позволяют участникам присоединяться к собраниям Teams в рамках высокоскоростной или неопределенной Организации с помощью телефонного устройства.</span><span class="sxs-lookup"><span data-stu-id="68d39-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="68d39-105">Участники собрания могут предпочесть использовать телефонное устройство для присоединения к собраниям Teams в сценариях, например при ограниченном подключении к Интернету или в том случае, если пользователи находятся в дороге, но у вас нет доступа к Teams.</span><span class="sxs-lookup"><span data-stu-id="68d39-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="68d39-106">Участники могут присоединиться к собраниям с помощью набора номера для телефонного номера в вашей организации или с помощью собрания на телефонное устройство.</span><span class="sxs-lookup"><span data-stu-id="68d39-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="68d39-107">Если вы используете голосовую конференцию с прямой маршрутизацией для GCC High и DoD, ваша организация использует собственные номера для телефонного подключения, а все телефонные номера для собраний — через прямую маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="68d39-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="68d39-108">Чтобы включить службу, организациям нужно настроить прямую маршрутизацию и настроить номера телефонов, которые можно использовать в качестве телефонных номеров для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="68d39-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="68d39-109">Требование использовать прямую переадресацию отличается от службы голосовой связи, которая предлагается для организаций с телефонным подключением, отличными от GCC и не использующей незвонку, в которой номера телефонов для подключения к службе предоставляются корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="68d39-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="68d39-110">Развертывание голосовой конференции с прямой маршрутизацией для установки GCC High и DoD</span><span class="sxs-lookup"><span data-stu-id="68d39-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="68d39-111">Шаг 1: получение голосовой конференции с прямой маршрутизацией для высокоскоростных лицензий GCC High или DoD</span><span class="sxs-lookup"><span data-stu-id="68d39-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="68d39-112">Чтобы использовать голосовую конференцию в GCC High или DoD, ваша организация и пользователи в вашей организации должны иметь возможность голосовой конференции с назначенной прямой лицензией.</span><span class="sxs-lookup"><span data-stu-id="68d39-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="68d39-113">Ниже указаны лицензии, с помощью которых вы можете включить голосовую конференцию с прямой маршрутизацией для GCC High или DoD.</span><span class="sxs-lookup"><span data-stu-id="68d39-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="68d39-114">GCC High (высокое качество): видеоконференции — более высокая лицензия на клиента для вашей организации и голосовой конференции — самые высокие лицензии для пользователей.</span><span class="sxs-lookup"><span data-stu-id="68d39-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="68d39-115">Использование голосовой связи – лицензия на клиента с помощью DoD для Организации и голосовой конференции – лицензии на использование по требованию для пользователей.</span><span class="sxs-lookup"><span data-stu-id="68d39-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="68d39-116">Для включения службы требуется лицензия клиента и хотя бы одна лицензия пользователя.</span><span class="sxs-lookup"><span data-stu-id="68d39-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="68d39-117">Вы не можете включить службу только с лицензией клиента или только с пользовательскими лицензиями.</span><span class="sxs-lookup"><span data-stu-id="68d39-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="68d39-118">Чтобы получить лицензии на обслуживание для вашего клиента и пользователей в Организации, обратитесь в группу своей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="68d39-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="68d39-119">Пользователи не могут быть включены для голосовой конференции с прямой маршрутизацией, пока не будут настроены номера телефонов для подключения.</span><span class="sxs-lookup"><span data-stu-id="68d39-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="68d39-120">Мы не рекомендуем использовать голосовую конференцию с прямой маршрутизацией для лицензий GCC High или DoD для пользователей до тех пор, пока вы не настроили номера телефонов для подключения, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="68d39-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="68d39-121">Шаг 2: Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="68d39-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="68d39-122">Чтобы настроить прямую переадресацию, ознакомьтесь со следующими статьями:</span><span class="sxs-lookup"><span data-stu-id="68d39-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="68d39-123">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="68d39-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="68d39-124">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="68d39-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="68d39-125">При настройке прямой маршрутизации не забудьте использовать полные доменные имена и порты, которые описаны в этих двух статьях.</span><span class="sxs-lookup"><span data-stu-id="68d39-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="68d39-126">Шаг 3. Настройте телефонные номера для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="68d39-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="68d39-127">Телефонные номера для телефонного подключения – это номера телефонов, которые связаны с вашим мостом для проведения голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="68d39-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="68d39-128">Эти номера используются участниками для присоединения к собраниям, которые запланированы для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="68d39-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="68d39-129">Эти номера также включаются в приглашения на собрания пользователей, которые запланируют собрания в вашей организации, и на странице "Поиск местного номера".</span><span class="sxs-lookup"><span data-stu-id="68d39-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="68d39-130">Определение номеров телефонов служб в клиенте</span><span class="sxs-lookup"><span data-stu-id="68d39-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="68d39-131">С помощью командлета PowerShell New-csHybridTelephoneNumber можно определять номера служебных служб в клиенте, которые можно использовать для маршрутизации звонков к службе голосовой связи через прямую маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="68d39-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="68d39-132">Например:</span><span class="sxs-lookup"><span data-stu-id="68d39-132">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="68d39-133">Назначение телефонных номеров служб для моста голосовой конференции в Организации</span><span class="sxs-lookup"><span data-stu-id="68d39-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="68d39-134">С помощью командлета PowerShell Register-csOnlineDialInConferencingServiceNumber вы можете назначить номера телефонов служб для моста голосовой связи в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="68d39-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="68d39-135">Вы можете просмотреть идентификатор своего моста звуковых конференций с помощью Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="68d39-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="68d39-136">Например:</span><span class="sxs-lookup"><span data-stu-id="68d39-136">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="68d39-137">Шаг 4: назначение голосовой конференции с прямой маршрутизацией для лицензий на самые высокие или нелицензионные лицензии на GCC</span><span class="sxs-lookup"><span data-stu-id="68d39-137">Step 4: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="68d39-138">Чтобы назначить голосовой конференции с прямой маршрутизацией для лицензий на самые высокие или нелицензионные лицензии GCC, ознакомьтесь с [разрешениями Назначение лицензий пользователям в Office 365 для бизнеса](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="68d39-138">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>

### <a name="step-5-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="68d39-139">Шаг 5: (необязательно) Просмотр списка номеров голосовой конференции в Teams</span><span class="sxs-lookup"><span data-stu-id="68d39-139">Step 5: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="68d39-140">Чтобы просмотреть список номеров голосовой конференц-связи в вашей организации, перейдите на вкладку [Просмотр списка номеров голосовой конференции в Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md) .</span><span class="sxs-lookup"><span data-stu-id="68d39-140">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span></span>

### <a name="step-6-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="68d39-141">Шаг 6: (необязательно) Настройка языков автосекретаря для номеров телефонов для телефонной конференции в вашей организации</span><span class="sxs-lookup"><span data-stu-id="68d39-141">Step 6: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="68d39-142">Сведения о том, как изменить языки для телефонной конференции в вашей организации: [Настройка языков автосекретаря для голосовой конференции в Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="68d39-142">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span></span>

### <a name="step-7-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="68d39-143">Шаг 7: (необязательно) изменение параметров моста голосовой связи в Организации</span><span class="sxs-lookup"><span data-stu-id="68d39-143">Step 7: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="68d39-144">Сведения о том, как [изменить параметры моста](change-the-settings-for-an-audio-conferencing-bridge.md) голосовой конференц-связи в вашей организации, см.</span><span class="sxs-lookup"><span data-stu-id="68d39-144">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>

### <a name="step-8-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="68d39-145">Шаг 8: (необязательно) задайте номера телефонов, которые включаются в приглашения на собрания пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="68d39-145">Step 8: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="68d39-146">Чтобы изменить набор телефонных номеров, включенных в приглашения на собрание пользователей, обратитесь к разделу [Настройка номеров телефонов, включенных в приглашения в Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) .</span><span class="sxs-lookup"><span data-stu-id="68d39-146">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md)</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="68d39-147">Возможности голосовой связи не поддерживаются в голосовой конференции с прямой маршрутизацией для более высокого и невысокой четкости</span><span class="sxs-lookup"><span data-stu-id="68d39-147">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="68d39-148">Ниже приведены возможности голосовой конференции, которые не поддерживаются в голосовой конференции с прямой маршрутизацией для более высокого и невысокой четкости.</span><span class="sxs-lookup"><span data-stu-id="68d39-148">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="68d39-149">Уведомления о входе и выходе с помощью записи имен.</span><span class="sxs-lookup"><span data-stu-id="68d39-149">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="68d39-150">Для голосовой конференции с прямым маршрутом уведомления о входе и выходе воспроизводится на собрании как звуки.</span><span class="sxs-lookup"><span data-stu-id="68d39-150">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="68d39-151">Политики ограничения исходящих звонков для голосовой конференции.</span><span class="sxs-lookup"><span data-stu-id="68d39-151">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="68d39-152">Элементы управления на уровне пользователей для ограничения исходящих вызовов не относятся к вызовам для собраний, направляемым через прямую маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="68d39-152">User-level controls to restrict outbound calls aren't applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="68d39-153">Отключите использование бесплатных номеров для организатора собраний.</span><span class="sxs-lookup"><span data-stu-id="68d39-153">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="68d39-154">Элементы управления на уровне пользователей, которые ограничивают использование бесплатных номеров для присоединения к собраниям Организации, не применимы к вызовам, направляемым через прямую маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="68d39-154">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="68d39-155">Отправка пользователям уведомлений об изменении их параметров.</span><span class="sxs-lookup"><span data-stu-id="68d39-155">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="68d39-156">Уведомления о голосовой конференции не поддерживаются для голосовой связи с прямой маршрутизацией на GCC High и DoD.</span><span class="sxs-lookup"><span data-stu-id="68d39-156">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
