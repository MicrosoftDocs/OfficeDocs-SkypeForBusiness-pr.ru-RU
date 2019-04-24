---
title: 'Развертывание единого хранилища контактов в Скайп для Business Server '
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Сводка: Включите единое хранилище контактов в Скайп для Business Server.'
ms.openlocfilehash: 5e7fb34d03459be5066d154e89fa8e27dc060757
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219624"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="3426e-103">Развертывание единого хранилища контактов в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="3426e-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="3426e-104">**Сводка:** Включите единое хранилище контактов в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="3426e-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="3426e-105">Включение единого хранилища контактов в Скайп для Business Server не требуются все параметры топологии.</span><span class="sxs-lookup"><span data-stu-id="3426e-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="3426e-106">Для предоставления пользователям доступа к единому хранилищу контактов выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="3426e-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="3426e-107">Политика единого хранилища контактов включена (по умолчанию включен).</span><span class="sxs-lookup"><span data-stu-id="3426e-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="3426e-108">Пользователи выполняют вход Скайп для бизнеса по крайней мере один раз.</span><span class="sxs-lookup"><span data-stu-id="3426e-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="3426e-109">После контакты пользователя были перенесены, которые происходит автоматически при входе пользователя в систему с Скайп для бизнеса, пользователь может получить доступ к и управлять их Скайп для бизнес-контакты из Скайп для предприятий, Outlook 2013 и Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="3426e-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="3426e-110">Пользователь не нужно выполнить вход Скайп для бизнеса для управления свои контакты из Outlook или Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="3426e-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3426e-111">Если пользователь входит в систему Скайп для бизнеса после миграции, контакты и группы, доступные и постоянно обновляемой, но пользователь не может управлять (, который является, добавление, удаление, перемещение, тега, Отмена или изменение) определенных контактов.</span><span class="sxs-lookup"><span data-stu-id="3426e-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="3426e-112">Включение для пользователей единого хранилища контактов</span><span class="sxs-lookup"><span data-stu-id="3426e-112">Enable users for unified contact store</span></span>

