---
title: Задайте телефона, номера, находящимся на приглашает
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: eb2c5c5e8cdc0562cb5a2e391c741763b1da0bd4
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703751"
---
# <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="5620f-103">Задайте телефона, номера, находящимся на приглашает</span><span class="sxs-lookup"><span data-stu-id="5620f-103">Set the phone numbers included on invites</span></span>

<span data-ttu-id="5620f-104">Аудиоконференций в Office 365 позволяет пользователям в вашей организации для создания Скайп для бизнеса и группами Майкрософт собраний и разрешить пользователям по телефонной линии к собраниям с помощью телефона.</span><span class="sxs-lookup"><span data-stu-id="5620f-104">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business and Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="5620f-105">В Office 365 у вас есть возможность использовать мост аудиоконференций Microsoft или моста аудиоконференций сторонних производителей, размещенного поставщиком утвержденных аудиоконференций (ACP).</span><span class="sxs-lookup"><span data-stu-id="5620f-105">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5620f-106">Не существует никакого ресурса, который содержит список всех номеров для аудиоконференций с подключением по телефону.</span><span class="sxs-lookup"><span data-stu-id="5620f-106">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="5620f-107">Если вы хотите узнать, если существует телефонные номера телефонов в области или страны или региона, используйте **Скайп по центру администрирования Business** > **голосовой связи** > **Телефонных номеров**, нажмите кнопку **Добавить** , затем **новых номеров службы **.</span><span class="sxs-lookup"><span data-stu-id="5620f-107">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="5620f-108">Используйте списки для **Страны или региона**, регион **** и **Город** для фильтрации поиска. > Кроме того, если вы ищете платные бесплатно номера, выберите **бесплатный номер** из **состояние и область** списка.</span><span class="sxs-lookup"><span data-stu-id="5620f-108">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="5620f-p103">Мост конференц-связи предоставляет вашей организации ряд телефонных номеров для подключения. Все эти номера могут быть использованы для подключения к собраниям, созданным организаторами, однако вы можете выбрать, какие номера будут указаны в приглашениях на собрания.</span><span class="sxs-lookup"><span data-stu-id="5620f-p103">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5620f-111">Организатор собрания может использовать не более одного платного и одного бесплатного телефонного номера в приглашении на собрание, однако также имеется ссылка в нижней части приглашения на собрания, по которой открывается список всех телефонных номеров для подключения к собранию.</span><span class="sxs-lookup"><span data-stu-id="5620f-111">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="5620f-112">Значение по умолчанию телефонные номера для организатора собрания</span><span class="sxs-lookup"><span data-stu-id="5620f-112">Set the default dial-in phone number for a meeting organizer</span></span>

<span data-ttu-id="5620f-113">![команды логотип 30x30.png](../images/teams-logo-30x30.png) **с помощью групп Майкрософт и Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="5620f-113">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="5620f-114">На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.</span><span class="sxs-lookup"><span data-stu-id="5620f-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![Показывает, Выбор пользователей в группы Microsoft и Скайп по центру администрирования Business](../images/teamsselectusers.png)

2. <span data-ttu-id="5620f-116">В верхней части страницы нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5620f-116">At the top of the page, click **Edit**.</span></span>

    ![Нажмите кнопку Изменить в Microsoft групп и Скайп по центру администрирования Business](../images/teamsedituser.png)

3. <span data-ttu-id="5620f-118">Рядом с пунктом **Звук конференц-связи**нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5620f-118">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Нажмите кнопку Изменить рядом с пунктом аудиоконференции](../images/teamseditaudioconf.png)

4. <span data-ttu-id="5620f-120">Использование полей **бесплатный номер** или **бесплатный номер** для ввода цифр для пользователя.</span><span class="sxs-lookup"><span data-stu-id="5620f-120">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>

