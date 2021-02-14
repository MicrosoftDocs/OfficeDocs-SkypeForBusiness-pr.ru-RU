---
title: Локальное развертывание системы комнат Skype с одним лесом
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: В этом разделе вы узнаете, как развернуть систему комнат Skype в локальной среде с одним лесом.
ms.openlocfilehash: 0449a5e909fa044df12766aec0a036bf97315386
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820759"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="81295-103">Локальное развертывание системы комнат Skype с одним лесом</span><span class="sxs-lookup"><span data-stu-id="81295-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="81295-104">В этом разделе вы узнаете, как развернуть систему комнат Skype в локальной среде с одним лесом.</span><span class="sxs-lookup"><span data-stu-id="81295-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="81295-105">В этом разделе представлен обзор действий по обеспечению учетной записи системы комнат Skype в локальном развертывании Exchange Server и Skype для бизнеса Server, размещенной в локальном развертывании с одним лесом.</span><span class="sxs-lookup"><span data-stu-id="81295-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="81295-106">Локальные развертывания с одним лесом</span><span class="sxs-lookup"><span data-stu-id="81295-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="81295-107">Если у вас уже есть учетная запись почтового ящика ресурса для комнаты, вы можете использовать ее.</span><span class="sxs-lookup"><span data-stu-id="81295-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="81295-108">В противном случае потребуется создать новый.</span><span class="sxs-lookup"><span data-stu-id="81295-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="81295-109">Для создания новой учетной записи почтового ящика ресурса можно использовать либо оболочку управления Exchange (PowerShell), либо консоль управления Exchange.</span><span class="sxs-lookup"><span data-stu-id="81295-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="81295-110">Мы рекомендуем использовать новый (удалить старый почтовый ящик и повторно создать) почтовый ящик ресурса для системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="81295-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="81295-111">Перед удалением убедитесь в том, что необходимо создать их базу данных почтового ящика, а затем экспортировать их обратно в повторно созданный почтовый ящик с помощью клиента Outlook (дополнительные сведения см. в этой теме.</span><span class="sxs-lookup"><span data-stu-id="81295-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="81295-112">Чтобы восстановить собрания, потерянные при удалении почтового ящика, см. в подключении или [восстановлении удаленного почтового ящика.](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="81295-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="81295-113">Чтобы использовать существующую учетную запись почтового ящика ресурса (например, LRS-01), выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="81295-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="81295-114">Запустите следующую команду Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="81295-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="81295-115">Если вы планируете создать почтовый ящик, для локальной организации Exchange с одним лесом запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="81295-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="81295-116">В примере выше создается включенная учетная запись пользователя в Active Directory и почтовый ящик помещения для конференц-зала в локальной организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="81295-116">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization.</span></span> <span data-ttu-id="81295-117">Параметр RoomMailboxPassword указывает пароль для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="81295-117">The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="81295-118">Настройте учетную запись для автоматического разрешения конфликтов, принимая или отклоняет собрания.</span><span class="sxs-lookup"><span data-stu-id="81295-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="81295-119">Учетными записями конференц-залов, оснащенными системой комнат Skype, в Exchange могут управлять отдельные пользователи, но обратите внимание, что до тех пор, пока отдельный человек не примет собрание, оно не будет отображаться в календаре домашнего экрана системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="81295-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="81295-120">Полный набор доступных команд см. в командной части Set-CalendarProcessing.</span><span class="sxs-lookup"><span data-stu-id="81295-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="81295-121">Чтобы напомнить организаторам собрания, что собрание необходимо сделать собранием Skype для бизнеса по сети в Outlook, запустите следующую команду, чтобы настроить mailTip для новой учетной записи:</span><span class="sxs-lookup"><span data-stu-id="81295-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="81295-122">Используйте следующие команды для настройки локализованных строк.</span><span class="sxs-lookup"><span data-stu-id="81295-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="81295-123">При необходимости в организации можно также добавить настраиваемые переводы:</span><span class="sxs-lookup"><span data-stu-id="81295-123">If required by your organization, you can also add custom translations:</span></span> 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="81295-124">Необязательно: настройте текст приемки собрания, который предоставляет пользователям сведения о комнате для собраний Skype для бизнеса и о том, что следует ожидать при их расписании и подмыве собрания.</span><span class="sxs-lookup"><span data-stu-id="81295-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="81295-125">Проверка учетной записи почтового ящика ресурса в Active Directory</span><span class="sxs-lookup"><span data-stu-id="81295-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="81295-126">Учетная запись почтового ящика конференц-зала, созданная Exchange на шаге 1 выше, может быть отключенным объектом пользователя в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="81295-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="81295-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="81295-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="81295-128">Клиент системы комнат Skype должен иметь возможность проверки подлинности в веб-службах Exchange для получения параметров календаря, а также отправлять электронную почту с содержимым доски.</span><span class="sxs-lookup"><span data-stu-id="81295-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="81295-129">Таким образом, если учетная запись отключена, необходимо включить эту учетную запись в Active Directory, выступая следующим образом:</span><span class="sxs-lookup"><span data-stu-id="81295-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="81295-130">В Active Directory запустите следующую команду, чтобы включить вход в учетную запись:</span><span class="sxs-lookup"><span data-stu-id="81295-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="81295-131">При запуске этой команды вам будет предложено ввести текущий пароль, а затем повторно ввести пароль дважды для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="81295-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="81295-132">После этого запустите следующую команду, чтобы включить учетную запись:</span><span class="sxs-lookup"><span data-stu-id="81295-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="81295-133">Включение учетных записей системы комнат Skype для Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="81295-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="81295-134">В этом разделе представлен обзор действий, необходимых для того, чтобы включить Skype для бизнеса для учетной записи конференц-зала, которая будет настроена в системе комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="81295-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="81295-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span><span class="sxs-lookup"><span data-stu-id="81295-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="81295-136">В следующей процедуре предполагается, что вы включили учетную запись системы комнат Skype в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="81295-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="81295-137">Чтобы включить учетную запись системы комнат Skype в пуле Skype для бизнеса Server, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="81295-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="81295-138">Необязательный. Разрешить этой учетной записи делать и принимать телефонные вызовы PSTN, включив учетную запись для Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="81295-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="81295-139">Корпоративная голосовая связь не требуется для системы комнат Skype, но если не включить ее для Корпоративная голосовая связь, клиент системы комнат Skype не сможет предоставить функции набора номера ЗВОНКОВ:</span><span class="sxs-lookup"><span data-stu-id="81295-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="81295-140">If you enable Корпоративная голосовая связь for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span><span class="sxs-lookup"><span data-stu-id="81295-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="81295-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span><span class="sxs-lookup"><span data-stu-id="81295-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="81295-142">После присоединения к собранию человек может звонить на любой номер.</span><span class="sxs-lookup"><span data-stu-id="81295-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="81295-143">В Skype для бизнеса Server функция набора номера из конференций использует политику голосовой связи пользователя, в данном случае это учетная запись системы комнат Skype, используемая для присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="81295-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="81295-144">В более ранних версиях Lync Server используется политика голосовой почты организатора.</span><span class="sxs-lookup"><span data-stu-id="81295-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="81295-145">Таким образом, если пользователь более ранней версии Lync Server запланировать комнату для собраний и пригласить учетную запись системы комнат Skype, любой пользователь может присоединиться к собранию с помощью комнаты для собраний Skype для бизнеса и набрать любой номер телефона для национальных, региональных или международных звонков, если организатору разрешено набирать эти номера.</span><span class="sxs-lookup"><span data-stu-id="81295-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  

