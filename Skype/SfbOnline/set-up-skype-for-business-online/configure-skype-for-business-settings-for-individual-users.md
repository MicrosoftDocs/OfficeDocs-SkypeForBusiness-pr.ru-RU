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
description: 'Узнайте, как изменить параметры Skype для бизнеса для отдельных пользователей, например аудио- и видеоконференцию, запись звонков и собраний. '
ms.openlocfilehash: 5ddad9b1502d0a271c20c412731c9872e247be1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093393"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="46414-103">Администраторы: настройка параметров Skype для бизнеса для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="46414-103">Admins: Configure Skype for Business settings for individual users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46414-104">Центр администрирования Microsoft Teams заменил Центр администрирования Skype для бизнеса (устаревший портал).</span><span class="sxs-lookup"><span data-stu-id="46414-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="46414-105">Все параметры управления Skype для бизнеса теперь находятся в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="46414-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="46414-106">Чтобы управлять функциями Skype для бизнеса в Центре администрирования Teams, вам должна быть назначена роль администратора [Azure AD](/azure/active-directory/roles/permissions-reference) глобального администратора или администратор Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="46414-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="46414-107">Дополнительные сведения см. в статье [Управление параметрами Skype для бизнеса в Центре администрирования Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="46414-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="46414-108">В этой статье объясняется, как администраторы настраивают Skype для бизнеса для небольшого количества пользователей.</span><span class="sxs-lookup"><span data-stu-id="46414-108">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="46414-109">Для этого мы включили ссылки на Windows PowerShell, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="46414-109">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="46414-110">Чтобы разрешить (или заблокировать) всех людей в вашей компании общаться с внешними пользователями, см.:</span><span class="sxs-lookup"><span data-stu-id="46414-110">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="46414-111">Разрешить пользователям связываться с внешними пользователями [Skype](allow-users-to-contact-external-skype-for-business-users.md)для бизнеса. Вы можете разрешить вашей организации использовать расширенные функции Skype для бизнеса (совместное использование рабочих столов, поиск пользователей в сети и т. д.) для связи с пользователями в определенной надежной (федерате) организации.</span><span class="sxs-lookup"><span data-stu-id="46414-111">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="46414-112">В этой статье также рассказывается, как заблокировать взаимодействие с определенными доменами.</span><span class="sxs-lookup"><span data-stu-id="46414-112">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="46414-113">[Разрешим пользователям Skype для бизнеса добавлять контакты Skype.](let-skype-for-business-users-add-skype-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="46414-113">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="46414-114">Вы можете позволить вашей организации использовать Skype для бизнеса для поиска людей, которые используют бесплатное приложение Skype, и мгновенных разговоров.</span><span class="sxs-lookup"><span data-stu-id="46414-114">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="46414-115">Настройка общих параметров для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="46414-115">Configure general settings for one user</span></span>
<span data-ttu-id="46414-116"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="46414-116"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="46414-117">Для выполнения этих [действий необходимы](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) разрешения администратора.</span><span class="sxs-lookup"><span data-stu-id="46414-117">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="46414-118">![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="46414-118">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="46414-119">Войте свою учетную запись с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="46414-119">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="46414-120">Выберите **Центры администрирования** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="46414-120">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="46414-121">Выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="46414-121">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="46414-123">Выберите пользователей, которых вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="46414-123">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="46414-124">В области справа выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="46414-124">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="46414-126">На странице **"Общие** параметры" в меню "Общие параметры" выберите нужные параметры и выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="46414-126">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="46414-127">**Действие**</span><span class="sxs-lookup"><span data-stu-id="46414-127">**Option**</span></span>|<span data-ttu-id="46414-128">**Details**</span><span class="sxs-lookup"><span data-stu-id="46414-128">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="46414-129">Звук и видео высокой четкости</span><span class="sxs-lookup"><span data-stu-id="46414-129">Audio and HD video</span></span>  <br/> |<span data-ttu-id="46414-130">Разрешить этому человеку записывать аудиособранию, аудио- и видеособранию или не позволять планировать собрания (нет).</span><span class="sxs-lookup"><span data-stu-id="46414-130">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="46414-131">Запись бесед и собраний</span><span class="sxs-lookup"><span data-stu-id="46414-131">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="46414-132">Выберите, что этот человек может записывать.</span><span class="sxs-lookup"><span data-stu-id="46414-132">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="46414-133">Эта возможность недоступна в Skype для бизнеса Basic.</span><span class="sxs-lookup"><span data-stu-id="46414-133">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="46414-134">Чтобы обеспечить соответствие требованиям, отключите неархивные функции</span><span class="sxs-lookup"><span data-stu-id="46414-134">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="46414-135">Выберите этот параметр, если требуется сохранять хранимую в электронном виде информацию в электронном виде.</span><span class="sxs-lookup"><span data-stu-id="46414-135">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="46414-136">При выборе этого параметра отключаются функции, [](/exchange/security-and-compliance/in-place-and-litigation-holds) которые не захватываются при настройках удержания на месте в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="46414-136">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](/exchange/security-and-compliance/in-place-and-litigation-holds) set up in the Exchange admin center.</span></span> <span data-ttu-id="46414-137">При этом отключатся следующие функции:</span><span class="sxs-lookup"><span data-stu-id="46414-137">It turns off the following features:</span></span> <br/>  <span data-ttu-id="46414-138">Передача файлов через службу мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="46414-138">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="46414-139">Общие страницы OneNote</span><span class="sxs-lookup"><span data-stu-id="46414-139">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="46414-140">Примечания PowerPoint</span><span class="sxs-lookup"><span data-stu-id="46414-140">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="46414-141">Чтобы массово настроить эти параметры, используйте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46414-141">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="46414-142">См. ["Настройка компьютера для Windows PowerShell."](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="46414-142">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="46414-143">Блокировка внешней связи</span><span class="sxs-lookup"><span data-stu-id="46414-143">Block external communications</span></span>
<span data-ttu-id="46414-144"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="46414-144"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="46414-145">После того как вы [разрешите](let-skype-for-business-users-add-skype-contacts.md) пользователям Skype для бизнеса добавлять контакты Skype для всех пользователей в вашей организации, вы можете выборочно заблокировать внешнюю связь для определенных пользователей, вы предприняв указанные здесь действия.</span><span class="sxs-lookup"><span data-stu-id="46414-145">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="46414-146">Выберите **"Пользователи",** выберите пользователей, параметры которых вы хотите отключить, и выберите **"Изменить".** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)</span><span class="sxs-lookup"><span data-stu-id="46414-146">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="46414-147">Выберите **"Внешняя связь"** и соответствующие параметры:</span><span class="sxs-lookup"><span data-stu-id="46414-147">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="46414-148">**Внешние пользователи Skype** для бизнеса: если вы не хотите, чтобы пользователь мог общаться с пользователями Skype для бизнеса в федеражных доменах, просто сдружества этого окна.</span><span class="sxs-lookup"><span data-stu-id="46414-148">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="46414-149">**Внешние пользователи Skype:** если вы не хотите, чтобы пользователь мог общаться с пользователями freeSkype.</span><span class="sxs-lookup"><span data-stu-id="46414-149">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="46414-150">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="46414-150">Click **Save**.</span></span>
    
