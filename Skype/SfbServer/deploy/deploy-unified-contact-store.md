---
title: 'Развертывание единого магазина контактов в Skype для бизнеса Server '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Сводка: Включите единое хранилище контактов в Skype для бизнеса Server.'
ms.openlocfilehash: 39317316be6c4590e992c61e91549748f3bf6719
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239321"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="99361-103">Развертывание единого магазина контактов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="99361-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="99361-104">**Сводка:** Включите единое хранилище контактов в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="99361-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="99361-105">Для включения единого магазина контактов в Skype для бизнеса Server не требуются параметры топологии.</span><span class="sxs-lookup"><span data-stu-id="99361-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="99361-106">Для предоставления пользователям доступа к единому хранилищу контактов выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="99361-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="99361-107">Включена политика единого магазина контактов (по умолчанию включена).</span><span class="sxs-lookup"><span data-stu-id="99361-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="99361-108">Пользователи входят в Skype для бизнеса по крайней мере один раз.</span><span class="sxs-lookup"><span data-stu-id="99361-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="99361-109">После того как контакты пользователей будут перенесены, что происходит автоматически, когда пользователь входит в систему с помощью Skype для бизнеса, пользователь может получить доступ к контактам Skype для бизнеса и управлять ими в Skype для бизнеса, Outlook 2013 или Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="99361-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="99361-110">Для управления контактами из Outlook или Outlook Web Access пользователю не нужно входить в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="99361-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="99361-111">Если пользователь входит в Skype для бизнеса после миграции, контакты и группы доступны и обновляются, но пользователи не могут управлять ими (то есть добавлять, удалять, перемещать, помечать, присвоенной или изменять) эти контакты.</span><span class="sxs-lookup"><span data-stu-id="99361-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="99361-112">Включение для пользователей единого хранилища контактов</span><span class="sxs-lookup"><span data-stu-id="99361-112">Enable users for unified contact store</span></span>

