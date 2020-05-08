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
ms.openlocfilehash: b7a4ee991ff8a8e41401b3b2d2dc20aa20708b88
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163938"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a><span data-ttu-id="0c6b8-103">Настройка номеров телефонов, включенных в приглашения в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="0c6b8-103">Set the phone numbers included on invites in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="0c6b8-104">Дополнительные сведения о номерах телефонов для собраний в Microsoft Teams можно найти в разделе [Настройка номеров телефонов, включенных в приглашения в Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span><span class="sxs-lookup"><span data-stu-id="0c6b8-104">For information about meeting invite phone numbers in Microsoft Teams, see [Set the phone numbers included on invites in Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span></span>

<span data-ttu-id="0c6b8-105">Голосовой Конференц-связь в Microsoft 365 или Office 365 позволяет пользователям в организации создавать собрания Skype для бизнеса и разрешать пользователям звонить на эти собрания с помощью телефона.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-105">Audio Conferencing in Microsoft 365 or Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="0c6b8-106">В Microsoft 365 и Office 365 вы сможете воспользоваться мостом Microsoft для конференц-связи с телефонным подключением или сторонним поставщиком услуг голосовой связи, размещенным в утвержденных поставщиках видеоконференций (ACP).</span><span class="sxs-lookup"><span data-stu-id="0c6b8-106">In Microsoft 365 and Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0c6b8-107">Не существует никакого ресурса, который содержит список всех номеров для аудиоконференций с подключением по телефону.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-107">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="0c6b8-108">Если вы хотите узнать, есть ли в вашей стране или регионе номера > **для телефонного** > подключения, введите**номера телефонов**в **центре администрирования Skype для бизнеса**, нажмите кнопку **Добавить** и выберите пункт **новые номера служб**.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-108">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="0c6b8-109">Используйте списки для **страны/региона**, область **или регион** и **город** , чтобы отфильтровать результаты поиска. > Кроме того, если вы ищете бесплатные номера сервисных услуг **, выберите бесплатный** из списка область **или регион** .</span><span class="sxs-lookup"><span data-stu-id="0c6b8-109">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="0c6b8-p103">Мост конференц-связи предоставляет вашей организации ряд телефонных номеров для подключения. Все эти номера могут быть использованы для подключения к собраниям, созданным организаторами, однако вы можете выбрать, какие номера будут указаны в приглашениях на собрания.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-p103">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0c6b8-112">Организатор собрания может использовать не более одного платного и одного бесплатного телефонного номера в приглашении на собрание, однако также имеется ссылка в нижней части приглашения на собрания, по которой открывается список всех телефонных номеров для подключения к собранию.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-112">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="0c6b8-113">Установка номера телефона для подключения по умолчанию для организатора собрания</span><span class="sxs-lookup"><span data-stu-id="0c6b8-113">Set the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="0c6b8-114">Войдите в свою рабочую или учебную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-114">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="0c6b8-115">Выберите **Центры администрирования** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="0c6b8-116">Выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-116">Choose **Users**.</span></span>
    
    ![Показывает, как выбрать пользователей в центре администрирования Skype для бизнеса](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="0c6b8-118">Выберите пользователей, которых вы хотите изменить:</span><span class="sxs-lookup"><span data-stu-id="0c6b8-118">Choose the users you want to edit:</span></span>
    
   - <span data-ttu-id="0c6b8-119">Чтобы выбрать одного пользователя, выберите имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-119">To select a single user, select the user's name.</span></span>
    
   - <span data-ttu-id="0c6b8-120">Чтобы выбрать всех пользователей на странице, установите флажок справа от **отображаемого имени** в верхней части списка.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-120">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
   - <span data-ttu-id="0c6b8-121">Чтобы выбрать несколько пользователей, установите флажок рядом с именем каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-121">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="0c6b8-122">В области справа выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-122">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="0c6b8-124">Выберите " **звуковые конференции**".</span><span class="sxs-lookup"><span data-stu-id="0c6b8-124">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="0c6b8-125">На странице " **Свойства** " в списке **имя поставщика** выберите поставщика для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-125">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="0c6b8-126">В зависимости от выбранного поставщика заполните следующие поля.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-126">Depending on the provider, complete the following boxes.</span></span>
    
   - <span data-ttu-id="0c6b8-127">**Корпорация Microsoft — это поставщик**: для выбора номеров по умолчанию для пользователя необходимо использовать **платный номер по** умолчанию и список **бесплатных номеров** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-127">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="0c6b8-128">Прежде чем мост конференц-связи может быть задан как бесплатный номер по умолчанию для пользователей, ему следует назначить хотя бы один бесплатный номер.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-128">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="0c6b8-129">Чтобы получить бесплатный номер, ознакомьтесь со статьей [Получение номеров телефонов служб для Skype для бизнеса](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="0c6b8-129">To get a toll-free number, see [Getting service phone numbers for Skype for Business](/microsoftteams/getting-service-phone-numbers).</span></span> 
  
   - <span data-ttu-id="0c6b8-130">**Сторонним поставщиком является поставщик**: с помощью полей **платный номер** и бесплатный **номер** для ввода номеров для пользователя.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-130">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="0c6b8-131">Сброс номеров доступа к конференции с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="0c6b8-131">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="0c6b8-132">В **Центр администрирования Skype для бизнеса**выберите **Аудиоконференция**.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-132">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="0c6b8-133">В верхней части страницы щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-133">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="0c6b8-134">Выберите пользователей, которых нужно сбросить, а затем на панели действий нажмите кнопку **очистить**.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-134">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="0c6b8-135">По умолчанию при изменении параметров конференций пользователя отправляется сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-135">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="0c6b8-136">Чтобы изменить этот параметр, ознакомьтесь с разрешениями [Включение и отключение отправки сообщений электронной почты при изменении параметров голосовой конференции](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="0c6b8-136">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0c6b8-137">Когда вы изменяете настройки голосовой конференции пользователя, повторяющиеся и будущие собрания Skype для бизнеса должны быть обновлены и отправлены участникам.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-137">When you change a user's audio conferencing settings, recurring and future Skype for Business meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="0c6b8-138">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c6b8-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="0c6b8-139">Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).</span><span class="sxs-lookup"><span data-stu-id="0c6b8-139">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet.</span></span>
    
- <span data-ttu-id="0c6b8-140">Используйте командлет [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) для изменения платного или бесплатного номера по умолчанию для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-140">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="0c6b8-141">Чтобы изменить бесплатный номер по умолчанию для определенного пользователя, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="0c6b8-141">To change the default toll-free number for a user, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="0c6b8-142">Используйте командлет **Set-CsOnlineDialInConferencingUserDefaultNumber** для изменения платного или бесплатного номера по умолчанию для пользователей на основе исходного номера по умолчанию, свойственного для местоположения этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-142">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0c6b8-143">Чтобы найти BridgeID, используйте командлет **Get-CsOnlineDialInConferencingBridge** .</span><span class="sxs-lookup"><span data-stu-id="0c6b8-143">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge** cmdlet.</span></span>
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="0c6b8-144">Чтобы задать бесплатный номер +18005551234 в качестве номера по умолчанию для всех пользователей, не имеющих номера по умолчанию, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="0c6b8-144">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="0c6b8-145">Чтобы изменить бесплатный номер по умолчанию для всех пользователей с бесплатным номером по умолчанию +18005551234 на +18005551239, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="0c6b8-145">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="0c6b8-146">Чтобы задать бесплатный номер +18005551234 в качестве номера по умолчанию для всех пользователей, расположенных в США, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="0c6b8-146">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="0c6b8-147">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="0c6b8-147">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="0c6b8-p107">Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0c6b8-151">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="0c6b8-151">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="0c6b8-152">Зачем использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c6b8-152">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="0c6b8-153">Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft 365, например при одновременном изменении параметров для нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="0c6b8-153">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="0c6b8-154">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="0c6b8-154">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="0c6b8-155">Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c6b8-155">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="0c6b8-156">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="0c6b8-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="0c6b8-157">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="0c6b8-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="0c6b8-158">См. также</span><span class="sxs-lookup"><span data-stu-id="0c6b8-158">Related topics</span></span>

[<span data-ttu-id="0c6b8-159">Попробуйте или купите голосовую конференцию в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="0c6b8-159">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
