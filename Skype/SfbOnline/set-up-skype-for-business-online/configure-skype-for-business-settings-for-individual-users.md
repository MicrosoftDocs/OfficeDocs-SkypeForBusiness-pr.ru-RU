---
title: Администраторы настраивают параметры Skype для бизнеса для отдельных пользователей
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
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
description: 'Сведения о том, как изменить параметры Skype для бизнеса для отдельных пользователей, например, голосовые и видеоконференции, записи звонков и собраний. '
ms.openlocfilehash: 8fa6af4099238f9ab908de2ea8c37340f93c3dff
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494172"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="ec72b-103">Администраторам: настройка параметров Skype для бизнеса для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="ec72b-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="ec72b-104">В этой статье объясняется, как администраторы настраивают Skype для бизнеса для небольшого количества пользователей.</span><span class="sxs-lookup"><span data-stu-id="ec72b-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="ec72b-105">Чтобы выполнить эти действия, мы включили ссылки на командлеты Windows PowerShell, которые вы можете использовать.</span><span class="sxs-lookup"><span data-stu-id="ec72b-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="ec72b-106">Чтобы разрешить (или заблокировать) всем сотрудникам Организации общаться с внешними людьми, ознакомьтесь со из:</span><span class="sxs-lookup"><span data-stu-id="ec72b-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="ec72b-107">[Разрешите пользователям связываться с внешними пользователями Skype для бизнеса](allow-users-to-contact-external-skype-for-business-users.md): вы можете использовать в своей организации расширенные функции Skype для бизнеса (общий доступ к рабочему столу и т. д.), чтобы общаться с людьми в определенном надежном (федеративного) компании.</span><span class="sxs-lookup"><span data-stu-id="ec72b-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="ec72b-108">В этой статье также объясняется, как заблокировать связь с определенными доменами.</span><span class="sxs-lookup"><span data-stu-id="ec72b-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="ec72b-109">[Позвольте пользователям Skype для бизнеса добавлять контакты Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="ec72b-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="ec72b-110">Вы можете использовать Skype для бизнеса для поиска и обмена мгновенными сообщениями с другими людьми, использующими Skype — бесплатное приложение.</span><span class="sxs-lookup"><span data-stu-id="ec72b-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="ec72b-111">Настройка общих параметров для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="ec72b-111">Configure general settings for one user</span></span>
<span data-ttu-id="ec72b-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="ec72b-112"></span></span>

