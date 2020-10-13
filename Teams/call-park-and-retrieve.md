---
title: Парковка и восстановление звонков в Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Узнайте о том, как использовать приостановку звонков и извлечь для помещения звонка на удержание в Microsoft Teams.
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424597"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="61d0b-103">Парковка и восстановление звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="61d0b-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="61d0b-104">Метод парковки и получения звонков — это функция, с помощью которой пользователь может поставить звонок на удержание.</span><span class="sxs-lookup"><span data-stu-id="61d0b-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="61d0b-105">При приостановке звонка служба генерирует уникальный код для получения вызова.</span><span class="sxs-lookup"><span data-stu-id="61d0b-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="61d0b-106">Пользователь, который приприпаркован звонок или другой пользователь может затем использовать этот код с поддерживаемым приложением или устройством для получения вызова.</span><span class="sxs-lookup"><span data-stu-id="61d0b-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="61d0b-107">(Дополнительные сведения см. в разделе Приостановка [звонка в Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) .)</span><span class="sxs-lookup"><span data-stu-id="61d0b-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="61d0b-108">Ниже приведены некоторые распространенные сценарии использования функции приостановки звонка.</span><span class="sxs-lookup"><span data-stu-id="61d0b-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="61d0b-109">Receptionist парки вызов для того, чтобы кто-то работал в фабрике.</span><span class="sxs-lookup"><span data-stu-id="61d0b-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="61d0b-110">Затем receptionist объявляет звонок и номер кода в системе общедоступной адресной системы.</span><span class="sxs-lookup"><span data-stu-id="61d0b-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="61d0b-111">Пользователь, для которого выполняется звонок, может затем выбрать телефон на телефоне в фабричном цехе и ввести код для получения звонка.</span><span class="sxs-lookup"><span data-stu-id="61d0b-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="61d0b-112">Пользователь парки Звонок на мобильном устройстве из-за отсутствия питания на батарее устройства.</span><span class="sxs-lookup"><span data-stu-id="61d0b-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="61d0b-113">Пользователь может ввести этот код, чтобы получить звонок с телефонного рабочего стола Teams.</span><span class="sxs-lookup"><span data-stu-id="61d0b-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="61d0b-114">Представитель службы поддержки парки звонок абоненту и отправляет извещение в канале Teams для эксперта по получению звонка и помогать клиенту.</span><span class="sxs-lookup"><span data-stu-id="61d0b-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="61d0b-115">Эксперт вводит код в клиентские группы, чтобы получить звонок.</span><span class="sxs-lookup"><span data-stu-id="61d0b-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="61d0b-116">Чтобы приостановить и получить звонки, пользователь должен быть пользователем голосовой связи и должен быть включен в политику приостановки звонка.</span><span class="sxs-lookup"><span data-stu-id="61d0b-116">To park and retrieve calls, a user must be an Enterprise Voice user and and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="61d0b-117">Функция парковки и извлечение звонков доступна только в [режиме развертывания Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) и не поддерживается на IP-телефонах Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="61d0b-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="61d0b-118">Настройка парковки и извлечение звонков</span><span class="sxs-lookup"><span data-stu-id="61d0b-118">Configure call park and retrieve</span></span>

<span data-ttu-id="61d0b-119">Вы должны быть администратором Teams, чтобы настроить приостановку и получение звонков.</span><span class="sxs-lookup"><span data-stu-id="61d0b-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="61d0b-120">По умолчанию он отключен.</span><span class="sxs-lookup"><span data-stu-id="61d0b-120">It is disabled by default.</span></span> <span data-ttu-id="61d0b-121">Вы можете включить ее для пользователей и создавать группы пользователей с помощью политики парковки звонков.</span><span class="sxs-lookup"><span data-stu-id="61d0b-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="61d0b-122">Если вы применяете одну и ту же политику к набору пользователей, они могут приостановить и получить звонки между собой.</span><span class="sxs-lookup"><span data-stu-id="61d0b-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="61d0b-123">Включение политики парковки звонков</span><span class="sxs-lookup"><span data-stu-id="61d0b-123">To enable a call park policy</span></span>

1. <span data-ttu-id="61d0b-124">В левой области навигации центра администрирования Microsoft Teams перейдите к **Voice**  >  **политикам парковки**для приема голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="61d0b-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="61d0b-125">На вкладке **Управление политиками** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="61d0b-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="61d0b-126">Присвойте политике имя, а затем установите переключатель **Разрешить приостановку звонка** **на включен**.</span><span class="sxs-lookup"><span data-stu-id="61d0b-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![Снимок экрана: настройки политики парковки звонков](media/call-park-add-policy.png)

4. <span data-ttu-id="61d0b-128">Нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="61d0b-128">Select **Save**.</span></span>

<span data-ttu-id="61d0b-129">Чтобы изменить политику, выберите ее в списке и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="61d0b-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="61d0b-130">Чтобы политика работала, она должна быть назначена пользователям.</span><span class="sxs-lookup"><span data-stu-id="61d0b-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="61d0b-131">Политику можно [назначить пользователям по отдельности](assign-policies.md) или назначить группе.</span><span class="sxs-lookup"><span data-stu-id="61d0b-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="61d0b-132">Назначение групповой политики вызова группе</span><span class="sxs-lookup"><span data-stu-id="61d0b-132">To assign a call part policy to a group</span></span>

1. <span data-ttu-id="61d0b-133">На странице **политики парковки звонков** на вкладке **назначение групповой политики** нажмите кнопку **Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="61d0b-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="61d0b-134">Найдите группу, которую вы хотите использовать, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="61d0b-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="61d0b-135">Выберите ранг по сравнению с другими назначениями групп.</span><span class="sxs-lookup"><span data-stu-id="61d0b-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="61d0b-136">В разделе **Выбор политики**выберите политику, которой вы хотите назначить эту группу.</span><span class="sxs-lookup"><span data-stu-id="61d0b-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="61d0b-137">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="61d0b-137">Click **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="61d0b-138">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="61d0b-138">Related topics</span></span>

[<span data-ttu-id="61d0b-139">Приостановка звонка в Teams</span><span class="sxs-lookup"><span data-stu-id="61d0b-139">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="61d0b-140">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="61d0b-140">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="61d0b-141">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="61d0b-141">New-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="61d0b-142">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="61d0b-142">Set-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="61d0b-143">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="61d0b-143">Grant-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)