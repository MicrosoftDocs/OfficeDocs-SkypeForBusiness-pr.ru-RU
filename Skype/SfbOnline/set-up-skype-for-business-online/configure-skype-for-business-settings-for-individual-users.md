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
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: 'Сведения о том, как изменить параметры Skype для бизнеса для отдельных пользователей, например, голосовые и видеоконференции, записи звонков и собраний. '
ms.openlocfilehash: 546e693dd1fb6e9becf7119c35d7b00875eda99a
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739177"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="1a413-103">Администраторы: настройка параметров Skype для бизнеса для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="1a413-103">Admins: Configure Skype for Business settings for individual users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a413-104">Центр администрирования Microsoft Teams заменяет центр администрирования Skype для бизнеса (устаревший портал).</span><span class="sxs-lookup"><span data-stu-id="1a413-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="1a413-105">Все параметры, необходимые для управления Skype для бизнеса, теперь находятся в центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="1a413-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="1a413-106">Дополнительные сведения можно найти в разделе [Управление параметрами Skype для бизнеса в центре администрирования Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="1a413-106">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="1a413-107">В этой статье объясняется, как администраторы настраивают Skype для бизнеса для небольшого количества пользователей.</span><span class="sxs-lookup"><span data-stu-id="1a413-107">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="1a413-108">Чтобы выполнить эти действия, мы включили ссылки на командлеты Windows PowerShell, которые вы можете использовать.</span><span class="sxs-lookup"><span data-stu-id="1a413-108">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="1a413-109">Чтобы разрешить (или заблокировать) всем сотрудникам Организации общаться с внешними людьми, ознакомьтесь со из:</span><span class="sxs-lookup"><span data-stu-id="1a413-109">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="1a413-110">[Разрешите пользователям связываться с внешними пользователями Skype для бизнеса](allow-users-to-contact-external-skype-for-business-users.md): вы можете использовать в своей организации расширенные функции Skype для бизнеса (общий доступ к рабочему столу и т. д.), чтобы общаться с людьми в определенном надежном (федеративного) компании.</span><span class="sxs-lookup"><span data-stu-id="1a413-110">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="1a413-111">В этой статье также объясняется, как заблокировать связь с определенными доменами.</span><span class="sxs-lookup"><span data-stu-id="1a413-111">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="1a413-112">[Позвольте пользователям Skype для бизнеса добавлять контакты Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="1a413-112">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="1a413-113">Вы можете использовать Skype для бизнеса для поиска и обмена мгновенными сообщениями с другими людьми, использующими Skype — бесплатное приложение.</span><span class="sxs-lookup"><span data-stu-id="1a413-113">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="1a413-114">Настройка общих параметров для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="1a413-114">Configure general settings for one user</span></span>
<span data-ttu-id="1a413-115"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="1a413-115"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="1a413-116">Для выполнения этих действий требуются [разрешения администратора](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) .</span><span class="sxs-lookup"><span data-stu-id="1a413-116">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="1a413-117">![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="1a413-117">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="1a413-118">Войдите в свою рабочую или учебную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="1a413-118">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="1a413-119">Выберите **Центры администрирования** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="1a413-119">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="1a413-120">Выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="1a413-120">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="1a413-122">Выберите пользователей, которых вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="1a413-122">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="1a413-123">В области справа выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="1a413-123">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="1a413-125">На странице параметров **Общие** установите или снимите флажки рядом с функциями, которые нужно изменить, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1a413-125">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="1a413-126">**Действие**</span><span class="sxs-lookup"><span data-stu-id="1a413-126">**Option**</span></span>|<span data-ttu-id="1a413-127">**Details**</span><span class="sxs-lookup"><span data-stu-id="1a413-127">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1a413-128">Аудио и видео в формате HD</span><span class="sxs-lookup"><span data-stu-id="1a413-128">Audio and HD video</span></span>  <br/> |<span data-ttu-id="1a413-129">Предоставление этому человеку возможности записи голосовых и видеособраний, а также не разрешать им планировать собрания (нет).</span><span class="sxs-lookup"><span data-stu-id="1a413-129">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="1a413-130">Запись бесед и собраний</span><span class="sxs-lookup"><span data-stu-id="1a413-130">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="1a413-131">Выберите, кому будет разрешено записывать этот человек.</span><span class="sxs-lookup"><span data-stu-id="1a413-131">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="1a413-132">Этот параметр недоступен в Skype для бизнеса базовый.</span><span class="sxs-lookup"><span data-stu-id="1a413-132">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="1a413-133">Для обеспечения соответствия требованиям отключите не архивированные функции.</span><span class="sxs-lookup"><span data-stu-id="1a413-133">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="1a413-134">Выберите этот параметр, если вы обязаны хранить данные, хранящиеся в электронном виде.</span><span class="sxs-lookup"><span data-stu-id="1a413-134">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="1a413-135">Если выбрать этот параметр, функции, не захваченные при наличии [места на месте](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) в центре администрирования Exchange, будут отключены.</span><span class="sxs-lookup"><span data-stu-id="1a413-135">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) set up in the Exchange admin center.</span></span> <span data-ttu-id="1a413-136">Это выключает следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="1a413-136">It turns off the following features:</span></span> <br/>  <span data-ttu-id="1a413-137">Передача файлов через службу мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="1a413-137">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="1a413-138">Общие страницы OneNote</span><span class="sxs-lookup"><span data-stu-id="1a413-138">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="1a413-139">Примечания PowerPoint</span><span class="sxs-lookup"><span data-stu-id="1a413-139">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="1a413-140">Чтобы настроить эти параметры в массовом режиме, используйте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a413-140">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="1a413-141">Ознакомьтесь со [сведениями о настройке компьютера для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1a413-141">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="1a413-142">Блокировка внешней связи</span><span class="sxs-lookup"><span data-stu-id="1a413-142">Block external communications</span></span>
<span data-ttu-id="1a413-143"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="1a413-143"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="1a413-144">После того как вы [решите пользователям Skype для бизнеса добавлять контакты Skype](let-skype-for-business-users-add-skype-contacts.md) для всех пользователей вашей компании, вы можете заблокировать внешнюю связь для определенных пользователей, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1a413-144">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="1a413-145">Выберите пункт **Пользователи**, выберите пользователей, параметры которых вы хотите отключить, и нажмите **изменить** ![ изменения ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .</span><span class="sxs-lookup"><span data-stu-id="1a413-145">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="1a413-146">Выберите **внешние подключения**и снимите соответствующие флажки.</span><span class="sxs-lookup"><span data-stu-id="1a413-146">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="1a413-147">**Внешние пользователи Skype для бизнеса**: снимите этот флажок, если вы не хотите, чтобы пользователь мог общаться с пользователями Skype для бизнеса в федеративных доменах.</span><span class="sxs-lookup"><span data-stu-id="1a413-147">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="1a413-148">**Внешние пользователи Skype**: снимите этот флажок, если вы не хотите, чтобы пользователь мог общаться с людьми, использующими приложение пользователями бесплатного.</span><span class="sxs-lookup"><span data-stu-id="1a413-148">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="1a413-149">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1a413-149">Click **Save**.</span></span>
    
<span data-ttu-id="1a413-150">Чтобы настроить эти параметры в массовом режиме, используйте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a413-150">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="1a413-151">Ознакомьтесь со [сведениями о настройке компьютера для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1a413-151">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="1a413-152">Изменение параметров голосовой конференции для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="1a413-152">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="1a413-153"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="1a413-153"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="1a413-154">Выберите пункт **Пользователи**, выберите пользователя, параметры голосовой связи которого вы хотите изменить, и нажмите кнопку **изменить** ![ изменения ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .</span><span class="sxs-lookup"><span data-stu-id="1a413-154">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="1a413-155">Выберите пункт **Голосовая конференция**, выберите поставщика видеоконференций, введите или измените необходимые данные, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1a413-155">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="1a413-156">**Настройка аудиоконференции**</span><span class="sxs-lookup"><span data-stu-id="1a413-156">**Audio conferencing setting**</span></span>|<span data-ttu-id="1a413-157">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1a413-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1a413-158">**Имя поставщика**</span><span class="sxs-lookup"><span data-stu-id="1a413-158">**Provider name**</span></span> <br/> |<span data-ttu-id="1a413-159">Выберите поставщика из списка.</span><span class="sxs-lookup"><span data-stu-id="1a413-159">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="1a413-160">**Платный номер** (обязательно)</span><span class="sxs-lookup"><span data-stu-id="1a413-160">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="1a413-161">В случае с независимыми телефонными номерами эти номера телефонов являются теми, которые вы получили от поставщика видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="1a413-161">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="1a413-162">Если пользователь выбрал Microsoft в качестве поставщика аудиоконференций, это будут номера, заданные для канала аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="1a413-162">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="1a413-163">Отформатируйте номера в том виде, в котором они должны отображаться в приглашениях на собрания в Skype для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1a413-163">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="1a413-164">**Бесплатный номер**</span><span class="sxs-lookup"><span data-stu-id="1a413-164">**Toll-free number**</span></span> <br/> |<span data-ttu-id="1a413-165">В случае с независимыми телефонными номерами эти номера телефонов являются теми, которые вы получили от поставщика видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="1a413-165">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="1a413-166">Если пользователь выбрал Microsoft в качестве поставщика аудиоконференций, это будут номера, заданные для канала аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="1a413-166">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="1a413-167">Отформатируйте номера в том виде, в котором они должны отображаться в приглашениях на собрания в Skype для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1a413-167">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="1a413-168">**Идентификатор конференции и ПИН-код** (обязательно)</span><span class="sxs-lookup"><span data-stu-id="1a413-168">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="1a413-169">ПИН-код участника или Конференция, который используется для присоединения к собраниям, запланированным этим пользователем, и предоставлено сторонним поставщиком услуг голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="1a413-169">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="1a413-170">Если пользователь использует Microsoft в качестве поставщика видеоконференций, это не обязательно.</span><span class="sxs-lookup"><span data-stu-id="1a413-170">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="1a413-171">Чтобы настроить эти параметры в массовом режиме, используйте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a413-171">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="1a413-172">[В разделе Настройка номеров телефонов, включенных в приглашения,](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Настройте компьютер для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1a413-172">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="1a413-173">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1a413-173">Related topics</span></span> 

[<span data-ttu-id="1a413-174">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="1a413-174">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="1a413-175">Лицензирование надстроек Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1a413-175">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
