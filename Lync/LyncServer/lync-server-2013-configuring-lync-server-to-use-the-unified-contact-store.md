---
title: 'Lync Server 2013: Настройка сервера Lync Server для работы с единым хранилищем контактов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 794d14172c5932436d46fbeb66ea1da4dd7a5e44
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a><span data-ttu-id="3f9c0-102">Настройка Microsoft Lync Server 2013 для работы с единым хранилищем контактов</span><span class="sxs-lookup"><span data-stu-id="3f9c0-102">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f9c0-103">_**Тема последнего изменения:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="3f9c0-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="3f9c0-104">Единое хранилище контактов позволяет пользователям поддерживать один список контактов, а затем включать эти контакты в несколько приложений, включая Microsoft Lync 2013, Microsoft Outlook 2013 и Microsoft Outlook Web App 2013.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-104">The unified contact store enables users to maintain a single contacts list and then have those contacts available in multiple applications, including Microsoft Lync 2013, Microsoft Outlook 2013, and Microsoft Outlook Web App 2013.</span></span> <span data-ttu-id="3f9c0-105">Если вы включите единое хранилище контактов для пользователя, который не хранится в Microsoft Lync Server 2013, а затем извлекается по протоколу SIP.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-105">When you enable the unified contact store for a user that user's contacts are not stored in Microsoft Lync Server 2013 and then retrieved using the SIP protocol.</span></span> <span data-ttu-id="3f9c0-106">Вместо этого его контакты хранятся в Microsoft Exchange Server 2013 и извлекаются с помощью веб-служб Exchange.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-106">Instead, his or her contacts are stored in Microsoft Exchange Server 2013 and are retrieved by using Exchange Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f9c0-107">Технически контактные данные хранятся в паре папок, которые находятся в почтовом ящике Exchange 2013 пользователя.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-107">Technically, contact information is stored in a pair of folders found in the user's Exchange 2013 mailbox.</span></span> <span data-ttu-id="3f9c0-108">Сами контакты хранятся в папке "Контакты Lync", которая отображается для конечных пользователей. метаданные о контактах хранятся во вложенной папке, невидимой для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-108">The contacts themselves are stored in a folder named Lync Contacts which is visible to end users; metadata about the contacts are stored in a subfolder that is not visible to end users.</span></span>



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a><span data-ttu-id="3f9c0-109">Включение единого хранилища контактов для пользователей</span><span class="sxs-lookup"><span data-stu-id="3f9c0-109">Enabling the Unified Contact Store for a User</span></span>

<span data-ttu-id="3f9c0-110">Если вы уже настроили проверку подлинности "сервер-сервер" между Lync Server 2013 и Exchange 2013, вам также будет разрешено использовать единое хранилище контактов; Дополнительная настройка сервера не требуется.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-110">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you have also enabled the use of the unified contact store; no additional server configuration is required.</span></span> <span data-ttu-id="3f9c0-111">Но для перемещения контактов пользователя в единое хранилище контактов необходима дополнительная настройка учетной записи пользователя, чтобы переместить контакты пользователя в единое хранилище.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-111">However, additional user account configuration is required in order to move a user's contacts into the unified contact store.</span></span> <span data-ttu-id="3f9c0-112">По умолчанию контакты пользователей хранятся в Lync Server, а не в едином банке контактов.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-112">By default, user contacts are kept in Lync Server and not in the unified contact store.</span></span>

<span data-ttu-id="3f9c0-113">Управление доступом к единому хранилищу контактов осуществляется с помощью политик служб пользователей Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-113">Access to the unified contact store is managed by using Lync Server user services policies.</span></span> <span data-ttu-id="3f9c0-114">Политики серверов пользователей содержат только одно свойство (UcsAllowed): оно определяет место хранения контактов пользователя.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-114">User server policies have only a single property (UcsAllowed); this property is used to determine the location where a user's contacts are stored.</span></span> <span data-ttu-id="3f9c0-115">Если пользователь управляется политикой пользовательских служб, в которой для Уксалловед установлено значение true ($True), контакты пользователя будут храниться в едином банке контактов.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-115">If a user is managed by a user services policy where UcsAllowed has been set to True ($True) then the user's contacts will be stored in the unified contact store.</span></span> <span data-ttu-id="3f9c0-116">Если пользователь управляется политикой пользовательских служб, в которой для Уксалловед установлено значение false ($False), его контакты будут храниться в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-116">If the user is managed by a user services policy where UcsAllowed has been set to False ($False) then his or her contacts will be stored in Lync Server.</span></span>