<span data-ttu-id="5620f-121">![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="5620f-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="5620f-122">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="5620f-122">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5620f-123">Выберите **Центры администрирования** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="5620f-123">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="5620f-124">Выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="5620f-124">Choose **Users**.</span></span>
    
    ![Показывает, Выбор пользователей в Скайп по центру администрирования бизнеса](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="5620f-126">Выберите пользователей, которые необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="5620f-126">Choose the users you want to edit:</span></span>
    
  - <span data-ttu-id="5620f-127">Чтобы выбрать одного пользователя, выберите имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="5620f-127">To select a single user, select the user's name.</span></span>
    
  - <span data-ttu-id="5620f-128">Чтобы выбрать все пользователи на странице, установите флажок рядом с полем **отображаемое имя** в верхней части списка.</span><span class="sxs-lookup"><span data-stu-id="5620f-128">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
  - <span data-ttu-id="5620f-129">Чтобы выбрать несколько пользователей, установите флажок рядом с именем каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="5620f-129">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="5620f-130">В области справа выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5620f-130">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="5620f-132">Выберите **звук конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="5620f-132">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="5620f-133">На странице " **Свойства** " выберите в списке **имя поставщика** поставщика для пользователя.</span><span class="sxs-lookup"><span data-stu-id="5620f-133">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="5620f-134">В зависимости от выбранного поставщика заполните следующие поля.</span><span class="sxs-lookup"><span data-stu-id="5620f-134">Depending on the provider, complete the following boxes.</span></span>
    
  - <span data-ttu-id="5620f-135">**Microsoft является поставщик**: используйте **номер счета по умолчанию** и списки **бесплатный номер по умолчанию** , чтобы выбрать значения по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="5620f-135">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5620f-136">Прежде чем мост конференц-связи может быть задан как бесплатный номер по умолчанию для пользователей, ему следует назначить хотя бы один бесплатный номер.</span><span class="sxs-lookup"><span data-stu-id="5620f-136">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="5620f-137">Чтобы получить бесплатный номер, видеть [Приступая к службе номера телефонов для Скайп для бизнеса и группами Майкрософт](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="5620f-137">To get a toll-free number, see [Getting service phone numbers for Skype for Business and Microsoft Teams](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span> 
  
  - <span data-ttu-id="5620f-138">**Сторонний является поставщик**: поля **бесплатный номер** и **телефоны** используются для ввода цифр для пользователя.</span><span class="sxs-lookup"><span data-stu-id="5620f-138">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


## <a name="change-the-audio-conferencing-phone-number-for-users"></a><span data-ttu-id="5620f-139">Изменение номера телефона аудиоконференций для пользователей</span><span class="sxs-lookup"><span data-stu-id="5620f-139">Change the audio conferencing phone number for users</span></span>

<span data-ttu-id="5620f-140">![команды логотип 30x30.png](../images/teams-logo-30x30.png) **с помощью групп Майкрософт и Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="5620f-140">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="5620f-141">На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.</span><span class="sxs-lookup"><span data-stu-id="5620f-141">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="5620f-142">В верхней части страницы нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5620f-142">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="5620f-143">Рядом с пунктом **Звук конференц-связи**нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5620f-143">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="5620f-144">Использование полей **бесплатный номер** или **бесплатный номер** для ввода цифр для пользователя.</span><span class="sxs-lookup"><span data-stu-id="5620f-144">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>

## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="5620f-145">Сброс номеров доступа к конференции с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="5620f-145">Reset audio conferencing phone numbers</span></span>

<span data-ttu-id="5620f-146">![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="5620f-146">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="5620f-147">В **Центр администрирования Skype для бизнеса**выберите **Аудиоконференция**.</span><span class="sxs-lookup"><span data-stu-id="5620f-147">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="5620f-148">В верхней части страницы щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="5620f-148">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="5620f-149">Выберите пользователей, которых требуется выполнить сброс и затем в области действий нажмите кнопку **Очистить**.</span><span class="sxs-lookup"><span data-stu-id="5620f-149">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="5620f-150">По умолчанию при изменении параметров конференц-связи пользователя, сообщения электронной почты отправляется пользователя.</span><span class="sxs-lookup"><span data-stu-id="5620f-150">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="5620f-151">Чтобы изменить этот параметр, см. [Включение и отключение отправки сообщения электронной почты при изменении параметров звука конференц-связи](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="5620f-151">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5620f-152">При изменении настроек аудиоконференции необходимо обновить и отправить участникам повторяющиеся и будущие собрания Skype для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5620f-152">When you change a user's audio conferencing settings, recurring and future Skype for Business and Microsoft Teams meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="5620f-153">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5620f-153">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="5620f-154">Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).</span><span class="sxs-lookup"><span data-stu-id="5620f-154">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet.</span></span>
    
- <span data-ttu-id="5620f-155">Используйте командлет [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) для изменения платного или бесплатного номера по умолчанию для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="5620f-155">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="5620f-156">Чтобы изменить бесплатный номер по умолчанию для определенного пользователя, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="5620f-156">To change the default toll-free number for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="5620f-157">Используйте командлет **Set-CsOnlineDialInConferencingUserDefaultNumber** для изменения платного или бесплатного номера по умолчанию для пользователей на основе исходного номера по умолчанию, свойственного для местоположения этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="5620f-157">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5620f-158">Чтобы найти BridgeID, используйте командлет **Get-CsOnlineDialInConferencingBridge** .</span><span class="sxs-lookup"><span data-stu-id="5620f-158">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge** cmdlet.</span></span>
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="5620f-159">Чтобы задать бесплатный номер +18005551234 в качестве номера по умолчанию для всех пользователей, не имеющих номера по умолчанию, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="5620f-159">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="5620f-160">Чтобы изменить бесплатный номер по умолчанию для всех пользователей с бесплатным номером по умолчанию +18005551234 на +18005551239, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="5620f-160">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="5620f-161">Чтобы задать бесплатный номер +18005551234 в качестве номера по умолчанию для всех пользователей, расположенных в США, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="5620f-161">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="5620f-162">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5620f-162">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="5620f-p107">Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="5620f-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5620f-166">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5620f-166">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="5620f-167">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="5620f-167">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="5620f-p108">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="5620f-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="5620f-170">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5620f-170">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="5620f-171">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5620f-171">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="5620f-172">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5620f-172">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="5620f-173">See also</span><span class="sxs-lookup"><span data-stu-id="5620f-173">Related topics</span></span>

[<span data-ttu-id="5620f-174">Пробная и платная аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="5620f-174">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