<span data-ttu-id="46414-151">Чтобы массово настроить эти параметры, используйте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46414-151">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="46414-152">См. ["Настройка компьютера для Windows PowerShell."](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="46414-152">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="46414-153">Изменение параметров аудиоконференции для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="46414-153">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="46414-154"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="46414-154"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="46414-155">Выберите **"Пользователи",** выберите пользователя, параметры аудиоконференции для которого нужно изменить, и выберите **"Изменить".** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)</span><span class="sxs-lookup"><span data-stu-id="46414-155">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="46414-156">Выберите **"Аудиоконференция",** выберите поставщика услуг аудиоконференции, введите или измените запрашиваемую информацию, а затем нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="46414-156">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="46414-157">**Настройка аудиоконференции**</span><span class="sxs-lookup"><span data-stu-id="46414-157">**Audio conferencing setting**</span></span>|<span data-ttu-id="46414-158">**Описание**</span><span class="sxs-lookup"><span data-stu-id="46414-158">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="46414-159">**Имя поставщика**</span><span class="sxs-lookup"><span data-stu-id="46414-159">**Provider name**</span></span> <br/> |<span data-ttu-id="46414-160">Выберите поставщика из списка.</span><span class="sxs-lookup"><span data-stu-id="46414-160">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="46414-161">**Платный номер** (обязательно)</span><span class="sxs-lookup"><span data-stu-id="46414-161">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="46414-162">Для сторонних поставщиков услуг аудиоконференций это телефонные номера, полученные от поставщика услуг аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="46414-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="46414-163">Если пользователь выбрал Microsoft в качестве поставщика аудиоконференций, это будут номера, заданные для канала аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="46414-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="46414-164">Отформатирование номеров в том виде, в каком они должны отображаться в запросах на собрания Skype для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="46414-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="46414-165">**Бесплатный номер**</span><span class="sxs-lookup"><span data-stu-id="46414-165">**Toll-free number**</span></span> <br/> |<span data-ttu-id="46414-166">Для сторонних поставщиков услуг аудиоконференций это телефонные номера, полученные от поставщика услуг аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="46414-166">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="46414-167">Если пользователь выбрал Microsoft в качестве поставщика аудиоконференций, это будут номера, заданные для канала аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="46414-167">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="46414-168">Отформатирование номеров в том виде, в каком они должны отображаться в запросах на собрания Skype для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="46414-168">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="46414-169">**Код конференции и ПИН-код** (обязательно)</span><span class="sxs-lookup"><span data-stu-id="46414-169">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="46414-170">ПИН-код участника (или код конференции) используется для присоединиться к собраниям, запланированным этим пользователем, и предоставляется сторонним поставщиком услуг аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="46414-170">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="46414-171">Если в качестве поставщика аудиоконференций используется Майкрософт, это не потребуется.</span><span class="sxs-lookup"><span data-stu-id="46414-171">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="46414-172">Чтобы массово настроить эти параметры, используйте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46414-172">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="46414-173">См. ["Настройка номеров телефонов, включенных в приглашения"](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) ["Настройка компьютера для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46414-173">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="46414-174">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="46414-174">Related topics</span></span> 

[<span data-ttu-id="46414-175">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="46414-175">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="46414-176">Лицензирование надстроек Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46414-176">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