<span data-ttu-id="3f9c0-117">При установке Lync Server 2013 также устанавливаются пользовательские политики для отдельных служб (настроенные в глобальной области).</span><span class="sxs-lookup"><span data-stu-id="3f9c0-117">When you install Lync Server 2013 a single user services policy (configured at the global scope) is installed as well.</span></span> <span data-ttu-id="3f9c0-118">Для значения Уксалловед в этой политике задано значение "true", то есть контакты пользователей по умолчанию будут храниться в едином хранилище контактов (предполагая, что оно развернуто и настроено).</span><span class="sxs-lookup"><span data-stu-id="3f9c0-118">The UcsAllowed value in this policy is set to True, meaning that, by default, user contacts will be stored in the unified contact store (assuming this has been deployed and configured).</span></span> <span data-ttu-id="3f9c0-119">Если вы хотите перенести всех пользователей из списка контактов в единое хранилище контактов, вам не нужно ничего делать.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-119">If you want to migrate all of your user contacts to the unified contact store you do not have to do anything at all.</span></span>

<span data-ttu-id="3f9c0-120">Если для вас предпочтительнее не переносить все ваши контакты в единое хранилище контактов, можно заблокировать единое хранилище контактов для всех пользователей, присвоив свойству UcsAllowed в глобальной политике значение False:</span><span class="sxs-lookup"><span data-stu-id="3f9c0-120">If you would prefer not to migrate all your contacts to the unified contact store you can disable the unified contact store for all users by setting the UcsAllowed property in the global policy to False:</span></span>

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

<span data-ttu-id="3f9c0-121">После того как вы отключите единое хранилище контактов в глобальной политике, вы можете создать политику для пользователей, которая позволит использовать единое хранилище контактов; Это позволит некоторым пользователям хранить свои контакты в едином банке контактов, когда другие пользователи продолжают хранить свои контакты в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-121">After you have disabled the unified contact store in the global policy you can then create a per-user policy that enables the use of the unified contact store; this allows you to have some users keep their contacts in the unified contact store while other users continue to keep their contacts in Lync Server.</span></span> <span data-ttu-id="3f9c0-122">Ниже приведен пример команды, позволяющей создать политику служб пользователей для отдельных пользователей:</span><span class="sxs-lookup"><span data-stu-id="3f9c0-122">You can create a per-user user services policy by using a command similar to this:</span></span>

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

<span data-ttu-id="3f9c0-p107">После создания политики ее необходимо назначить всем пользователям, которым требуется доступ к единому хранилищу контактов. Политики на уровне пользователей можно назначить пользователям с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="3f9c0-p107">After you have created the new policy you must then assign that policy to any user who should have access to the unified contact store. Per-user policies can be assigned to users by using commands similar to this:</span></span>

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

<span data-ttu-id="3f9c0-125">После назначения политике сервер Lync Server начнет переносить контакты пользователя в единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-125">After the policy has been assigned Lync Server will begin to migrate the user's contacts to the unified contact store.</span></span> <span data-ttu-id="3f9c0-126">После завершения миграции пользователь сможет хранить свои контакты в Exchange, а не на сервере Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-126">After migration is complete, the user will then have his or her contacts stored in Exchange rather than Lync Server.</span></span> <span data-ttu-id="3f9c0-127">Если пользователь после завершения миграции в Lync 2013 будет выполнен, появится окно с сообщением, и ему будет предложено выйти из Lync, а затем снова войти в систему, чтобы завершить процесс.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-127">If the user happens to be logged on to Lync 2013 at the time migration completes, a message box will appear and he or she will be asked to log off of Lync and then log back on in order to finalize the process.</span></span> <span data-ttu-id="3f9c0-128">Контакты пользователей, которым не назначена эта политика для отдельных пользователей, не переносятся в единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-128">Users who have not been assigned this per-user policy will not have their contacts migrated to the unified contact store.</span></span> <span data-ttu-id="3f9c0-129">Это обусловлено тем, что такие пользователи подпадают под действие глобальной политики, а в глобальной политике доступ к единому хранилищу контактов запрещен.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-129">That’s because those users are being managed by the global policy, and use of the unified contact store has been disabled in the global policy.</span></span>

