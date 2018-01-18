---
title: "Назначение стороннего поставщика услуг аудиоконференций"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to set up a third-party as your dial-in conferencing provider with Skype for Business. '
ms.openlocfilehash: a53a2e63f15aa40eb6a88ab13daba2022b35e3b6
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2017
---
# <a name="assign-a-third-party-as-the-audio-conferencing-provider"></a><span data-ttu-id="5497c-103">Назначение стороннего поставщика услуг аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="5497c-103">Assign a third-party as the audio conferencing provider</span></span>

<span data-ttu-id="5497c-104">Поставщика аудиоконференций предоставляет *bridge конференции*.</span><span class="sxs-lookup"><span data-stu-id="5497c-104">An audio conferencing provider supplies the *conference bridge*.</span></span> <span data-ttu-id="5497c-105">Мост конференции предоставляет телефонные номера, контакты и конференции идентификаторы для собрания, которые создаются.</span><span class="sxs-lookup"><span data-stu-id="5497c-105">The conference bridge provides the dial-in phone number, PINs, and conference IDs for meetings that are created.</span></span> <span data-ttu-id="5497c-106">Необходимо назначить поставщика аудиоконференций для тех, кто собирается расписание или привести Скайп для бизнеса или группами Майкрософт собраний.</span><span class="sxs-lookup"><span data-stu-id="5497c-106">You only need to assign an audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5497c-107">В Microsoft Teams пользователь не может использовать стороннего поставщика услуг аудиоконференций, необходимо использовать аудиоконференцию в Office 365, где в качестве поставщика услуг аудиоконференции устанавливается Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5497c-107">For Microsoft Teams, a user can't use a third-party audio conferencing provider, they must use Audio Conferencing in Office 365, which sets the audio conferencing provider to Microsoft.</span></span> 
  
## <a name="steps-to-do-before-you-can-assign-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="5497c-108">Действия, выполняемые ДО назначения стороннего поставщика аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="5497c-108">Steps to do BEFORE you can assign a third-party audio conferencing provider</span></span>