<span data-ttu-id="3426e-113">При развертывании Скайп для Business Server и публикации топологии, единое хранилище контактов включен по умолчанию для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="3426e-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="3426e-114">Не требуется предпринимать никаких дополнительных действий, чтобы включить единое хранилище контактов, после развертывания Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="3426e-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="3426e-115">Тем не менее можно использовать командлет **Set-CsUserServicesPolicy** для настройки пользователей, которые единого хранилища контактов.</span><span class="sxs-lookup"><span data-stu-id="3426e-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="3426e-116">Для включения этой функции глобально, с сайта, по клиентам или отдельных пользователей или групп пользователей.</span><span class="sxs-lookup"><span data-stu-id="3426e-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="3426e-117">Включение для пользователей единое хранилище контактов</span><span class="sxs-lookup"><span data-stu-id="3426e-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="3426e-118">Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для бизнеса**и нажмите кнопку **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="3426e-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="3426e-119">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="3426e-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="3426e-120">Чтобы включить единое хранилище контактов глобально для всех Скайп для пользователей Business Server, взаимодействия между каналами следующий командлет в командной строки Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3426e-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="3426e-121">Чтобы включить единое хранилище контактов для пользователей на конкретном сайте, в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3426e-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="3426e-122">Например:</span><span class="sxs-lookup"><span data-stu-id="3426e-122">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="3426e-123">Чтобы включить единое хранилище контактов по клиентам, в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3426e-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="3426e-124">Например:</span><span class="sxs-lookup"><span data-stu-id="3426e-124">For example:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="3426e-125">Чтобы включить единое хранилище контактов для конкретных пользователей, в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3426e-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="3426e-126">Также можно использовать псевдонимы или SIP URI вместо отображаемых имен пользователей.</span><span class="sxs-lookup"><span data-stu-id="3426e-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="3426e-127">Например:</span><span class="sxs-lookup"><span data-stu-id="3426e-127">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="3426e-128">В предыдущем примере первый команда создает новую политику уровня пользователя с именем пользователи с поддержкой UCS с флагом UcsAllowed имеет значение True.</span><span class="sxs-lookup"><span data-stu-id="3426e-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="3426e-129">Вторая команда назначает политику пользователю с отображаемым именем Ken Myer, что означает, что включен Кен Майер для единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="3426e-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="3426e-130">Перенос пользователей в единое хранилище контактов</span><span class="sxs-lookup"><span data-stu-id="3426e-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="3426e-131">Контакты пользователя автоматически переносятся на сервер Exchange 2013 при пользователя:</span><span class="sxs-lookup"><span data-stu-id="3426e-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="3426e-132">Была назначена политика служб пользователя, который имеет UcsAllowed установлено значение True.</span><span class="sxs-lookup"><span data-stu-id="3426e-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="3426e-133">Был подготовлен с почтового ящика Exchange 2013 и по крайней мере один раз вошел в почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="3426e-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="3426e-134">Журналы в с помощью Скайп для бизнеса Расширенный клиент.</span><span class="sxs-lookup"><span data-stu-id="3426e-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="3426e-135">Если пользователь входит в систему под Lync или более ранних клиента или пользователя не подключен к серверу Exchange 2013, игнорируется политика обслуживания пользователей и контактов пользователя остаются в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="3426e-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="3426e-136">Можно определить, перенесены ли контакты пользователя с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="3426e-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="3426e-137">Проверьте следующий раздел реестра на клиентском компьютере:</span><span class="sxs-lookup"><span data-stu-id="3426e-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="3426e-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\URL-адрес <SIP\>\UCS</span><span class="sxs-lookup"><span data-stu-id="3426e-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="3426e-139">Если контакты пользователя хранятся в Exchange 2013, этот раздел содержит значение параметр InUCSMode со значением 2165.</span><span class="sxs-lookup"><span data-stu-id="3426e-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="3426e-140">Выполните командлет **Test-CsUnifiedContactStore** .</span><span class="sxs-lookup"><span data-stu-id="3426e-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="3426e-141">Скайп для Business Server Командная консоль командной строки введите:</span><span class="sxs-lookup"><span data-stu-id="3426e-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="3426e-142">Если **Test-CsUnifiedContactStore** выполнен успешно, контакты пользователя были перенесены в единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="3426e-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="3426e-143">Откат перенесенных пользователей</span><span class="sxs-lookup"><span data-stu-id="3426e-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="3426e-144">Если необходимо выполнить откат объединенных контакт хранилища компонента, откат контактов только в том случае, если переместить пользователя обратно в Exchange 2010 или Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3426e-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="3426e-145">Откат, отключить политику для пользователя и затем выполните командлет **Invoke-CsUcsRollback** .</span><span class="sxs-lookup"><span data-stu-id="3426e-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="3426e-146">Только что под управлением **Invoke-CsUcsRollback** сам по себе он не достаточно обеспечить постоянное отката так как единое хранилище контактов миграции инициируется еще раз Если этот параметр политики не отключен.</span><span class="sxs-lookup"><span data-stu-id="3426e-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="3426e-147">К примеру Если пользователь является откат, поскольку откат Exchange 2013 Exchange 2010, а затем перемещен в почтовый ящик Exchange 2013, миграции единое хранилище контактов инициируется еще раз семь дней после отката, до тех пор, пока сохранять объединенные контакта включен для пользователя в политика обслуживания пользователей.</span><span class="sxs-lookup"><span data-stu-id="3426e-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="3426e-148">Командлет **Move-CsUser** автоматически выполняет откат хранилища контактов пользователя с Exchange 2013 для Скайп для Business Server в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="3426e-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="3426e-149">Когда пользователи перемещаются из Скайп для сервера Microsoft Lync Server 2013 и Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3426e-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="3426e-150">Когда пользователи перемещаются распределенно, например, когда пользователь перемещается из Скайп для бизнеса в Интернет Скайп для Business Server локальных, или наоборот.</span><span class="sxs-lookup"><span data-stu-id="3426e-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="3426e-151">Импорт данных единое хранилище контактов из резервной копии базы данных может привести к единое хранилище контактов данные и данные пользователя к повреждению при изменении режима единое хранилище контактов между экспорта и импорта.</span><span class="sxs-lookup"><span data-stu-id="3426e-151">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import.</span></span> <span data-ttu-id="3426e-152">Например:</span><span class="sxs-lookup"><span data-stu-id="3426e-152">For example:</span></span>
  
- <span data-ttu-id="3426e-153">При экспорте списки контактов перед контактов перенесены в Exchange 2013 и импортируйте после миграции, те же данные будут поврежденных данных единое хранилище контактов и списки контактов.</span><span class="sxs-lookup"><span data-stu-id="3426e-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="3426e-154">При экспорте данных пользователя после миграции пользователей в Exchange 2013, откат миграции и затем для какой-либо причине импорта данных из после завершения переноса, объединенных контакт хранения данных и списки контактов поврежден.</span><span class="sxs-lookup"><span data-stu-id="3426e-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="3426e-155">Перед тем как перемещать с почтовым ящиком Exchange с Exchange 2013 в Exchange 2010, администратор Exchange должен убедитесь в том, что Скайп администратора Business Server сначала возвращается Скайп для контактов пользователя Business Server с Exchange 2013 к Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="3426e-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="3426e-156">Откат контактов единое хранилище контактов для Скайп для Business Server, см процедуре «Чтобы откат контактов единое хранилище контактов с сервера Exchange 2013 кому Скайп for Business Server,» позже в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="3426e-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="3426e-157">**Откате контактов пользователя:** При использовании командлета **Move-CsUser** для перемещения пользователей между Скайп для Business Server 2015 и Lync Server 2010, можно пропустить эти шаги, поскольку командлета **Move-CsUser** автоматически выполняет откат единое хранилище контактов при перемещении пользователей с Скайп для Бизнес-2015 Server на Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3426e-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="3426e-158">**Move-CsUser** отключать политики единое хранилище контактов, поэтому миграции единое хранилище контактов повторяется, если пользователь перемещается обратно Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3426e-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

