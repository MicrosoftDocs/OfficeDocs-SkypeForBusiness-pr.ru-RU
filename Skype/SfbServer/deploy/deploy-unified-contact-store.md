---
title: 'Развертывание единого хранения контактов в Skype для бизнеса Server '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: Сводка. В этой теме включается единое хранилище контактов в Skype для бизнеса Server.
ms.openlocfilehash: 7bf4dcb884dc9fecee15209f5acb563fce9efd43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812559"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="6f205-103">Развертывание единого хранения контактов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f205-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="6f205-104">**Сводка:** В включить единое хранилище контактов в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6f205-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="6f205-105">Для включения единого хранения контактов в Skype для бизнеса Server не требуются параметры топологии.</span><span class="sxs-lookup"><span data-stu-id="6f205-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="6f205-106">Чтобы включить единое хранилище контактов для пользователей:</span><span class="sxs-lookup"><span data-stu-id="6f205-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="6f205-107">Политика единого хранилища контактов включена (по умолчанию — включена).</span><span class="sxs-lookup"><span data-stu-id="6f205-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="6f205-108">Пользователи хотя бы один раз войдите в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="6f205-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="6f205-109">После переноса контактов пользователя, что происходит автоматически при входе пользователя в Skype для бизнеса, пользователь может получать доступ к своим контактам Skype для бизнеса, Outlook 2013 или Outlook Web Access и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="6f205-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="6f205-110">Пользователю не нужно вошел в Skype для бизнеса, чтобы управлять своими контактами из Outlook или Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="6f205-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6f205-111">Если пользователь входит в Skype для бизнеса после миграции, контакты и группы доступны и находятся в курсе, но пользователь не может управлять этими контактами (т. е. добавлять, удалять, перемещать, помечать, оттегировать или изменять) этими контактами.</span><span class="sxs-lookup"><span data-stu-id="6f205-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="6f205-112">Включить для пользователей единое хранилище контактов</span><span class="sxs-lookup"><span data-stu-id="6f205-112">Enable users for unified contact store</span></span>