1. <span data-ttu-id="5497c-109">В зависимости от вашего плана Office 365 необходимо приобрести лицензии дополнительный компонент **Аудиоконференции** для пользователей в вашей организации, которые будут расписание или привести Скайп для бизнеса или группами Майкрософт собраний с помощью звука конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="5497c-109">Depending on your Office 365 plan, you might need to buy **Audio Conferencing** add-on licenses for the people in your organization who are going to schedule or lead Skype for Business or Microsoft Teams meetings using Audio Conferencing.</span></span> <span data-ttu-id="5497c-110">Для получения дополнительных сведений см [Скайп для бизнеса и группами Майкрософт дополнительный компонент лицензирования](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="5497c-110">To learn more, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="5497c-111">Если вы приобрели лицензии **Аудиоконференции** дополнительный компонент, их необходимо назначьте пользователей в вашей организации, которые будут расписание или привести собраний, использующих звук конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="5497c-111">If you purchased **Audio Conferencing** add-on licenses, assign them to the people in your organization who are going to schedule or lead meetings that use Audio Conferencing.</span></span> <span data-ttu-id="5497c-112">В разделе [Назначение Скайп для бизнеса и группами Майкрософт лицензий](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="5497c-112">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5497c-p104">Если назначить пользователю лицензию **аудиоконференции** **ПОСЛЕ** назначения ему стороннего поставщика услуг аудиоконференций, автоматически будет задано использование Майкрософт в качестве такого поставщика. В этом случае потребуется сначала удалить Майкрософт как поставщика услуг аудиоконференций, и только после этого вы сможете назначить пользователю стороннего поставщика.</span><span class="sxs-lookup"><span data-stu-id="5497c-p104">If you assign an **Audio Conferencing** license to someone **AFTER** you assign them a third-party audio conferencing provider, that person will automatically be set to use Microsoft as their audio conferencing provider instead! If this happens, you will need to first remove Microsoft as the audio conferencing provider before you can assign a third-party audio conferencing provider to them.</span></span>
  
3. <span data-ttu-id="5497c-p105">Найти сторонних поставщиков аудиоконференций можно на сайте [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530). Свяжитесь с ними и выясните, как именно следует выполнять настройку.</span><span class="sxs-lookup"><span data-stu-id="5497c-p105">Find a third-party audio conferencing provider at [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530). Contact them and find out how to get things set up with them.</span></span>
    
    <span data-ttu-id="5497c-117">Поставщик предоставит вам:</span><span class="sxs-lookup"><span data-stu-id="5497c-117">They will give you:</span></span>
    
  - <span data-ttu-id="5497c-118">**номера для подключения (платные)** и бесплатные номера (при наличии);</span><span class="sxs-lookup"><span data-stu-id="5497c-118">**Dial-in numbers (toll)** and toll-free numbers if they are available.</span></span>
    
  - <span data-ttu-id="5497c-p106">**идентификаторы конференции**, используемые для каждого пользователя, планирующего собрания. Некоторые поставщики называют их секретными кодами конференции.</span><span class="sxs-lookup"><span data-stu-id="5497c-p106">**Conference IDs** that are used for each person who schedules meetings. Some ACPs call these conference passcodes.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5497c-121">Если выполнена начальная настройка для стороннего поставщика услуг аудиоконференций, но теперь требуется внести изменения, в нижней части страницы **Мост Microsoft** перейдите по ссылке **Click here to configure a third-party audio conferencing provider (Щелкните здесь, чтобы настроить стороннего поставщика услуг аудиоконференций)**.</span><span class="sxs-lookup"><span data-stu-id="5497c-121">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="5497c-122">При включении аудиоконференции для пользователя и назначении для него стороннего поставщика аудиоконференций номера и идентификаторы (секретные коды) конференции автоматически добавляются в каждое создаваемое им **новое собрание** Skype для бизнеса online.</span><span class="sxs-lookup"><span data-stu-id="5497c-122">When you enable a person for audio conferencing, and assign them a third-party audio conferencing provider, the audio numbers and conference IDs (passcodes) are automatically added to any **new** Skype for Business Online meetings that they create.</span></span>
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-a-user"></a><span data-ttu-id="5497c-123">Назначение пользователю стороннего поставщика услуг аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="5497c-123">How to assign a third-party audio conferencing provider to a user</span></span>

1. <span data-ttu-id="5497c-p107">В **Центр администрирования Skype для бизнеса**щелкните **Пользователи**. Выберите пользователя в списке и нажмите кнопку **Изменить** в области действий.</span><span class="sxs-lookup"><span data-stu-id="5497c-p107">In the **Skype for Business admin center**, choose **Users**. Select the user from the list and click **Edit** in the action pane.</span></span>
    
2. <span data-ttu-id="5497c-126">На странице свойств пользователя щелкните **Аудиоконференция** и введите следующие данные:</span><span class="sxs-lookup"><span data-stu-id="5497c-126">On the user's properties page, click **Audio conferencing** and enter this information:</span></span>
    
  - <span data-ttu-id="5497c-127">**Имя поставщика** Выберите в списке стороннего поставщика.</span><span class="sxs-lookup"><span data-stu-id="5497c-127">**Provider name** Select the third-party provider from the list.</span></span>
    
  - <span data-ttu-id="5497c-128">**Платный номер по умолчанию**: обязательное значение.</span><span class="sxs-lookup"><span data-stu-id="5497c-128">**Default toll number** This is required.</span></span>
    
  - <span data-ttu-id="5497c-129">**Бесплатный номер по умолчанию**: необязательное значение.</span><span class="sxs-lookup"><span data-stu-id="5497c-129">**Default toll-free number** This not required.</span></span>
    
  - <span data-ttu-id="5497c-130">**Идентификатор конференции**: его можно узнать у поставщика услуг аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="5497c-130">**Conference ID** This is provided by your audio conferencing provider.</span></span>
    
3. <span data-ttu-id="5497c-131">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5497c-131">Click **Save**.</span></span>
    
4. <span data-ttu-id="5497c-p108">Отправьте каждому пользователю ПИН-код, полученный от поставщика услуг аудиоконференций. ПИН-код может потребоваться для подключения в качестве организатора или ведущего конференции.</span><span class="sxs-lookup"><span data-stu-id="5497c-p108">Send each person the PIN you received from the audio conferencing provider. The PIN may be required to call in as the conference call organizer or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5497c-134">При использовании стороннего поставщика аудиоконференций вы не можете просматривать или задавать ПИН-коды от имени организаторов собраний.</span><span class="sxs-lookup"><span data-stu-id="5497c-134">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-many-people-at-the-same-time"></a><span data-ttu-id="5497c-135">Одновременное назначение поставщика аудиоконференций нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="5497c-135">How to assign a third-party audio conferencing provider to many people at the same time</span></span>

1. <span data-ttu-id="5497c-p109">В **Центр администрирования Skype для бизнеса**выберите **Аудиоконференция** > **Мост Microsoft**. В нижней части страницы щелкните **Если вы хотите настроить сторонний поставщик аудиоконференций, щелкните здесь**.</span><span class="sxs-lookup"><span data-stu-id="5497c-p109">In the **Skype for Business admin center**, choose **Audio conferencing** > **Microsoft bridge**. At the bottom of the page, click the link in **If you would like to configure a third-party audio conferencing provider instead, click here**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5497c-138">Если вы выполнили начальной настройки для ACP сторонних производителей, но необходимо внести изменения в нижней части страницы **Microsoft Bridge** , **щелкните здесь, чтобы настроить поставщика аудиоконференций сторонних производителей**.</span><span class="sxs-lookup"><span data-stu-id="5497c-138">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page, **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
2. <span data-ttu-id="5497c-p110">На странице **Настройка стороннего поставщика аудиоконференц-связи** в разделе **Импорт и экспорт пользователей** щелкните **Мастер экспорта**, а затем выполните действия, предложенные **мастером экспорта пользователей**. Закончив работу с мастером, вы получите файл со списком пользователей, для которых требуется настроить аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="5497c-p110">On the **Configure a third party audio conferencing provider** page, under **Import and export users**, click **Export wizard**, and then follow the steps in the **Export Users wizard**. When you finish, you'll have a file that lists the people you want to set up for audio conferencing.</span></span>
    
3. <span data-ttu-id="5497c-p111">Отправьте созданный файл стороннему поставщику аудиоконференций. Он добавит сведения, необходимые для аудиоконференции, для пользователей в файле и вернет файл вам.</span><span class="sxs-lookup"><span data-stu-id="5497c-p111">Send the file you created to your third-party audio conferencing provider. They will add audio conferencing information for the people listed in the file, and then return the file to you.</span></span>
    
4. <span data-ttu-id="5497c-p112">Обязательно убедитесь, что в возвращенном файле содержатся правильные сведения. Иногда бывает, что не для всех пользователей в списке указываются нужные сведения.</span><span class="sxs-lookup"><span data-stu-id="5497c-p112">Double-check that the returned file has the right information in it. We've heard of instances where not everyone listed in the file got the right information.</span></span>
    
5. <span data-ttu-id="5497c-145">На странице **Настройка стороннего поставщика аудиоконференц-связи** в разделе **Импорт и экспорт пользователей** щелкните **Мастер импорта**, а затем выполните действия, предложенные **мастером импорта пользователей.**</span><span class="sxs-lookup"><span data-stu-id="5497c-145">On the **Configure a third-party audio conferencing provider page**, under **Import and export users**, click **Import wizard**, and then follow the steps in the **Import Users wizard**</span></span>
    
6. <span data-ttu-id="5497c-p113">Отправьте каждому пользователю ПИН-код, полученный от поставщика аудиоконференций. ПИН-код может потребоваться для подключения в качестве организатора или ведущего конференции.</span><span class="sxs-lookup"><span data-stu-id="5497c-p113">Send each person the PIN you received from the audio conferencing provider. The PIN may be required to call in as the conference call organizer, or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5497c-148">При использовании стороннего поставщика аудиоконференций вы не можете просматривать или задавать ПИН-коды от имени организаторов собраний.</span><span class="sxs-lookup"><span data-stu-id="5497c-148">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="when-to-use-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="5497c-149">Когда рекомендуется использовать стороннего поставщика аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="5497c-149">When to use a third-party audio conferencing provider</span></span>

<span data-ttu-id="5497c-p114">Если вы находитесь в стране или регионе, где аудиоконференция в Office 365 недоступна, качество службы будет недостаточно высоким из-за расположения. Если у вас есть текущий контракт со сторонним поставщиком услуг аудиоконференций, рекомендуем пользоваться услугами стороннего поставщика. В противном случае в качестве поставщика услуг аудиоконференций рекомендуется выбирать Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5497c-p114">If you are in a country or region where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract with a third-party audio conferencing provider, we recommend using a third-party audio conferencing provider. Otherwise, we recommend using Microsoft as your audio conferencing provider.</span></span>
  
## <a name="automate-assigning-the-third-party-audio-conferencing-provider-by-using-windows-powershell"></a><span data-ttu-id="5497c-152">Автоматизация назначения стороннего поставщика аудиоконференций с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5497c-152">Automate assigning the third-party audio conferencing provider by using Windows PowerShell</span></span>

- <span data-ttu-id="5497c-153">Чтобы сэкономить время или автоматизировать процесс, используйте командлет [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851).</span><span class="sxs-lookup"><span data-stu-id="5497c-153">To save time or automate this, you can use the [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) cmdlet.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5497c-p115">Чтобы выбрать стороннего поставщика услуг аудиоконференций вместо Майкрософт, необходимо удалить компанию Майкрософт как поставщика услуг аудиоконференций. Это можно сделать с помощью командлета [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ).</span><span class="sxs-lookup"><span data-stu-id="5497c-p115">To change the audio provider from Microsoft to a third-party audio conferencing provider, you must remove Microsoft as the audio conferencing provider. To do this, use the [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) cmdlet.</span></span>
  
- <span data-ttu-id="5497c-156">Дополнительные сведения об использовании Windows PowerShell см. в статье [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="5497c-156">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
    
## <a name="what-else-do-i-need-to-know"></a><span data-ttu-id="5497c-157">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="5497c-157">What else do I need to know?</span></span>

<span data-ttu-id="5497c-158">Лица в вашей организации можно использовать только один поставщик услуг аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="5497c-158">A person in your organization can only use one audio conferencing provider.</span></span> <span data-ttu-id="5497c-159">Чтобы изменить поставщика аудиоконференций другого пользователя в корпорацию Майкрософт, видеть [Перемещение пользователя поставщика аудиоконференций в корпорацию Майкрософт](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) и [Назначить Microsoft в качестве поставщика аудиоконференций](assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="5497c-159">To change a person's audio conferencing provider to Microsoft, see [Moving a user's audio conferencing provider to Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5497c-160">См. также:</span><span class="sxs-lookup"><span data-stu-id="5497c-160">Related Topics</span></span>

[<span data-ttu-id="5497c-161">Настройка аудиоконференций в Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5497c-161">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  
[<span data-ttu-id="5497c-162">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5497c-162">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

