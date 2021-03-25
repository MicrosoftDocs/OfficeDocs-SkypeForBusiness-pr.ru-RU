---
title: Настройка номеров телефонов, включенных в приглашения в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 956c2fa23f61f0c0e24cd1c2a0802bd3f1397bb1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113225"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a><span data-ttu-id="5d50c-103">Настройка номеров телефонов, включенных в приглашения в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5d50c-103">Set the phone numbers included on invites in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="5d50c-104">Сведения о номерах телефонов для приглашения на собрание в Microsoft Teams см. в сведениях о том, как настроить телефонные номера, включенные в приглашения [в Microsoft Teams.](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams)</span><span class="sxs-lookup"><span data-stu-id="5d50c-104">For information about meeting invite phone numbers in Microsoft Teams, see [Set the phone numbers included on invites in Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span></span>

<span data-ttu-id="5d50c-105">Аудиоконференция в Microsoft 365 или Office 365 позволяет пользователям в вашей организации создавать собрания Skype для бизнеса, а затем позволять пользователям звонить на эти собрания по телефону.</span><span class="sxs-lookup"><span data-stu-id="5d50c-105">Audio Conferencing in Microsoft 365 or Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="5d50c-106">В Microsoft 365 и Office 365 можно использовать мост аудиоконференций Майкрософт или сторонний мост аудиоконференций, который находится у утвержденного поставщика услуг аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="5d50c-106">In Microsoft 365 and Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d50c-107">Не существует никакого ресурса, который содержит список всех номеров для аудиоконференций с подключением по телефону.</span><span class="sxs-lookup"><span data-stu-id="5d50c-107">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="5d50c-108">Если вы хотите узнать, доступны ли телефонные номера для телефонного звонка в вашем регионе или стране или регионе, воспользуйтесь номерами голосовых телефонов Центра администрирования **Skype** для бизнеса и выберите "Добавить новые номера  >    >  служб".  </span><span class="sxs-lookup"><span data-stu-id="5d50c-108">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="5d50c-109">С помощью списков "Страна **или**  регион", "Область" и "Город" можно фильтровать результаты поиска.> Кроме того, если вам нужно найти бесплатные номера служб, выберите "Бесплатный" в списке "Область или регион".   </span><span class="sxs-lookup"><span data-stu-id="5d50c-109">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="5d50c-p103">Мост конференц-связи предоставляет вашей организации ряд телефонных номеров для подключения. Все эти номера могут быть использованы для подключения к собраниям, созданным организаторами, однако вы можете выбрать, какие номера будут указаны в приглашениях на собрания.</span><span class="sxs-lookup"><span data-stu-id="5d50c-p103">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d50c-112">Организатор собрания может использовать не более одного платного и одного бесплатного телефонного номера в приглашении на собрание, однако также имеется ссылка в нижней части приглашения на собрания, по которой открывается список всех телефонных номеров для подключения к собранию.</span><span class="sxs-lookup"><span data-stu-id="5d50c-112">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="5d50c-113">Настройка номера телефона для телефонного звонка по умолчанию для организатора собрания</span><span class="sxs-lookup"><span data-stu-id="5d50c-113">Set the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="5d50c-114">Войте свою учетную запись с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="5d50c-114">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="5d50c-115">Выберите **Центры администрирования** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="5d50c-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="5d50c-116">Выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="5d50c-116">Choose **Users**.</span></span>
    
    ![Выбор пользователей в Центре администрирования Skype для бизнеса](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="5d50c-118">Выберите пользователей, которые вы хотите изменить:</span><span class="sxs-lookup"><span data-stu-id="5d50c-118">Choose the users you want to edit:</span></span>
    
   - <span data-ttu-id="5d50c-119">Чтобы выбрать одного пользователя, выберите его имя.</span><span class="sxs-lookup"><span data-stu-id="5d50c-119">To select a single user, select the user's name.</span></span>
    
   - <span data-ttu-id="5d50c-120">Чтобы выбрать всех пользователей на странице, выберите поле рядом с **отображаемой** именем в верхней части списка.</span><span class="sxs-lookup"><span data-stu-id="5d50c-120">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
   - <span data-ttu-id="5d50c-121">Чтобы выбрать несколько пользователей, выберите поле рядом с именем каждого из них.</span><span class="sxs-lookup"><span data-stu-id="5d50c-121">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="5d50c-122">В области справа выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5d50c-122">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="5d50c-124">Выберите **"Аудиоконференция".**</span><span class="sxs-lookup"><span data-stu-id="5d50c-124">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="5d50c-125">На странице **"Свойства"** в списке **"Имя** поставщика" выберите поставщика для пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d50c-125">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="5d50c-126">В зависимости от выбранного поставщика заполните следующие поля.</span><span class="sxs-lookup"><span data-stu-id="5d50c-126">Depending on the provider, complete the following boxes.</span></span>
    
   - <span data-ttu-id="5d50c-127">**Майкрософт является поставщиком:**  используйте платный  номер по умолчанию и бесплатные списки номеров по умолчанию, чтобы выбрать номера по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d50c-127">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="5d50c-128">Прежде чем мост конференц-связи может быть задан как бесплатный номер по умолчанию для пользователей, ему следует назначить хотя бы один бесплатный номер.</span><span class="sxs-lookup"><span data-stu-id="5d50c-128">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="5d50c-129">Чтобы получить бесплатный номер, см. получение номеров телефонов служб [для Skype для бизнеса.](/microsoftteams/getting-service-phone-numbers)</span><span class="sxs-lookup"><span data-stu-id="5d50c-129">To get a toll-free number, see [Getting service phone numbers for Skype for Business](/microsoftteams/getting-service-phone-numbers).</span></span> 
  
   - <span data-ttu-id="5d50c-130">**Сторонний поставщик — это** поставщик: используйте  поля "Платный номер" и "Бесплатные номера", чтобы ввести номера для пользователя. </span><span class="sxs-lookup"><span data-stu-id="5d50c-130">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="5d50c-131">Сброс номеров доступа к конференции с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="5d50c-131">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="5d50c-132">В **Центр администрирования Skype для бизнеса** выберите **Аудиоконференция**.</span><span class="sxs-lookup"><span data-stu-id="5d50c-132">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="5d50c-133">В верхней части страницы щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="5d50c-133">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="5d50c-134">Выберите пользователей, которые нужно сбросить, и на области действий нажмите кнопку **"Очистить".**</span><span class="sxs-lookup"><span data-stu-id="5d50c-134">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="5d50c-135">По умолчанию при изменении параметров пользовательских параметров conferencing пользователю отправляется сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="5d50c-135">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="5d50c-136">Чтобы изменить это, см. параметр "Включить или отключить отправку сообщений электронной почты при изменении параметров [аудиоконференции".](enable-or-disable-sending-emails-when-their-settings-change.md)</span><span class="sxs-lookup"><span data-stu-id="5d50c-136">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5d50c-137">При изменении параметров аудиоконференции необходимо обновить и отправить участникам повторяющиеся и будущие собрания Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5d50c-137">When you change a user's audio conferencing settings, recurring and future Skype for Business meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="5d50c-138">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d50c-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="5d50c-139">Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).</span><span class="sxs-lookup"><span data-stu-id="5d50c-139">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet.</span></span>
    
- <span data-ttu-id="5d50c-140">Используйте командлет [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) для изменения платного или бесплатного номера по умолчанию для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="5d50c-140">Use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="5d50c-141">Чтобы изменить бесплатный номер по умолчанию для определенного пользователя, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="5d50c-141">To change the default toll-free number for a user, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="5d50c-142">Используйте командлет **Set-CsOnlineDialInConferencingUserDefaultNumber** для изменения платного или бесплатного номера по умолчанию для пользователей на основе исходного номера по умолчанию, свойственного для местоположения этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="5d50c-142">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5d50c-143">Чтобы найти код BridgeID, используйте **cmdlet Get-CsOnlineDialInConferencingBridge.**</span><span class="sxs-lookup"><span data-stu-id="5d50c-143">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge** cmdlet.</span></span>
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="5d50c-144">Чтобы задать бесплатный номер +18005551234 в качестве номера по умолчанию для всех пользователей, не имеющих номера по умолчанию, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="5d50c-144">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="5d50c-145">Чтобы изменить бесплатный номер по умолчанию для всех пользователей с бесплатным номером по умолчанию +18005551234 на +18005551239, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="5d50c-145">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="5d50c-146">Чтобы задать бесплатный номер +18005551234 в качестве номера по умолчанию для всех пользователей, расположенных в США, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="5d50c-146">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="5d50c-147">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5d50c-147">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="5d50c-p107">Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="5d50c-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5d50c-151">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5d50c-151">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="5d50c-152">Зачем нужно использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d50c-152">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="5d50c-153">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="5d50c-153">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="5d50c-154">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="5d50c-154">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="5d50c-155">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="5d50c-155">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="5d50c-156">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5d50c-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="5d50c-157">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5d50c-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="5d50c-158">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5d50c-158">Related topics</span></span>

[<span data-ttu-id="5d50c-159">Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="5d50c-159">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)