<span data-ttu-id="ec72b-113">Для выполнения этих действий требуются [разрешения администратора](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) .</span><span class="sxs-lookup"><span data-stu-id="ec72b-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="ec72b-114">![Значок, показывающий логотип](../images/sfb-logo-30x30.png) Skype для бизнеса **, с помощью центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="ec72b-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="ec72b-115">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="ec72b-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="ec72b-116">Выберите **Центры администрирования** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="ec72b-116">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="ec72b-117">Выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="ec72b-117">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="ec72b-119">Выберите пользователей, которых вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="ec72b-119">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="ec72b-120">В области справа выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="ec72b-120">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="ec72b-122">На странице параметров **Общие** установите или снимите флажки рядом с функциями, которые нужно изменить, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ec72b-122">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="ec72b-123">**Действие**</span><span class="sxs-lookup"><span data-stu-id="ec72b-123">**Option**</span></span>|<span data-ttu-id="ec72b-124">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="ec72b-124">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ec72b-125">Аудио и видео в формате HD</span><span class="sxs-lookup"><span data-stu-id="ec72b-125">Audio and HD video</span></span>  <br/> |<span data-ttu-id="ec72b-126">Предоставление этому человеку возможности записи голосовых и видеособраний, а также не разрешать им планировать собрания (нет).</span><span class="sxs-lookup"><span data-stu-id="ec72b-126">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="ec72b-127">Запись бесед и собраний</span><span class="sxs-lookup"><span data-stu-id="ec72b-127">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="ec72b-128">Выберите, кому будет разрешено записывать этот человек.</span><span class="sxs-lookup"><span data-stu-id="ec72b-128">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="ec72b-129">Этот параметр недоступен в Skype для бизнеса базовый.</span><span class="sxs-lookup"><span data-stu-id="ec72b-129">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="ec72b-130">Для обеспечения соответствия требованиям отключите не архивированные функции.</span><span class="sxs-lookup"><span data-stu-id="ec72b-130">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="ec72b-131">Выберите этот параметр, если вы обязаны хранить данные, хранящиеся в электронном виде.</span><span class="sxs-lookup"><span data-stu-id="ec72b-131">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="ec72b-132">Если выбрать этот параметр, функции, не захваченные при наличии [места на месте](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) в центре администрирования Exchange, будут отключены.</span><span class="sxs-lookup"><span data-stu-id="ec72b-132">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in the Exchange admin center.</span></span> <span data-ttu-id="ec72b-133">Это выключает следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="ec72b-133">It turns off the following features:</span></span> <br/>  <span data-ttu-id="ec72b-134">Передача файлов через службу мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="ec72b-134">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="ec72b-135">Общие страницы OneNote</span><span class="sxs-lookup"><span data-stu-id="ec72b-135">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="ec72b-136">Примечания PowerPoint</span><span class="sxs-lookup"><span data-stu-id="ec72b-136">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="ec72b-137">Чтобы настроить эти параметры в массовом режиме, используйте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec72b-137">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="ec72b-138">Ознакомьтесь со [сведениями о настройке компьютера для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ec72b-138">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="ec72b-139">Блокировка внешней связи</span><span class="sxs-lookup"><span data-stu-id="ec72b-139">Block external communications</span></span>
<span data-ttu-id="ec72b-140"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="ec72b-140"></span></span>

<span data-ttu-id="ec72b-141">После того как вы [решите пользователям Skype для бизнеса добавлять контакты Skype](let-skype-for-business-users-add-skype-contacts.md) для всех пользователей вашей компании, вы можете заблокировать внешнюю связь для определенных пользователей, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ec72b-141">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="ec72b-142">Выберите пункт **Пользователи**, выберите пользователей, параметры которых вы хотите отключить, и нажмите **изменить** ![изменения](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="ec72b-142">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="ec72b-143">Выберите **внешние подключения**и снимите соответствующие флажки.</span><span class="sxs-lookup"><span data-stu-id="ec72b-143">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="ec72b-144">**Внешние пользователи Skype для бизнеса**: снимите этот флажок, если вы не хотите, чтобы пользователь мог общаться с пользователями Skype для бизнеса в федеративных доменах.</span><span class="sxs-lookup"><span data-stu-id="ec72b-144">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="ec72b-145">**Внешние пользователи Skype**: снимите этот флажок, если вы не хотите, чтобы пользователь мог общаться с людьми, использующими приложение пользователями бесплатного.</span><span class="sxs-lookup"><span data-stu-id="ec72b-145">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="ec72b-146">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ec72b-146">Click **Save**.</span></span>
    
<span data-ttu-id="ec72b-147">Чтобы настроить эти параметры в массовом режиме, используйте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec72b-147">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="ec72b-148">Ознакомьтесь со [сведениями о настройке компьютера для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ec72b-148">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="ec72b-149">Изменение параметров голосовой конференции для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="ec72b-149">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="ec72b-150"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="ec72b-150"></span></span>

1. <span data-ttu-id="ec72b-151">Выберите пункт **Пользователи**, выберите пользователя, параметры голосовой связи которого вы хотите изменить, и нажмите кнопку **изменить** ![изменения](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="ec72b-151">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="ec72b-152">Выберите пункт **Голосовая конференция**, выберите поставщика видеоконференций, введите или измените необходимые данные, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ec72b-152">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="ec72b-153">**Настройка аудиоконференции**</span><span class="sxs-lookup"><span data-stu-id="ec72b-153">**Audio conferencing setting**</span></span>|<span data-ttu-id="ec72b-154">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ec72b-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ec72b-155">**Имя поставщика**</span><span class="sxs-lookup"><span data-stu-id="ec72b-155">**Provider name**</span></span> <br/> |<span data-ttu-id="ec72b-156">Выберите поставщика из списка.</span><span class="sxs-lookup"><span data-stu-id="ec72b-156">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="ec72b-157">**Платный номер** (обязательно)</span><span class="sxs-lookup"><span data-stu-id="ec72b-157">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="ec72b-158">В случае с независимыми телефонными номерами эти номера телефонов являются теми, которые вы получили от поставщика видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="ec72b-158">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="ec72b-159">Если пользователь выбрал Microsoft в качестве поставщика аудиоконференций, это будут номера, заданные для канала аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="ec72b-159">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="ec72b-160">Отформатируйте номера в том виде, в котором они должны отображаться в приглашениях на собрания в Skype для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ec72b-160">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="ec72b-161">**Бесплатный номер**</span><span class="sxs-lookup"><span data-stu-id="ec72b-161">**Toll-free number**</span></span> <br/> |<span data-ttu-id="ec72b-162">В случае с независимыми телефонными номерами эти номера телефонов являются теми, которые вы получили от поставщика видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="ec72b-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="ec72b-163">Если пользователь выбрал Microsoft в качестве поставщика аудиоконференций, это будут номера, заданные для канала аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="ec72b-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="ec72b-164">Отформатируйте номера в том виде, в котором они должны отображаться в приглашениях на собрания в Skype для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ec72b-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="ec72b-165">**Идентификатор конференции и ПИН-** код предусмотрен</span><span class="sxs-lookup"><span data-stu-id="ec72b-165">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="ec72b-166">ПИН-код участника или Конференция, который используется для присоединения к собраниям, запланированным этим пользователем, и предоставлено сторонним поставщиком услуг голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="ec72b-166">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="ec72b-167">Если пользователь использует Microsoft в качестве поставщика видеоконференций, это не обязательно.</span><span class="sxs-lookup"><span data-stu-id="ec72b-167">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="ec72b-168">Чтобы настроить эти параметры в массовом режиме, используйте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec72b-168">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="ec72b-169">[В разделе Настройка номеров телефонов, включенных в приглашения,](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Настройте компьютер для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ec72b-169">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="ec72b-170">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ec72b-170">Related topics</span></span> 

[<span data-ttu-id="ec72b-171">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ec72b-171">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="ec72b-172">Лицензирование надстроек Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec72b-172">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