<span data-ttu-id="99361-113">При развертывании Skype для бизнеса Server и публикации топологии единое хранилище контактов включается для всех пользователей по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="99361-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="99361-114">Вам не нужно предпринимать никаких дополнительных действий, чтобы активировать единое хранилище контактов после развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="99361-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="99361-115">Однако вы можете использовать командлет **Set-ксусерсервицесполици** , чтобы настроить, какие пользователи будут доступны в едином хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="99361-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="99361-116">Вы можете включить эту функцию глобально, по сайту, по клиенту или по отдельным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="99361-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="99361-117">Включение пользователей в едином хранилище контактов</span><span class="sxs-lookup"><span data-stu-id="99361-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="99361-118">Запустите консоль управления в Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Skype**для бизнеса и щелкните **Командная консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="99361-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="99361-119">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="99361-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="99361-120">Чтобы включить единое хранилище контактов глобально для всех пользователей Skype для бизнеса Server, в командной строке Windows PowerShell можно использовать следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="99361-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="99361-121">Чтобы включить единое хранилище контактов для пользователей на определенном сайте, введите в командной строке:</span><span class="sxs-lookup"><span data-stu-id="99361-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="99361-122">Например:</span><span class="sxs-lookup"><span data-stu-id="99361-122">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="99361-123">Чтобы включить единое хранилище контактов по клиенту, в командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="99361-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="99361-124">Например:</span><span class="sxs-lookup"><span data-stu-id="99361-124">For example:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="99361-125">Чтобы включить единое хранилище контактов для определенных пользователей, в командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="99361-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="99361-126">Вы также можете использовать псевдонимы пользователя или URI SIP вместо отображаемого имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="99361-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="99361-127">Например:</span><span class="sxs-lookup"><span data-stu-id="99361-127">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="99361-128">В предыдущем примере первая команда создает новую политику для пользователей с включенным управлением UCS, при этом для флага Уксалловед задано значение true.</span><span class="sxs-lookup"><span data-stu-id="99361-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="99361-129">Вторая команда назначает пользователю политику с отображаемым именем Кен мер, что означает, что Кен мер теперь включен для единого магазина контактов.</span><span class="sxs-lookup"><span data-stu-id="99361-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="99361-130">Перенос пользователей в единое хранилище контактов</span><span class="sxs-lookup"><span data-stu-id="99361-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="99361-131">Пользовательские контакты автоматически переносятся на сервер Exchange 2013, когда пользователь:</span><span class="sxs-lookup"><span data-stu-id="99361-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="99361-132">Назначена политика пользовательских служб, у которой Уксалловед установлено значение true.</span><span class="sxs-lookup"><span data-stu-id="99361-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="99361-133">Была настроена с помощью почтового ящика Exchange 2013 и один раз вошел в почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="99361-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="99361-134">Войдите в систему с помощью многофункционального клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="99361-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="99361-135">Если пользователь входит в систему с помощью Lync или более ранней версии клиента или если пользователь не подключен к серверу Exchange 2013, политика служб пользователей игнорируется, а контакты пользователя остаются в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="99361-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="99361-136">Чтобы определить, перенесены ли контакты пользователя, используйте один из указанных ниже способов.</span><span class="sxs-lookup"><span data-stu-id="99361-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="99361-137">На клиентском компьютере проверьте следующий раздел реестра:</span><span class="sxs-lookup"><span data-stu-id="99361-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="99361-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<URL-\>адрес SIP \укс</span><span class="sxs-lookup"><span data-stu-id="99361-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="99361-139">Если контакты пользователя хранятся в Exchange 2013, в этом разделе содержится значение Инуксмоде со значением 2165.</span><span class="sxs-lookup"><span data-stu-id="99361-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="99361-140">Запустите командлет **Test-ксунифиедконтактсторе** .</span><span class="sxs-lookup"><span data-stu-id="99361-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="99361-141">В командной строке Skype для Business Server Management Shell введите:</span><span class="sxs-lookup"><span data-stu-id="99361-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="99361-142">Если **тест-ксунифиедконтактсторе** выполняется успешно, контакты пользователя были перенесены в единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="99361-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="99361-143">Откат пользователей, для которых выполнена миграция</span><span class="sxs-lookup"><span data-stu-id="99361-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="99361-144">Если вы хотите выполнить откат в едином хранилище контактов, изменяйте контакты только в том случае, если вы вернете пользователя на Exchange 2010 или Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="99361-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="99361-145">Чтобы выполнить откат, отключите политику для пользователя, а затем выполните командлет **Invoke-ксуксроллбакк** .</span><span class="sxs-lookup"><span data-stu-id="99361-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="99361-146">Просто запустить функцию **Invoke-ксуксроллбакк** недостаточно для обеспечения постоянной процедуры отката, так как единая миграция хранилища контактов инициируется повторно, если она не отключена.</span><span class="sxs-lookup"><span data-stu-id="99361-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="99361-147">Например, если пользователь выполняет откат, так как Exchange 2013 возвращается в Exchange 2010, а почтовый ящик пользователя перемещается в Exchange 2013, то единая миграция в магазине контактов начнется еще раз через семь дней после отката, пока единая база данных контактов по-прежнему включен для пользователя в политике служб пользователей.</span><span class="sxs-lookup"><span data-stu-id="99361-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="99361-148">Командлет **Move-CsUser** автоматически откатывает хранилище контактов пользователя Exchange 2013 на сервер Skype для бизнеса Server в указанных ниже случаях.</span><span class="sxs-lookup"><span data-stu-id="99361-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="99361-149">При перемещении пользователей из Skype для бизнеса на сервер Microsoft Lync Server 2013 или Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="99361-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="99361-150">Миграция локальных пользователей, например при перемещении пользователя из Skype для бизнеса Online в локальную версию Skype для бизнеса Server или наоборот.</span><span class="sxs-lookup"><span data-stu-id="99361-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="99361-151">Импорт данных из хранилища Объединенных контактов из резервной базы данных может привести к повреждению данных из хранилища контактов и данных пользователя, если в процессе экспорта и импорта изменился режим хранилища единого контакта.</span><span class="sxs-lookup"><span data-stu-id="99361-151">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import.</span></span> <span data-ttu-id="99361-152">Например:</span><span class="sxs-lookup"><span data-stu-id="99361-152">For example:</span></span>
  
- <span data-ttu-id="99361-153">Если вы экспортируете списки контактов перед тем, как контакты пользователей будут перенесены в Exchange 2013, а затем, после миграции, импортируйте эти данные в единое хранилище контактов и списки контактов, которые будут повреждены.</span><span class="sxs-lookup"><span data-stu-id="99361-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="99361-154">Если вы экспортируете данные пользователя после миграции пользователей в Exchange 2013, откати миграции и, по некоторым причинам, вы импортируете данные из системы после миграции, они будут повреждены.</span><span class="sxs-lookup"><span data-stu-id="99361-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="99361-155">Перед перемещением почтового ящика Exchange из Exchange 2013 в Exchange 2010 администратор Exchange должен предварительно вернуть контакты пользователей Skype для бизнеса Server из Exchange 2013 в Skype для Business Server.</span><span class="sxs-lookup"><span data-stu-id="99361-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="99361-156">Чтобы вернуть контакты из магазина Объединенных контактов в Skype для бизнеса Server, ознакомьтесь с разделом "как вернуть контакты из Exchange 2013 в Skype для бизнеса Server" Далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="99361-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="99361-157">**Как восстановить контакты пользователей:** Если для перемещения пользователей между Skype для бизнеса Server 2015 и Lync Server 2010 используется командлет **Move-CsUser** , вы можете пропустить эти действия, так как командлет **Move-CsUser** автоматически откатывает единое хранилище контактов при перемещении пользователей из Skype Бизнес-сервер 2015 на Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="99361-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="99361-158">В разделе **Move-CsUser** не отключена политика хранилища контактов, поэтому миграция в единое хранилище контактов будет повторена, если пользователь перейдет обратно в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="99361-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

