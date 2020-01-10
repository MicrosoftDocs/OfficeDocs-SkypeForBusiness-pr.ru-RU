---
title: Развертывание одного локального леса для системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: В этом разделе описывается развертывание Системы комнат Skype в локальной среде с одиночным лесом.
ms.openlocfilehash: 091500e1abc1a5e65bb060793aca0d5babe9fb35
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002949"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="0b2e8-103">Развертывание одного локального леса для системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="0b2e8-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="0b2e8-104">В этом разделе описывается развертывание Системы комнат Skype в локальной среде с одиночным лесом.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="0b2e8-105">В этом разделе приводятся общие сведения о том, как подготовить учетную запись системы комнаты Skype на сервере Exchange Server и в Skype для бизнеса Server, размещенных в одном лесе в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="0b2e8-106">Локальные развертывания с одиночным лесом</span><span class="sxs-lookup"><span data-stu-id="0b2e8-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="0b2e8-107">Вы можете использовать учетную запись почтового ящика ресурса для конференц-зала, если она у вас есть.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="0b2e8-108">В противном случае потребуется создать новую учетную запись.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="0b2e8-109">Для создания новой учетной записи почтового ящика ресурса можно использовать либо командную консоль Exchange (PowerShell), либо консоль управления Exchange.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="0b2e8-110">Мы рекомендуем использовать новый почтовый ящик ресурсов (удаление старого почтового ящика и повторного создания) для системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="0b2e8-111">Обязательно выполните резервное копирование данные почтового ящика перед удалением и затем экспортируйте их обратно в повторно созданный почтовый ящик, используя клиент Outlook (дополнительные сведения см. в разделе "Экспорт или резервное копирование сообщений, календаря, задач и контактов").</span><span class="sxs-lookup"><span data-stu-id="0b2e8-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="0b2e8-112">Чтобы восстановить собрания из-за удаления почтового ящика, обратитесь к разделу [подключение или восстановление удаленного почтового ящика](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="0b2e8-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="0b2e8-113">Для использования существующей учетной записи почтового ящика ресурса (например, LRS-01) выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="0b2e8-114">Выполните следующую команду в командной консоли Exchange PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0b2e8-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="0b2e8-115">Если вы планируете создать новый почтовый ящик, выполните следующую команду для локальной организации Exchange с одиночным лесом:</span><span class="sxs-lookup"><span data-stu-id="0b2e8-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="0b2e8-p102">В приведенном выше примере создается активная учетная запись пользователя в Active Directory и почтовый ящик комнаты для конференц-зала в локальной организации Exchange. Параметр RoomMailboxPassword определяет пароль для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-p102">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization. The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="0b2e8-118">Настройте учетную запись для автоматического разрешения конфликтов путем приема/отклонения собраний.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="0b2e8-119">Система комнат Skype — это возможность управлять учетными записями комнаты на Конференции в Exchange, но обратите внимание на то, что до тех пор, пока они не будут принимать приглашение на собрание, оно не будет отображаться в календаре на начальном экране системы помещения Skype.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="0b2e8-120">Полный список доступных команд см. в Set-CalendarProcessing.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="0b2e8-121">Чтобы напомнить собранию организаторов на собрание Skype для бизнеса в Outlook, выполните следующую команду, чтобы настроить подсказку для новой учетной записи:</span><span class="sxs-lookup"><span data-stu-id="0b2e8-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="0b2e8-122">Для настройки локализованных строк используйте следующие команды.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="0b2e8-123">Также можно добавить настраиваемые переводы, если это требуется для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-123">If required by your organization, you can also add custom translations:</span></span> 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="0b2e8-124">Необязательно: Настройка текста для принятия приглашения на собрание, предоставляющего пользователям сведения о комнате собрания Skype для бизнеса, а также о том, что следует ожидать при планировании и присоединении к собраниям.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="0b2e8-125">Проверка учетной записи почтового ящика ресурса в Active Directory</span><span class="sxs-lookup"><span data-stu-id="0b2e8-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="0b2e8-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="0b2e8-127">Система комнаты Skype не может войти в систему или пройти проверку подлинности с помощью Kerberos/NTLM, если учетная запись отключена в службе каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="0b2e8-128">Клиент системы комнаты Skype должен быть в состоянии проверять подлинность с помощью веб-служб Exchange, чтобы получать параметры календаря, а также отправлять сообщения электронной почты с содержимым доски.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="0b2e8-129">Поэтому, если учетная запись отключена, необходимо включить ее в Active Directory, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="0b2e8-130">Для включения входа в учетную запись выполните следующую команду в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="0b2e8-131">При запуске этой команды появится запрос на ввод текущего пароля и на повторный ввод пароля для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="0b2e8-132">После настройки пароля выполните следующую команду, чтобы активировать учетную запись.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="0b2e8-133">Включение системных учетных записей комнаты Skype для Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0b2e8-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="0b2e8-134">В этом разделе приводятся общие сведения о действиях, необходимых для включения Skype для бизнеса для учетной записи комнаты для конференций, которая будет настроена в системе комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="0b2e8-135">После того как вы создадите учетную запись почтового ящика ресурсов для Конференц-зал, используйте командную консоль управления Skype для бизнеса Server для включения системных учетных записей Skype для бизнеса для служб Skype.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b2e8-136">В описанной ниже процедуре предполагается, что вы включили учетную запись системы комнаты Skype в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="0b2e8-137">Выполните следующую команду, чтобы включить учетную запись системы комнаты Skype в пуле сервера Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="0b2e8-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="0b2e8-139">Корпоративная голосовая связь не требуется для системы комнат Skype, но если вы не включите ее для корпоративной голосовой связи, клиент системы комнат Skype не сможет предоставить возможность набора номера для PSTN:</span><span class="sxs-lookup"><span data-stu-id="0b2e8-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="0b2e8-140">Если вы включите корпоративную голосовую почту для учетной записи комнаты на конференц-зале Skype, убедитесь, что вы настроили политику голосовой связи, подходящую для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="0b2e8-141">Если комната для собраний Skype для бизнеса — общедоступный ресурс, любой пользователь может использовать его для присоединения к собранию, как запланированное, так и нерегламентированное.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="0b2e8-142">After joining a meeting, the person could dial out to any number.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="0b2e8-143">В Skype для бизнеса Server функция исходящих звонков из конференций использует политику голосовой связи пользователя, в этом случае учетная запись комнаты для помещения в Skype, которая использовалась для присоединения к собранию.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="0b2e8-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="0b2e8-145">Таким образом, если пользователь более ранней версии Lync Server планирует комнату для собраний и приглашает учетную запись комнаты для помещения в комнату, любой пользователь может использовать для собрания собрание Skype для бизнеса, чтобы присоединиться к собранию и набрать любой национальный, региональный или Международный телефонный номер, если организатор может набрать эти номера.</span><span class="sxs-lookup"><span data-stu-id="0b2e8-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  

