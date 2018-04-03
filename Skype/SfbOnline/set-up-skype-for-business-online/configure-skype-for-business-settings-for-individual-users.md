---
title: Скайп Настройка "Администраторы" для бизнеса параметры для отдельных пользователей
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: 'Узнайте, как изменить Скайп для бизнеса параметры для отдельных пользователей, таких как: аудио- и видеоконференций, собраний и регистрации вызовов. '
ms.openlocfilehash: 8659434542696ccb37a0353cd491cc0d01f01e30
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2018
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="e9f07-103">Администраторы: Настройка Скайп Business для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="e9f07-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="e9f07-104">В этой статье объясняется, как администраторы настраивать Скайп для бизнеса, для небольшого числа пользователей.</span><span class="sxs-lookup"><span data-stu-id="e9f07-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="e9f07-105">Для выполнения этих действий в пакетном режиме, включены ссылки на командлетов Windows PowerShell, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="e9f07-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="e9f07-106">Чтобы разрешить (или заблокировать) всем сотрудникам организации для взаимодействия с внешним пользователям, см.</span><span class="sxs-lookup"><span data-stu-id="e9f07-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="e9f07-107">[Разрешить пользователям включать поддержку для связи внешних Скайп для бизнес-пользователи](allow-users-to-contact-external-skype-for-business-users.md): можно разрешить вашей организации используйте advanced Скайп для функций Business (общий доступ настольных компьютеров, внешнего вида для пользователей, которые через Интернет, и т.д.) для взаимодействия с пользователями в определенном надежные (федеративных) business.</span><span class="sxs-lookup"><span data-stu-id="e9f07-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="e9f07-108">В статье также описываются способы заблокировать обмен данными с определенных доменов.</span><span class="sxs-lookup"><span data-stu-id="e9f07-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="e9f07-109">[Сообщите Скайп для бизнес-пользователи добавлять контакты Скайп](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="e9f07-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="e9f07-110">Позволяет организации использовать Скайп для бизнеса для поиска и обмена мгновенными Сообщениями пользователей Скайп бесплатное приложение.</span><span class="sxs-lookup"><span data-stu-id="e9f07-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="e9f07-111">Настройка общих параметров для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="e9f07-111">Configure general settings for one user</span></span>
<span data-ttu-id="e9f07-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="e9f07-112"></span></span>

<span data-ttu-id="e9f07-113">Необходимо иметь [разрешения администратора](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) для выполнения следующих действий.</span><span class="sxs-lookup"><span data-stu-id="e9f07-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>
  
1. <span data-ttu-id="e9f07-114">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="e9f07-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="e9f07-115">Выберите **Центры администрирования** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="e9f07-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="e9f07-116">Выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="e9f07-116">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="e9f07-118">Выберите пользователей, которые требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="e9f07-118">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="e9f07-119">В области справа выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e9f07-119">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="e9f07-121">На странице " **Общие** параметры" установите или снимите флажок рядом с пунктом функции, которые требуется изменить и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e9f07-121">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="e9f07-122">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="e9f07-122">**Option**</span></span>|<span data-ttu-id="e9f07-123">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="e9f07-123">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e9f07-124">Аудио и видео высокой Четкости</span><span class="sxs-lookup"><span data-stu-id="e9f07-124">Audio and HD video</span></span>  <br/> |<span data-ttu-id="e9f07-125">Разрешить этой человека записывать аудио собрания, аудио- и видеоконференций собраний или запретить их для планирования любого meeetings (нет).</span><span class="sxs-lookup"><span data-stu-id="e9f07-125">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meeetings (none).</span></span>  <br/> |
|<span data-ttu-id="e9f07-126">Запись бесед и собраний</span><span class="sxs-lookup"><span data-stu-id="e9f07-126">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="e9f07-127">Выберите, что этот человек разрешается вести запись.</span><span class="sxs-lookup"><span data-stu-id="e9f07-127">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="e9f07-128">Этот параметр недоступен с Скайп для базовой бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e9f07-128">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="e9f07-129">Для соответствия требованиям отключите не архивируются функции</span><span class="sxs-lookup"><span data-stu-id="e9f07-129">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="e9f07-130">Выберите этот параметр, если вы закону, чтобы сохранить электронных.</span><span class="sxs-lookup"><span data-stu-id="e9f07-130">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="e9f07-131">При выборе этого параметра отключает функции, которые не регистрируются при наличии [Хранения на месте](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) настройки в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="e9f07-131">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center.</span></span> <span data-ttu-id="e9f07-132">Отключает следующие функции:</span><span class="sxs-lookup"><span data-stu-id="e9f07-132">It turns off the following features:</span></span> <br/>  <span data-ttu-id="e9f07-133">Передача файлов через службу мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="e9f07-133">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="e9f07-134">Общие страницы OneNote</span><span class="sxs-lookup"><span data-stu-id="e9f07-134">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="e9f07-135">Примечания PowerPoint</span><span class="sxs-lookup"><span data-stu-id="e9f07-135">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="e9f07-136">Чтобы настроить эти параметры в пакетном режиме, с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9f07-136">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="e9f07-137">См.: [Управление политики в Скайп для бизнеса в Интернет](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="e9f07-137">See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="e9f07-138">Блокировать внешней связи</span><span class="sxs-lookup"><span data-stu-id="e9f07-138">Block external communications</span></span>
<span data-ttu-id="e9f07-139"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="e9f07-139"></span></span>

<span data-ttu-id="e9f07-140">После вы [позволить Скайп для бизнес-пользователям добавлять контакты Скайп](let-skype-for-business-users-add-skype-contacts.md) для всех пользователей в вашей компании можно выборочно заблокировать внешних коммуникаций для определенных пользователей, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e9f07-140">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="e9f07-141">Выберите **пользователей**, выберите пользователей, параметры которого требуется отключить и выберите команду **Изменить** ![изменить](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="e9f07-141">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="e9f07-142">Выбор **внешних коммуникаций**, а затем снимите нужные флажки:</span><span class="sxs-lookup"><span data-stu-id="e9f07-142">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
  - <span data-ttu-id="e9f07-143">**Внешние Скайп для бизнес-пользователи**: снимите этот флажок, если необходимо запретить пользователям связываться с Скайп для бизнес-пользователей в федеративных доменах.</span><span class="sxs-lookup"><span data-stu-id="e9f07-143">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
  - <span data-ttu-id="e9f07-144">**Внешние Скайп пользователей**: Если вы не требуется, чтобы пользователь могли взаимодействовать с другими пользователями, у которых freeSkype приложения, снимите флажок.</span><span class="sxs-lookup"><span data-stu-id="e9f07-144">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="e9f07-145">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="e9f07-145">Click **Save**.</span></span>
    
<span data-ttu-id="e9f07-146">Чтобы настроить эти параметры в пакетном режиме, с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9f07-146">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="e9f07-147">В разделе [Управление коммуникаций в Скайп для бизнеса в Интернет с помощью внешних пользователей и организаций](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="e9f07-147">See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="e9f07-148">Изменение параметров звукового конференц-связи для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="e9f07-148">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="e9f07-149"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="e9f07-149"></span></span>

1. <span data-ttu-id="e9f07-150">Выберите **пользователей**, установите аудиоконференций, параметры которого требуется изменить, пользователю и выберите команду **Изменить** ![изменить](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="e9f07-150">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="e9f07-151">Выбрать **звук конференц-связи**, выберите поставщика аудиоконференций, введите или измените требуемые сведения и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e9f07-151">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="e9f07-152">**Настройка аудиоконференции**</span><span class="sxs-lookup"><span data-stu-id="e9f07-152">**Audio conferencing setting**</span></span>|<span data-ttu-id="e9f07-153">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e9f07-153">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e9f07-154">**Имя поставщика**</span><span class="sxs-lookup"><span data-stu-id="e9f07-154">**Provider name**</span></span> <br/> |<span data-ttu-id="e9f07-155">Выберите поставщика из списка.</span><span class="sxs-lookup"><span data-stu-id="e9f07-155">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="e9f07-156">**Платный номер** (обязательно)</span><span class="sxs-lookup"><span data-stu-id="e9f07-156">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="e9f07-157">Для ACP сторонних производителей эти номера телефонов, из них, полученные от поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="e9f07-157">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="e9f07-158">Если пользователь использует Microsoft в качестве поставщика аудиоконференций, это будут номера, заданные для звукового конференц-канала.</span><span class="sxs-lookup"><span data-stu-id="e9f07-158">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="e9f07-159">Форматирование чисел, как они отображаются в Скайп для бизнеса и группами Майкрософт приглашения на собрания.</span><span class="sxs-lookup"><span data-stu-id="e9f07-159">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="e9f07-160">**Бесплатный номер**</span><span class="sxs-lookup"><span data-stu-id="e9f07-160">**Toll-free number**</span></span> <br/> |<span data-ttu-id="e9f07-161">Для ACP сторонних производителей эти номера телефонов, из них, полученные от поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="e9f07-161">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="e9f07-162">Если пользователь использует Microsoft в качестве поставщика аудиоконференций, это будут номера, заданные для звукового конференц-канала.</span><span class="sxs-lookup"><span data-stu-id="e9f07-162">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="e9f07-163">Форматирование чисел, как они отображаются в Скайп для бизнеса и группами Майкрософт приглашения на собрания.</span><span class="sxs-lookup"><span data-stu-id="e9f07-163">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="e9f07-164">**Идентификатор конференции и ПИН-кода** (обязательно)</span><span class="sxs-lookup"><span data-stu-id="e9f07-164">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="e9f07-165">Участник ПИН-код или конференции код, используется для присоединения к собраниям, запланированных данным пользователем и предоставляются от поставщика аудиоконференций сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="e9f07-165">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="e9f07-166">Если пользователь использует Microsoft в качестве поставщика аудиоконференций, это не требуется указать.</span><span class="sxs-lookup"><span data-stu-id="e9f07-166">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="e9f07-167">Чтобы настроить эти параметры в пакетном режиме, с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9f07-167">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="e9f07-168">В разделе [Задайте телефона, номера, находящимся на приглашает](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="e9f07-168">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="e9f07-169">See also</span><span class="sxs-lookup"><span data-stu-id="e9f07-169">Related topics</span></span> 

[<span data-ttu-id="e9f07-170">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e9f07-170">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="e9f07-171">Лицензирование надстроек Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e9f07-171">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 