<span data-ttu-id="6f205-113">При развертывании Skype для бизнеса Server и публикации топологии единое хранилище контактов включено для всех пользователей по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6f205-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="6f205-114">Вам не нужно никаких дополнительных действий, чтобы включить единое хранилище контактов после развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6f205-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="6f205-115">Однако можно использовать командлет **Set-CsUserServicesPolicy**, чтобы указать, каким пользователям доступно единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="6f205-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="6f205-116">Эту возможность можно включать глобально, по узлам, по клиентам, по отдельности или группами.</span><span class="sxs-lookup"><span data-stu-id="6f205-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="6f205-117">Включение для пользователей единого хранилища контактов</span><span class="sxs-lookup"><span data-stu-id="6f205-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="6f205-118">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", **"Skype** для бизнеса" и "Skype для бизнеса **Server Management Shell".** </span><span class="sxs-lookup"><span data-stu-id="6f205-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6f205-119">Выполните любые из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="6f205-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="6f205-120">Чтобы включить глобальное единое хранилище контактов для всех пользователей Skype для бизнеса Server, в командной строке Windows PowerShell следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="6f205-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="6f205-121">Чтобы включить единое хранилище контактов для пользователей на определенном сайте, введите в запросе:</span><span class="sxs-lookup"><span data-stu-id="6f205-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="6f205-122">Пример:</span><span class="sxs-lookup"><span data-stu-id="6f205-122">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="6f205-123">Чтобы включить единое хранилище контактов по арендатору, введите:</span><span class="sxs-lookup"><span data-stu-id="6f205-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="6f205-124">Пример:</span><span class="sxs-lookup"><span data-stu-id="6f205-124">For example:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="6f205-125">Чтобы включить единое хранилище контактов для определенных пользователей, введите:</span><span class="sxs-lookup"><span data-stu-id="6f205-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="6f205-126">Вместо отображаемых имен пользователей можно использовать псевдонимы или SIP URI.</span><span class="sxs-lookup"><span data-stu-id="6f205-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="6f205-127">Например:</span><span class="sxs-lookup"><span data-stu-id="6f205-127">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="6f205-128">В предыдущем примере первая команда создает новую политику на уровне пользователя с именем UCS Enabled Users и с флагом UcsAllowed, установленным в значение True.</span><span class="sxs-lookup"><span data-stu-id="6f205-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="6f205-129">Вторая команда назначает эту политику пользователю с отображаемым именем Ken Myer, что означает, что теперь Кену Майеру разрешен доступ к единому хранилищу контактов.</span><span class="sxs-lookup"><span data-stu-id="6f205-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="6f205-130">Перенос пользователей в единое хранилище контактов</span><span class="sxs-lookup"><span data-stu-id="6f205-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="6f205-131">Контакты пользователя автоматически переносятся на сервер Exchange 2013 в следующих условиях.</span><span class="sxs-lookup"><span data-stu-id="6f205-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="6f205-132">пользователю назначена политика служб пользователя, где для параметра UcsAllowed установлено значение true;</span><span class="sxs-lookup"><span data-stu-id="6f205-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="6f205-133">Он был предусмотрен с помощью почтового ящика Exchange 2013 и хотя бы один раз вошел в почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="6f205-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="6f205-134">Пользователь входит в систему с помощью клиента Skype для бизнеса с расширенными возможностями.</span><span class="sxs-lookup"><span data-stu-id="6f205-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="6f205-135">Если пользователь входит в систему с помощью Lync или более ранних клиентов или пользователь не подключен к серверу Exchange 2013, политика служб пользователей игнорируется, а контакты пользователя остаются в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6f205-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="6f205-136">Можно определить, перенесены ли контакты пользователя, с помощью любого из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="6f205-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="6f205-137">Проверьте следующий раздел реестра на клиентском компьютере:</span><span class="sxs-lookup"><span data-stu-id="6f205-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="6f205-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync<\\ SIP URL \> \UCS</span><span class="sxs-lookup"><span data-stu-id="6f205-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="6f205-139">Если контакты пользователя хранятся в Exchange 2013, этот ключ содержит значение InUCSMode со значением 2165.</span><span class="sxs-lookup"><span data-stu-id="6f205-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="6f205-140">Выполните командлет **Test-CsUnifiedContactStore**.</span><span class="sxs-lookup"><span data-stu-id="6f205-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="6f205-141">В командной строке командной строки Skype для бизнеса Server введите:</span><span class="sxs-lookup"><span data-stu-id="6f205-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="6f205-142">Если командлет **Test-CsUnifiedContactStore** выполнен успешно, следовательно, выполнен перенос контактов пользователя к единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="6f205-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="6f205-143">Откат перенесенных пользователей</span><span class="sxs-lookup"><span data-stu-id="6f205-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="6f205-144">Если необходимо откатить функцию единого хранения контактов, откат контактов следует только в том случае, если вы переместили пользователя обратно в Exchange 2010 или Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6f205-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="6f205-145">Для выполнении отката отключите политику для пользователя, а затем выполните командлет **Invoke-CsUcsRollback**.</span><span class="sxs-lookup"><span data-stu-id="6f205-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="6f205-146">Выполнения одного командлета **Invoke-CsUcsRollback** недостаточно для обеспечения постоянного отката, поскольку если политика не отключена, то миграция универсального хранилища контактов будет инициирована повторно.</span><span class="sxs-lookup"><span data-stu-id="6f205-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="6f205-147">Например, если пользователь откатился из-за отката Exchange 2013 в Exchange 2010, а затем почтовый ящик пользователя перемещен в Exchange 2013, миграция единого магазина контактов будет инициироваться снова через семь дней после отката, если единое хранилище контактов по-прежнему включено для пользователя в политике служб пользователей.</span><span class="sxs-lookup"><span data-stu-id="6f205-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="6f205-148">В следующих ситуациях с помощью cmdlet **Move-CsUser** автоматически откатируется хранилище контактов пользователя из Exchange 2013 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6f205-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="6f205-149">При перемещении пользователей из Skype для бизнеса Server в Microsoft Lync Server 2013 или Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6f205-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="6f205-150">При миграции пользователей в локальной сети, например при перемещении пользователя из Skype для бизнеса Online в локальное приложение Skype для бизнеса Server или наоборот.</span><span class="sxs-lookup"><span data-stu-id="6f205-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="6f205-p107">Импорт данных универсального хранилища контактов из резервной копии базы данных может привести к повреждению данных универсального хранилища контактов и пользовательских данных, если режим универсального хранилища контактов изменится с экспорта на импорт. Пример:</span><span class="sxs-lookup"><span data-stu-id="6f205-p107">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span>
  
- <span data-ttu-id="6f205-153">Если экспортировать списки контактов до переноса контактов пользователей в Exchange 2013, а затем после миграции импортировать те же данные, данные единого хранения контактов и списки контактов будут повреждены.</span><span class="sxs-lookup"><span data-stu-id="6f205-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="6f205-154">Если экспортировать данные пользователей после миграции пользователей в Exchange 2013, откатить миграцию, а затем по какой-либо причине импортировать данные после миграции, данные единого хранения контактов и списки контактов будут повреждены.</span><span class="sxs-lookup"><span data-stu-id="6f205-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="6f205-155">Перед перемещением почтового ящика Exchange из Exchange 2013 в Exchange 2010 администратор Exchange должен убедиться, что администратор Skype для бизнеса Server сначала откатил контакты пользователей Skype для бизнеса Server из Exchange 2013 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6f205-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="6f205-156">Чтобы откатить контакты единого хранения контактов в Skype для бизнеса Server, см. процедуру "Откат контактов единого магазина контактов из Exchange 2013 в Skype для бизнеса Server" далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="6f205-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="6f205-157">**Откат контактов пользователей:** Если для перемещения пользователей между Skype для бизнеса Server 2015 и Lync Server 2010 используется cmdlet **Move-CsUser,** эти действия можно пропустить, так как при перемещениях пользователей из Skype для бизнеса Server 2015 в Lync Server 2010 он автоматически откатит единое хранилище контактов. </span><span class="sxs-lookup"><span data-stu-id="6f205-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="6f205-158">**Move-CsUser** не отключит единую политику хранения контактов, поэтому при перемещении пользователя обратно в Skype для бизнеса Server 2015 миграция в единое хранилище контактов будет повторна.</span><span class="sxs-lookup"><span data-stu-id="6f205-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