<span data-ttu-id="3f9c0-130">Вы можете убедиться, что контакты пользователя успешно перенесены в единое хранилище контактов, выполнив командлет [Test-ксунифиедконтактсторе](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-130">You can verify that a user's contacts have successfully been migrated to the unified contact store by running the [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) cmdlet from within the Lync Server Management Shell:</span></span>

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="3f9c0-131">Если Test-CsUnifiedContactStore выполнен успешно, контакты для пользователя sip:kenmyer@litwareinc.com были перенесены в единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-131">If Test-CsUnifiedContactStore succeeds that means that the contacts for the user sip:kenmyer@litwareinc.com have been migrated to the unified contact store.</span></span>

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a><span data-ttu-id="3f9c0-132">Откат в единое хранилище контактов</span><span class="sxs-lookup"><span data-stu-id="3f9c0-132">Rolling Back the Unified Contact Store</span></span>

<span data-ttu-id="3f9c0-133">Если вы хотите удалить контакты пользователя из хранилища Объединенных контактов (например, если нужно переадресовать пользователя на сервере Microsoft Lync Server 2010 и, следовательно, он больше не может использовать единое хранилище контактов), необходимо выполнить два действия.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-133">If you need to remove a user's contacts from the unified contact store (for example, if the user needs to be rehomed on Microsoft Lync Server 2010 and thus can no longer use the unified contact store) you must do two things.</span></span> <span data-ttu-id="3f9c0-134">Сначала следует назначить пользователю новую политику служб пользователей, запрещающую хранение контактов в едином хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-134">First, you must assign the user a new user services policy, one that prohibits storing contacts in the unified contact store.</span></span> <span data-ttu-id="3f9c0-135">(То есть, политика, в которой для свойства Уксалловед задано значение $False.) Если у вас нет такой политики, вы можете создать ее с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="3f9c0-135">(That is, a policy where the UcsAllowed property has been set to $False.) If you do not have such a policy you can create one using a command similar to this:</span></span>

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

<span data-ttu-id="3f9c0-136">Затем вы можете назначить эту политику на уровней пользователей (NoUnifiedContactStore) с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="3f9c0-136">You can then assign this new per-user policy (NoUnifiedContactStore) by using a command like this:</span></span>

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

<span data-ttu-id="3f9c0-137">Предыдущая команда назначает новую политику пользователю Ken Myer и не позволяет переносить его контакты в единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-137">The preceding command assigns the new policy to the user Ken Myer, and also prevents Ken's contacts from being migrated to the unified contact store.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f9c0-138">В некоторых случаях вы можете добиться того же результата, просто отменив Назначение текущей политики пользователей.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-138">In some cases you can achieve the same net effect by simply unassigning the user's current user services policy.</span></span> <span data-ttu-id="3f9c0-139">Например, предположим, что политика служб пользователя Ken Myer разрешает ему доступ к единому хранилищу контактов, но глобальная политика запрещает доступ к нему.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-139">For example, suppose Ken Myer has a per-user user services policy the enables the unified contact store, but your global policy prohibits the use of the unified contact store.</span></span> <span data-ttu-id="3f9c0-140">В этом случае вы можете снять назначение Ken политики служб для пользователей.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-140">In that case, you could unassign Ken's per-user services policy.</span></span> <span data-ttu-id="3f9c0-141">После этого пользователь Ken автоматически подпадает под действие глобальной политики и лишается доступа к единому хранилищу контактов.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-141">When you do that, Ken will automatically be managed by the global policy, and thus will no longer have access to the unified contact store.</span></span><BR><span data-ttu-id="3f9c0-142">Чтобы отменить назначение ранее назначенной политики для пользователя, используйте ту же команду, что и при указании, но в этот раз параметру Полицинаме будет присвоено значение NULL:</span><span class="sxs-lookup"><span data-stu-id="3f9c0-142">To unassign a previously-assigned per-user policy, use the same command as shown before, but this time set the PolicyName parameter to a null value:</span></span><BR><span data-ttu-id="3f9c0-143">Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="3f9c0-143">Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



</div>

<span data-ttu-id="3f9c0-144">При работе с единым хранилищем контактов следует учитывать правило, согласно которому контакты пользователя не переносятся в единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-144">The terminology "prevents Ken's contacts from being migrated to the unified contact store" is important to keep in mind when working with the unified contact store.</span></span> <span data-ttu-id="3f9c0-145">Если просто назначить для пользователя Ken новую политику служб пользователя, его контакты не переносятся из единого хранилища контактов.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-145">Simply assigning Ken a new user services policy will not move his contacts out of the unified contact store.</span></span> <span data-ttu-id="3f9c0-146">Когда пользователь входит в Lync Server 2013, система проверяет политику пользовательских служб, чтобы узнать, нужно ли хранить ее контакты в едином банке контактов.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-146">When a user logs on to Lync Server 2013, the system checks the user's user services policy to see whether his or her contacts should be kept in the unified contact store.</span></span> <span data-ttu-id="3f9c0-147">В случае утвердительного ответа (для свойства UcsAllowed задано значение $True) эти контакты переносятся в единое хранилище контактов (если они еще не находятся в нем).</span><span class="sxs-lookup"><span data-stu-id="3f9c0-147">If the answer is yes (that is, if the UcsAllowed property is set to $True) then those contacts will be migrated to the unified contact store (assuming that those contacts are not already in the unified contact store).</span></span> <span data-ttu-id="3f9c0-148">Если ответ отсутствует, Lync Server просто пропускает контакты пользователя и переходит к следующей задаче.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-148">If the answer is no, then Lync Server simply ignores the user's contacts and moves on to its next task.</span></span> <span data-ttu-id="3f9c0-149">Это означает, что Lync Server не будет автоматически переносить контакты пользователя из единого хранилища контактов независимо от значения свойства Уксалловед.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-149">That means that Lync Server will not automatically move a user's contacts from out of the unified contact store, regardless of the value of the UcsAllowed property.</span></span>

<span data-ttu-id="3f9c0-150">Это также означает, что после назначения пользователю новой политики пользовательских служб необходимо запустить командлет [Invoke-ксуксроллбакк](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) , чтобы переместить контакты пользователя из Exchange 2013 и обратно в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-150">That also means that, after assigning the user a new user services policy, you must then run the [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) cmdlet in order to move the user's contacts out of Exchange 2013 and back to Lync Server 2013.</span></span> <span data-ttu-id="3f9c0-151">Например, после назначения пользователю Ken Myer новой политики служб пользователя можно перенести его контакты из единого хранилища контактов с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="3f9c0-151">For example, after assigning Ken Myer a new user services policy you can then move his contacts out of the unified contact store by using the following command:</span></span>

    Invoke-CsUcsRollback -Identity "Ken Myer"

<span data-ttu-id="3f9c0-152">Если изменить политику служб пользователя, но не выполнять командлет Invoke-CsUcsRollback, контакты пользователя Ken не удаляются из единого хранилища контактов.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-152">If you change the user services policy but do not run the Invoke-CsUcsRollback cmdlet Ken's contacts will not be removed from the unified contact store.</span></span> <span data-ttu-id="3f9c0-153">Что происходит, если выполнить Invoke-CsUcsRollback, не изменяя политику служб пользователя Ken Myer?</span><span class="sxs-lookup"><span data-stu-id="3f9c0-153">What if you run Invoke-CsUcsRollback but do not change Ken Myer's user services policy?</span></span> <span data-ttu-id="3f9c0-154">Контакты этого пользователя временно удаляются из единого хранилища контактов.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-154">In that case, Ken's contacts will be temporarily removed from the unified contact store.</span></span> <span data-ttu-id="3f9c0-155">Важно помнить о том, что контакты удаляются временно.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-155">The fact that this removal is temporary is important to keep in mind.</span></span> <span data-ttu-id="3f9c0-156">После того как контакты Кен были удалены из хранилища контактов, Lync Server 2013 ждет 7 дней, а затем проверит, какая политика служб пользователей назначена Кенам.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-156">After Ken's contacts have been removed from the unified contact store, Lync Server 2013 will wait 7 days and then check to see which user services policy has been assigned to Ken.</span></span> <span data-ttu-id="3f9c0-157">Если пользователю Ken по-прежнему назначена политика, разрешающая ему доступ к единому хранилищу контактов, его контакты автоматически перемещаются в хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-157">If Ken is still assigned a policy that enables the user of the unified contact store, then his contacts will automatically be moved back to into the contact store.</span></span> <span data-ttu-id="3f9c0-158">Для удаления контактов из хранилища контактов без возможности восстановления необходимо не только выполнить командлет Invoke-CsUcsRollback, но и изменить политику служб пользователя.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-158">To permanently remove contacts from the unified contact store you must change the user services policy in addition to running the Invoke-CsUcsRollback cmdlet.</span></span>

<span data-ttu-id="3f9c0-p114">Из-за большого количества переменных, влияющих на перенос, трудно определить, сколько времени потребуется для полного переноса учетных записей в единое хранилище контактов. В качестве общего правила следует иметь в виду, что перенос не вступает в силу немедленно: даже при переносе небольшого числа контактов для полного завершения переноса может потребоваться около 10 минут.</span><span class="sxs-lookup"><span data-stu-id="3f9c0-p114">Due to the large number of variables that can affect migration, it is difficult to estimate how long it will take before accounts are fully migrated to the unified contact store. As a general rule, however, migration does not take effect immediately: even when migrating a small number of contacts it might take 10 minutes or more before the move is complete.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

