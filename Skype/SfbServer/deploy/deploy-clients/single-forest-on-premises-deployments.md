---
title: Развертывание единого леса в системе номеров Skype
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
description: Ознакомьтесь с этой темой, чтобы узнать, как развернуть систему Skype Room System в одной локальной среде леса.
ms.openlocfilehash: df213b24ef3400aa5551a090d2dd218d05794988
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120328"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="cce5c-103">Развертывание единого леса в системе номеров Skype</span><span class="sxs-lookup"><span data-stu-id="cce5c-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="cce5c-104">Ознакомьтесь с этой темой, чтобы узнать, как развернуть систему Skype Room System в одной локальной среде леса.</span><span class="sxs-lookup"><span data-stu-id="cce5c-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="cce5c-105">В этом разделе представлен обзор действий по обеспечению учетной записи Skype Room System на Exchange Server и Skype для бизнеса Server, размещенной в одном локальном развертывании леса.</span><span class="sxs-lookup"><span data-stu-id="cce5c-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="cce5c-106">Локальные развертывания с одним лесом</span><span class="sxs-lookup"><span data-stu-id="cce5c-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="cce5c-107">Если у вас уже есть учетная запись почтового ящика ресурса для комнаты для конференций, ее можно использовать.</span><span class="sxs-lookup"><span data-stu-id="cce5c-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="cce5c-108">В противном случае потребуется создать новый.</span><span class="sxs-lookup"><span data-stu-id="cce5c-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="cce5c-109">Для создания новой учетной записи почтового ящика ресурсов можно использовать как оболочку управления Exchange (PowerShell), так и консоль управления Exchange.</span><span class="sxs-lookup"><span data-stu-id="cce5c-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="cce5c-110">Рекомендуется использовать новый (удалить старый почтовый ящик и повторно создать) почтовый ящик ресурса для Системы номеров Skype.</span><span class="sxs-lookup"><span data-stu-id="cce5c-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="cce5c-111">Убедитесь, что перед удалением необходимо создать базу данных почтовых ящиков, а затем экспортировать их обратно в вновь созданный почтовый ящик с помощью клиента Outlook (дополнительные сведения см. в экспорте или обратном сборе сообщений, календаря, задач и контактов).</span><span class="sxs-lookup"><span data-stu-id="cce5c-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="cce5c-112">Чтобы восстановить собрания, потерянные путем удаления почтового ящика, см. в руб. Подключение или восстановление [удаленного почтового ящика.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="cce5c-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help).</span></span> 
  
<span data-ttu-id="cce5c-113">Чтобы использовать существующую учетную запись почтового ящика ресурсов (например, LRS-01), выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="cce5c-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="cce5c-114">Запустите следующую команду PowerShell управления Exchange:</span><span class="sxs-lookup"><span data-stu-id="cce5c-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="cce5c-115">Если вы планируете создать новый почтовый ящик, то для одной лесной локальной организации Exchange запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cce5c-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="cce5c-116">В этом примере создается учетная запись пользователя с включенной поддержкой в Active Directory и почтовый ящик комнаты для конференц-зала в локальной организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="cce5c-116">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization.</span></span> <span data-ttu-id="cce5c-117">Параметр RoomMailboxPassword указывает пароль для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="cce5c-117">The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="cce5c-118">Настройте учетную запись для автоматического разрешения конфликтов, принимая собрания или отклоняет их.</span><span class="sxs-lookup"><span data-stu-id="cce5c-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="cce5c-119">Учетные записи конференц-залов в Exchange, оборудованные системой Skype, могут управляться отдельными лицами, но обратите внимание, что до тех пор, пока человек не примет собрание, оно не будет отображаться в календаре домашнего экрана системы номеров Skype.</span><span class="sxs-lookup"><span data-stu-id="cce5c-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="cce5c-120">Полный набор доступных команд см. в пункте Set-CalendarProcessing.</span><span class="sxs-lookup"><span data-stu-id="cce5c-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="cce5c-121">Чтобы напомнить организаторам собрания о том, как сделать собрание Skype для бизнеса в Outlook, запустите следующую команду, чтобы настроить MailTip для новой учетной записи:</span><span class="sxs-lookup"><span data-stu-id="cce5c-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="cce5c-122">Чтобы настроить локализованные строки, используйте следующие команды.</span><span class="sxs-lookup"><span data-stu-id="cce5c-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="cce5c-123">Если требуется ваша организация, вы также можете добавить настраиваемые переводы:</span><span class="sxs-lookup"><span data-stu-id="cce5c-123">If required by your organization, you can also add custom translations:</span></span> 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="cce5c-124">Необязательный. Настройте текст приемки собраний, который предоставляет пользователям сведения о Комнате собраний Skype для бизнеса и о том, что следует ожидать при расписании собраний и вступать в них.</span><span class="sxs-lookup"><span data-stu-id="cce5c-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="cce5c-125">Проверка учетной записи почтовых ящиков ресурса в Active Directory</span><span class="sxs-lookup"><span data-stu-id="cce5c-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="cce5c-126">Учетная запись почтового ящика конференц-зала, созданная Exchange на шаге 1 выше, может быть отключенным объектом пользователя в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cce5c-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="cce5c-127">Система номеров Skype не может войти или проверить подлинность с помощью проверки подлинности Kerberos/NTLM, если учетная запись отключена в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cce5c-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="cce5c-128">Клиент системы номеров Skype должен иметь возможность проверки подлинности в веб-службах Exchange для получения параметров календаря, а также отправлять сообщения электронной почты с содержимым доски.</span><span class="sxs-lookup"><span data-stu-id="cce5c-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="cce5c-129">Поэтому, если учетная запись отключена, необходимо включить эту учетную запись в Active Directory, делая следующее:</span><span class="sxs-lookup"><span data-stu-id="cce5c-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="cce5c-130">В Active Directory запустите следующую команду, чтобы включить журнал учетной записи:</span><span class="sxs-lookup"><span data-stu-id="cce5c-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="cce5c-131">Запуск этой команды позволит ввести текущий пароль, а затем дважды ввести пароль для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="cce5c-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="cce5c-132">После зачета пароля запустите следующую команду, чтобы включить учетную запись:</span><span class="sxs-lookup"><span data-stu-id="cce5c-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="cce5c-133">Включение учетных записей skype Room System для Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cce5c-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="cce5c-134">В этом разделе представлен обзор действий, необходимых для того, чтобы включить Skype для бизнеса для вашей учетной записи конференц-зала, которая будет настроена в skype Room System.</span><span class="sxs-lookup"><span data-stu-id="cce5c-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="cce5c-135">После создания учетной записи почтового ящика ресурсов для помещений для конференций используйте Skype для управления бизнес-серверами, чтобы включить учетные записи skype Room System для служб Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="cce5c-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cce5c-136">В следующей процедуре предполагается, что вы включили учетную запись Skype Room System в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cce5c-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="cce5c-137">Запустите следующую команду, чтобы включить учетную запись Skype Room System в пуле Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="cce5c-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="cce5c-138">Необязательный. Разрешить этой учетной записи делать и принимать телефонные вызовы PSTN, включив учетную запись для Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="cce5c-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="cce5c-139">Корпоративная голосовая связь не требуется для системы номеров Skype, но если вы не включаете ее для Корпоративная голосовая связь, клиент skype Room System не сможет предоставить функции набора номера PSTN:</span><span class="sxs-lookup"><span data-stu-id="cce5c-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="cce5c-140">Если вы Корпоративная голосовая связь для учетной записи конференц-зала Skype Room System, настройте ограниченную голосовую политику, которая подходит для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="cce5c-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="cce5c-141">Если комната собраний Skype для бизнеса является общедоступным ресурсом, любой желающий может присоединиться к собранию, запланированному или разово.</span><span class="sxs-lookup"><span data-stu-id="cce5c-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="cce5c-142">После присоединения к собранию человек может набрать любой номер.</span><span class="sxs-lookup"><span data-stu-id="cce5c-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="cce5c-143">В Skype для бизнеса Server функция конференц-связи использует голосовую политику пользователя, в данном случае учетную запись Skype Room System, используемую для данной встречи.</span><span class="sxs-lookup"><span data-stu-id="cce5c-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="cce5c-144">В более ранних версиях Lync Server используется голосовая политика организатора.</span><span class="sxs-lookup"><span data-stu-id="cce5c-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="cce5c-145">Поэтому если пользователь более ранней версии Lync Server настроит зал собраний и пригласит учетную запись skype Room System, любой пользователь может присоединиться к собранию в Комнате собраний Skype для бизнеса и набрать любой национальный или региональный или международный телефонный номер, если организатору разрешено набирать эти номера.</span><span class="sxs-lookup"><span data-stu-id="cce5c-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
