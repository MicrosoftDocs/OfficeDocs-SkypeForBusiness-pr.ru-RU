---
title: Установка телефона, номера, находящимся на приглашает в Скайп для бизнеса в Интернет
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: c78a3fb140431dd46b3850e1d01e7fb29fb29210
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229417"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a><span data-ttu-id="a0d62-103">Установка телефона, номера, находящимся на приглашает в Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="a0d62-103">Set the phone numbers included on invites in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="a0d62-104">Сведения о собрании пригласить телефонных номеров в группами Майкрософт, содержатся в разделе [Задание телефона, номера, находящимся на приглашает в группах Майкрософт](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span><span class="sxs-lookup"><span data-stu-id="a0d62-104">For information about meeting invite phone numbers in Microsoft Teams, see [Set the phone numbers included on invites in Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span></span>

<span data-ttu-id="a0d62-105">Аудиоконференций в Office 365 позволяет пользователям в вашей организации для создания Скайп для бизнеса собраний и разрешить пользователям по телефонной линии к собраниям с помощью телефона.</span><span class="sxs-lookup"><span data-stu-id="a0d62-105">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="a0d62-106">В Office 365 у вас есть возможность использовать мост аудиоконференций Microsoft или моста аудиоконференций сторонних производителей, размещенного поставщиком утвержденных аудиоконференций (ACP).</span><span class="sxs-lookup"><span data-stu-id="a0d62-106">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a0d62-107">Не существует никакого ресурса, который содержит список всех номеров для аудиоконференций с подключением по телефону.</span><span class="sxs-lookup"><span data-stu-id="a0d62-107">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="a0d62-108">Если вы хотите узнать, если существует телефонные номера телефонов в области или страны или региона, используйте **Скайп по центру администрирования Business** > **голосовой связи** > **Телефонных номеров**, нажмите кнопку **Добавить** , затем \*\*новых номеров службы \*\*.</span><span class="sxs-lookup"><span data-stu-id="a0d62-108">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="a0d62-109">Используйте списки для **Страны или региона**, регион \*\*\*\* и **Город** для фильтрации вашей search.> Кроме того, если вы ищете платные бесплатно номера **бесплатный** выберите из **состояние и область** списка.</span><span class="sxs-lookup"><span data-stu-id="a0d62-109">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="a0d62-p103">Мост конференц-связи предоставляет вашей организации ряд телефонных номеров для подключения. Все эти номера могут быть использованы для подключения к собраниям, созданным организаторами, однако вы можете выбрать, какие номера будут указаны в приглашениях на собрания.</span><span class="sxs-lookup"><span data-stu-id="a0d62-p103">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a0d62-112">Организатор собрания может использовать не более одного платного и одного бесплатного телефонного номера в приглашении на собрание, однако также имеется ссылка в нижней части приглашения на собрания, по которой открывается список всех телефонных номеров для подключения к собранию.</span><span class="sxs-lookup"><span data-stu-id="a0d62-112">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="a0d62-113">Значение по умолчанию телефонные номера для организатора собрания</span><span class="sxs-lookup"><span data-stu-id="a0d62-113">Set the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="a0d62-114">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="a0d62-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a0d62-115">Выберите **Центры администрирования** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="a0d62-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a0d62-116">Выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="a0d62-116">Choose **Users**.</span></span>
    
    ![Показывает, Выбор пользователей в Скайп по центру администрирования бизнеса](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="a0d62-118">Выберите пользователей, которые необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="a0d62-118">Choose the users you want to edit:</span></span>
    
   - <span data-ttu-id="a0d62-119">Чтобы выбрать одного пользователя, выберите имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="a0d62-119">To select a single user, select the user's name.</span></span>
    
   - <span data-ttu-id="a0d62-120">Чтобы выбрать все пользователи на странице, установите флажок рядом с полем **отображаемое имя** в верхней части списка.</span><span class="sxs-lookup"><span data-stu-id="a0d62-120">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
   - <span data-ttu-id="a0d62-121">Чтобы выбрать несколько пользователей, установите флажок рядом с именем каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="a0d62-121">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="a0d62-122">В области справа выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a0d62-122">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="a0d62-124">Выберите **звук конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="a0d62-124">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="a0d62-125">На странице " **Свойства** " выберите в списке **имя поставщика** поставщика для пользователя.</span><span class="sxs-lookup"><span data-stu-id="a0d62-125">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="a0d62-126">В зависимости от выбранного поставщика заполните следующие поля.</span><span class="sxs-lookup"><span data-stu-id="a0d62-126">Depending on the provider, complete the following boxes.</span></span>
    
   - <span data-ttu-id="a0d62-127">**Microsoft является поставщик**: используйте **номер счета по умолчанию** и списки **бесплатный номер по умолчанию** , чтобы выбрать значения по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="a0d62-127">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="a0d62-128">Прежде чем мост конференц-связи может быть задан как бесплатный номер по умолчанию для пользователей, ему следует назначить хотя бы один бесплатный номер.</span><span class="sxs-lookup"><span data-stu-id="a0d62-128">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="a0d62-129">Чтобы получить бесплатный номер, видеть [Приступая к службе номера телефонов для Скайп для бизнеса](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="a0d62-129">To get a toll-free number, see [Getting service phone numbers for Skype for Business](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span> 
  
   - <span data-ttu-id="a0d62-130">**Сторонний является поставщик**: поля **бесплатный номер** и **телефоны** используются для ввода цифр для пользователя.</span><span class="sxs-lookup"><span data-stu-id="a0d62-130">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="a0d62-131">Сброс номеров доступа к конференции с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="a0d62-131">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="a0d62-132">В **Центр администрирования Skype для бизнеса**выберите **Аудиоконференция**.</span><span class="sxs-lookup"><span data-stu-id="a0d62-132">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="a0d62-133">В верхней части страницы щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="a0d62-133">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="a0d62-134">Выберите пользователей, которых требуется выполнить сброс и затем в области действий нажмите кнопку **Очистить**.</span><span class="sxs-lookup"><span data-stu-id="a0d62-134">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="a0d62-135">По умолчанию при изменении параметров конференц-связи пользователя, сообщения электронной почты отправляется пользователя.</span><span class="sxs-lookup"><span data-stu-id="a0d62-135">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="a0d62-136">Чтобы изменить этот параметр, см. [Включение и отключение отправки сообщения электронной почты при изменении параметров звука конференц-связи](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="a0d62-136">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a0d62-137">Изменить параметры пользователя аудиоконференций, повторяющиеся и будущих Скайп для собраний Business необходимо обновляется и отправлено участникам.</span><span class="sxs-lookup"><span data-stu-id="a0d62-137">When you change a user's audio conferencing settings, recurring and future Skype for Business meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a0d62-138">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0d62-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="a0d62-139">Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).</span><span class="sxs-lookup"><span data-stu-id="a0d62-139">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet.</span></span>
    
- <span data-ttu-id="a0d62-140">Используйте командлет [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) для изменения платного или бесплатного номера по умолчанию для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="a0d62-140">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="a0d62-141">Чтобы изменить бесплатный номер по умолчанию для определенного пользователя, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="a0d62-141">To change the default toll-free number for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="a0d62-142">Используйте командлет **Set-CsOnlineDialInConferencingUserDefaultNumber** для изменения платного или бесплатного номера по умолчанию для пользователей на основе исходного номера по умолчанию, свойственного для местоположения этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="a0d62-142">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a0d62-143">Чтобы найти BridgeID, используйте командлет **Get-CsOnlineDialInConferencingBridge** .</span><span class="sxs-lookup"><span data-stu-id="a0d62-143">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge** cmdlet.</span></span>
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="a0d62-144">Чтобы задать бесплатный номер +18005551234 в качестве номера по умолчанию для всех пользователей, не имеющих номера по умолчанию, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="a0d62-144">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="a0d62-145">Чтобы изменить бесплатный номер по умолчанию для всех пользователей с бесплатным номером по умолчанию +18005551234 на +18005551239, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="a0d62-145">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="a0d62-146">Чтобы задать бесплатный номер +18005551234 в качестве номера по умолчанию для всех пользователей, расположенных в США, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="a0d62-146">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="a0d62-147">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="a0d62-147">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="a0d62-p107">Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="a0d62-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a0d62-151">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a0d62-151">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="a0d62-152">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="a0d62-152">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="a0d62-p108">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="a0d62-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="a0d62-155">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0d62-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="a0d62-156">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a0d62-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a0d62-157">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a0d62-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="a0d62-158">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a0d62-158">Related topics</span></span>

[<span data-ttu-id="a0d62-159">Пробная и платная аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="a0d62-159">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
